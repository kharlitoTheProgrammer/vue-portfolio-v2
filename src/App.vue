<script setup lang="ts">
import { ref, onMounted } from "vue";
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";
import LoadingComponent from "./components/LoadingComponent.vue";

const isLoading = ref<boolean>(true);

setTimeout(() => {
  isLoading.value = false; // Set loading to false after 3 seconds
}, 2200);

let cursorGlow: HTMLElement | null = null;

// Mouse target
let mouseX = window.innerWidth / 2;
let mouseY = window.innerHeight / 2;
// Current position of the glow
let currentX = mouseX;
let currentY = mouseY;

// Higher smoothing factor for *buttery smoothness*
const smoothing = 0.08; // Try 0.05 to 0.1 for even slower/smoother feel

function animate() {
  if (cursorGlow) {
    // Lerp towards mouse position
    currentX += (mouseX - currentX) * smoothing;
    currentY += (mouseY - currentY) * smoothing;

    // Apply translation
    cursorGlow.style.transform = `translate(${currentX - 100}px, ${currentY - 100}px)`;
    // (subtract half size because your div is 200x200)
  }
  requestAnimationFrame(animate);
}

onMounted(() => {
  cursorGlow = document.getElementById('cursor-glow');

  document.addEventListener('mousemove', (e) => {
    mouseX = e.clientX;
    mouseY = e.clientY;
  });

  animate();
});
</script>

<template>
  <div class="bg-[#1A2421] h-screen">
    <div id="cursor-glow"></div>

    <div v-if="isLoading">
      <LoadingComponent />
    </div>
    <div class="flex justify-between h-full max-w-screen px-40 gap-8" v-else>
      <HeaderComponent />
      <MainComponent />
    </div>
  </div>
</template>

<style scoped>
#cursor-glow {
  position: fixed;
  top: 0;
  left: 0;
  width: 200px;
  height: 200px;
  background: radial-gradient(circle, rgba(34, 48, 44, 1) 0%, transparent 60%);
  border-radius: 50%;
  pointer-events: none;
  z-index: 9999;
  mix-blend-mode: screen;
  filter: blur(50px);
  transition: background 0.3s ease;
}
</style>