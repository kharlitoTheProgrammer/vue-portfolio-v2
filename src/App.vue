<script setup lang="ts">
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";
</script>

<template>
  <div class="bg-[#1A2421] h-screen">
    <div class="flex justify-between h-full max-w-screen px-20 gap-8">
      <HeaderComponent />
      <MainComponent />
    </div>
  </div>
</template>
