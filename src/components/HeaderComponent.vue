<script setup lang="ts">
import {
  SquareArrowOutUpRightIcon,
  LinkedinIcon,
  GithubIcon,
} from "lucide-vue-next";
import { onMounted, ref } from "vue";

const navItems = ref<any>([
  { isSelected: true, label: "About", name: "about" },
  { isSelected: false, label: "Experience", name: "experience" },
  { isSelected: false, label: "Tech Stack", name: "techStack" },
  { isSelected: false, label: "Projects", name: "projects" },
  { isSelected: false, label: "Certifications", name: "certifications" },
]);

const selectItem = (index: any, sectionId: string) => {
  navItems.value.forEach((item: { isSelected: boolean }) => {
    item.isSelected = false;
  });
  navItems.value[index].isSelected = true;

  const element = document.getElementById(sectionId);
  if (element) {
    element.scrollIntoView({ behavior: "smooth" });
  }
};

onMounted(() => {
  const sections = document.querySelectorAll("section");
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          const id = entry.target.getAttribute("id");
          if (id) {
            navItems.value.forEach((item: { isSelected: boolean; name: string; }) => {
              item.isSelected = item.name === id;
            });
          }
        }
      });
    },
    { threshold: 0.5 } // triggers when 50% of the section is in view
  );

  sections.forEach((section) => {
    observer.observe(section);
  });
});
</script>

<template>
  <header
    class="sticky top-0 flex flex-col justify-between w-[48%] special-gothic-expanded-one-regular z-50 py-24 h-full slide">
    <div>
      <h1 class="text-[#D5C7B2] text-6xl">Kharl Aquino</h1>
      <h2 class="text-[#A49581] text-3xl">Frontend Developer</h2>

      <button
        class="mt-20 cursor-pointer text-[#A49581] opacity-80 hover:-translate-y-1 transition ease-in-out duration-300 hover:opacity-100 gap-1 text-xl animate-pulse">
        <a href="/Resume_Kharl_Aquino.pdf" class="flex items-center justify-center gap-2">
          View resumé
          <SquareArrowOutUpRightIcon :size="15" />
        </a>
      </button>

      <section class="mt-5">
        <ul class="text-[#A49581]">
          <li v-for="(item, index) in navItems" :key="index" @click="selectItem(index, item.name)"
            class="cursor-pointer transition duration-300 ease-in-out text-4xl" :class="{
              'hover:underline opacity-50 hover:opacity-80': !item.isSelected,
            }">
            <span v-if="item.isSelected" class="transition-all duration-900 ease-in-out">━━━ <span>{{ item.label
            }}</span></span>
            <span v-else>{{ item.label }}</span>
          </li>
        </ul>
      </section>
    </div>
    <ul class="flex gap-2">
      <li class="hover:-translate-y-1 transition duration-500 hover:scale-110 cursor-pointer">
        <a href="https://www.linkedin.com/in/kharl-chris-an-aquino-b6617625b/" target="_blank">
          <LinkedinIcon color="#A49581" :size="35" />
        </a>
      </li>
      <li class="hover:-translate-y-1 transition duration-500 hover:scale-110 cursor-pointer">
        <a href="https://www.github.com/kharlitoTheProgrammer" target="_blank">
          <GithubIcon color="#A49581" :size="35" />
        </a>
      </li>
    </ul>
  </header>
</template>
<style scoped>
.special-gothic-expanded-one-regular {
  font-family: "Special Gothic Expanded One", sans-serif;
  font-weight: 400;
  font-style: normal;
}

.special-gothic-regular {
  font-family: "Special Gothic", sans-serif;
  font-weight: 400;
  font-style: normal;
}

@keyframes slideInLeft {
  from {
    transform: translateX(-400px);
    filter: blur(2px);
    transition: all 1s;
  }

  to {
    transform: translateX(0);
  }
}

.slide {
  animation-name: slideInLeft;
  animation-duration: 1.2s;
  animation-timing-function: ease-in-out;
  animation-delay: 0s;
  animation-iteration-count: 1;
}
</style>
