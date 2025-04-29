<script setup lang="ts">
import { Icon } from "@iconify/vue/dist/iconify.js";
import { ref } from "vue";

const techStack = ref([
  { icon: "devicon:html5", label: "HTML" },
  { icon: "devicon:css3", label: "CSS" },
  { icon: "devicon:javascript", label: "JavaScript" },
  { icon: "devicon:typescript", label: "TypeScript" },
  { icon: "devicon:vuejs", label: "Vue" },
  { icon: "devicon:react", label: "React" },
  { icon: "devicon:angular", label: "Angular" },
  { icon: "devicon:tailwindcss", label: "Tailwind CSS" },
]);
const techTools = ref([
  { icon: "devicon:vitejs", label: "Vite" },
  { icon: "devicon:vscode", label: "Visual Studio Code" },
  { icon: "devicon:androidstudio", label: "Android Studio" },
]);
</script>

<template>
  <section id="techStack" class="special-gothic-regular">
    <h3
      class="text-4xl opacity-100 font-bold special-gothic-expanded-one-regular"
    >
      Tech Stack
    </h3>
    <div class="flex flex-col gap-5">
      <div
        class="mt-5 flex flex-col justify-between w-full hover:bg-[#20332A] px-6 py-3 rounded-xl hover:transition hover:duration-700 group"
      >
        <div class="flex flex-col w-full">
          <div class="flex justify-center items-center">
            <h3 class="text-xl special-gothic-expanded-one-regular">
              Frontend
            </h3>
          </div>
          <div class="grid grid-cols-4 items-center justify-center pt-4 gap-10">
            <div
              v-for="(item, index) in techStack"
              :key="index"
              class="flex flex-col items-center gap-2 hover:-translate-y-2 duration-600 transition ease-in-out"
            >
              <Icon :icon="item.icon" :height="30" :width="30" />
              <p>{{ item.label }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="flex flex-col gap-5">
      <div
        class="mt-5 flex flex-col justify-between w-full hover:bg-[#20332A] px-6 py-3 rounded-xl hover:transition hover:duration-700 group"
      >
        <div class="flex flex-col w-full">
          <div class="flex justify-center items-center">
            <h3 class="text-xl special-gothic-expanded-one-regular">
              Verion Control
            </h3>
          </div>
          <div class="flex flex-wrap items-center justify-center pt-4 gap-10">
            <div
              class="flex flex-col items-center gap-2 hover:-translate-y-2 duration-600 transition ease-in-out"
            >
              <Icon icon="devicon:github" :height="30" :width="30" />
              <p>Github</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="flex flex-col gap-5">
      <div
        class="mt-5 flex flex-col justify-between w-full hover:bg-[#20332A] px-6 py-3 rounded-xl hover:transition hover:duration-700 group"
      >
        <div class="flex flex-col w-full">
          <div class="flex justify-center items-center">
            <h3 class="text-xl special-gothic-expanded-one-regular">Tools</h3>
          </div>
          <div class="grid grid-cols-3 items-center justify-center pt-4 gap-10">
            <div
              v-for="(item, index) in techTools"
              :key="index"
              class="flex flex-col items-center gap-2 hover:-translate-y-2 duration-600 transition ease-in-out"
            >
              <Icon :icon="item.icon" :height="30" :width="30" />
              <p>{{ item.label }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
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
