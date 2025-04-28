<script setup lang="ts">
import ProjectsTab from "./ProjectsTab.vue";
import AboutTab from "./AboutTab.vue";
import ExperienceTab from "./ExperienceTab.vue";
import CertificationTab from "./CertificationTab.vue";
import TechStackComponent from "./TechStackComponent.vue";
</script>

<template>
  <main class="w-[52%] text-[#A49581] space-y-24 flex-grow py-24 max-h-full overflow-y-auto -mr-40 pr-40 slide2">
    <AboutTab />
    <ExperienceTab />
    <TechStackComponent />
    <ProjectsTab />
    <CertificationTab />
    <footer class="text-lg w-2/3 special-gothic-expanded-one-regular">
      Designed in <span class="font-bold">Figma</span> and developed in
      <span class="font-bold">Visual Studio Code</span> using
      <span class="font-bold">Vue 3</span> and
      <span class="font-bold">Tailwind CSS</span>. Deployed on
      <span class="font-bold">Vercel</span> for a fast and seamless experience.
    </footer>
  </main>
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

@keyframes slideInRight {
  from {
    transform: translateX(400px);
    filter: blur(2px);
    transition: all 1s;
  }

  to {
    transform: translateX(0);
  }
}

.slide2 {
  animation-name: slideInRight;
  animation-duration: 1s;
  animation-timing-function: ease-in;
  animation-delay: 0s;
  animation-iteration-count: 1;
  animation-direction: normal;
  animation-fill-mode: none;
}
</style>
