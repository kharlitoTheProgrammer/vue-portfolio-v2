<script setup lang="ts">
import { ref } from "vue";
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";
import LoadingComponent from "./components/LoadingComponent.vue";

const isLoading = ref<boolean>(true);

setTimeout(() => {
  isLoading.value = false; // Set loading to false after 3 seconds
}, 2200);
</script>

<template>
  <div class="bg-[#1A2421] h-screen">
    <div v-if="isLoading">
      <LoadingComponent />
    </div>
    <div class="flex justify-between h-full max-w-screen px-40 gap-8" v-else>
      <HeaderComponent />
      <MainComponent />
    </div>
  </div>
</template>
