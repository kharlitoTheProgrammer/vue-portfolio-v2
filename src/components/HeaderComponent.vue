<script setup lang="ts">
import {
  SquareArrowOutUpRightIcon,
  LinkedinIcon,
  GithubIcon,
} from "lucide-vue-next";
import { ref } from "vue";

const navItems = ref<any>([
  { isSelected: true, label: "About", name: "about" },
  { isSelected: false, label: "Experience", name: "experience" },
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
</script>

<template>
  <header
    class="sticky top-0 flex flex-col justify-between w-[48%] special-gothic-expanded-one-regular z-50 py-24 h-full"
  >
    <div>
      <h1 class="text-[#D5C7B2] text-5xl">Kharl Aquino</h1>
      <h2 class="text-[#A49581]">Frontend Developer</h2>
      <button
        class="mt-10 cursor-pointer text-[#A49581] opacity-70 hover:-translate-y-1 transition ease-in-out duration-300 hover:opacity-100 flex items-center justify-center gap-1 text-xs animate-pulse"
      >
        View resume <SquareArrowOutUpRightIcon :size="10" />
      </button>
      <section class="mt-10">
        <ul class="text-[#A49581]">
          <li
            v-for="(item, index) in navItems"
            :key="index"
            @click="selectItem(index, item.name)"
            class="cursor-pointer transition duration-300 ease-in-out"
            :class="{
              'hover:underline opacity-50 hover:opacity-80': !item.isSelected,
            }"
          >
            <span
              v-if="item.isSelected"
              class="transition-all duration-900 ease-in-out"
              >━━━ <span>{{ item.label }}</span></span
            >
            <span v-else>{{ item.label }}</span>
          </li>
        </ul>
      </section>
    </div>
    <ul class="flex gap-2">
      <li
        class="hover:-translate-y-1 transition duration-500 hover:scale-110 cursor-pointer"
      >
        <a
          href="https://www.linkedin.com/in/kharl-chris-an-aquino-b6617625b/"
          target="_blank"
        >
          <LinkedinIcon color="#A49581" :size="20" />
        </a>
      </li>
      <li
        class="hover:-translate-y-1 transition duration-500 hover:scale-110 cursor-pointer"
      >
        <a href="https://www.github.com/kharlitoTheProgrammer" target="_blank">
          <GithubIcon color="#A49581" :size="20" />
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
</style>
