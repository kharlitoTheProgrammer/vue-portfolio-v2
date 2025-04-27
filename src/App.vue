<script setup lang="ts">
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";
</script>

<template>
  <div class="bg-[#1A2421] h-screen">
    <!-- <div
      class="fixed inset-0 backdrop-blur-lg flex items-center justify-center py-10"
    >
      <div class="bg-white w-1/2 h-full"></div>
    </div> -->
    <div class="flex justify-between h-full max-w-screen px-40 gap-8">
      <HeaderComponent />
      <MainComponent />
    </div>
  </div>
</template>
