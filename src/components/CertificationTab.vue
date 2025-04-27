<script setup lang="ts">
import { ref } from "vue";

const certifications = ref([
  {
    date: "June 16, 2023",
    instructor: "freeCodeCamp",
    certName: "Responsive Web Design",
  },
  {
    date: "December 11, 2023",
    instructor: "Cisco Networking Academy",
    certName: "JavaScript Essentials 1",
  },
  {
    date: "December 7, 2023",
    instructor: "Dr. Angela Yu",
    certName: "The Complete 2023 Web Development Bootcamp",
  },
]);
</script>

<template>
  <section id="certifications" class="special-gothic-regular">
    <h3
      class="text-4xl opacity-100 font-bold special-gothic-expanded-one-regular"
    >
      Certifications
    </h3>
    <div class="flex flex-col gap-5">
      <div
        class="mt-5 flex justify-between w-full"
        v-for="(item, index) in certifications"
        :key="index"
      >
        <div class="w-[35%] flex mr-10">
          <span class="text-2xl opacity-75">{{ item.date }}</span>
        </div>
        <div class="w-full flex flex-col gap-1">
          <!-- Change from w-full to w-[60%] -->
          <h4 class="text-3xl font-bold">
            {{ item.certName }}
          </h4>
          <p class="text-xl">
            {{ item.instructor }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>
