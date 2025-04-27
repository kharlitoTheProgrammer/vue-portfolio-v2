<script setup lang="ts">
import { ref } from "vue";

const techUsedSO = ref([
  { label: "JavaScript" },
  { label: "TypeScript" },
  { label: "Vue JS" },
  { label: "Tailwind CSS" },
]);

const techUsedCaps = ref([{ label: "Kotlin" }, { label: "Android Studio" }]);

const projects = ref([
  {
    title: "Special Order Application",
    description:
      "Contributed to the development of a web app for generating Special Order documents for graduating students. Utilized Vue.js for dynamic rendering and API integration. Helped design a responsive UI using Tailwind CSS. Assisted in backend API management with Laravel",
    techUsed: techUsedSO,
  },
  {
    title:
      "Mobile-Based Virtual Eyeglass Frame Fitting Using Augmented Reality with Integrated Online Appointment Management System for R. Sarabia Optical",
    description:
      "Developed a mobile AR app for virtual eyeglass fitting, serving 150+ users, with Firebase integration for authentication and data storage. Led UI and functionality improvements.",
    techUsed: techUsedCaps,
  },
]);
</script>

<template>
  <section id="projects" class="special-gothic-regular">
    <h3 class="font-bold text-4xl special-gothic-expanded-one-regular">
      Projects
    </h3>
    <div
      class="flex gap-2 mt-5 hover:bg-[#20332A] px-6 py-3 rounded-xl hover:transition hover:duration-700 group"
      v-for="(item, index) in projects"
      :key="index"
    >
      <div>
        <div class="border border-gray-500 w-50 h-50 rounded-md mr-5"></div>
      </div>
      <div class="space-y-3">
        <h4 class="text-2xl font-bold">{{ item.title }}</h4>
        <p class="text-xl opacity-80">{{ item.description }}</p>
        <div class="flex flex-wrap mt-1 gap-0.5">
          <p
            class="text-sm text-[#2E7D32] bg-[#121815] h-7 rounded-full flex justify-center items-center px-5 py-1 font-bold hover:-translate-y-2 transition-all ease-in-out duration-500"
            v-for="(itemUsed, index) in item.techUsed"
            :key="index"
          >
            {{ itemUsed.label }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>
