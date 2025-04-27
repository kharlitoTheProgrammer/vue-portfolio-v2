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
  <main
    class="w-[52%] text-[#A49581] space-y-24 flex-grow py-24 max-h-full overflow-y-auto -mr-40 pr-40"
  >
    <section id="about" class="space-y-10 special-gothic-expanded-one-regular">
      <p class="text-2xl opacity-60">
        I'm a junior frontend developer passionate about building clean,
        accessible, and responsive user interfaces. I enjoy turning designs into
        functional, polished experiences while continuously improving my skills
        in performance, usability, and modern web technologies. I'm excited
        about creating projects that not only look great but also offer a smooth
        and thoughtful user experience.
      </p>
      <p class="text-2xl opacity-60">
        Currently, I'm a Front-End Developer Intern at
        <span class="font-bold">DepEd CALABARZON Region IV-A</span>, where I
        <span class="font-bold"
          >contribute to building and improving internal web applications.</span
        >
        I focus on developing
        <span class="font-bold">responsive, user-friendly interfaces</span>
        while collaborating with the team to ensure clean code practices and a
        smooth user experience. During my internship,
        <span class="font-bold"
          >I have strengthened my skills in modern frontend technologies and
          learned the importance of usability, accessibility, and performance in
          real-world projects.</span
        >
      </p>
      <p class="text-2xl opacity-60">
        During my capstone project, which was ranked among the top 10 in my
        semester within the IT department, I had the opportunity to explore both
        frontend and backend development. While I focused mainly on the
        frontend, this experience allowed me to build a solid foundation in
        backend technologies, deepening my passion for creating meaningful,
        user-centered solutions.
      </p>
    </section>
    <section id="experience" class="special-gothic-regular">
      <h3
        class="text-4xl opacity-100 font-bold special-gothic-expanded-one-regular"
      >
        Experience
      </h3>
      <div class="flex flex-col gap-5">
        <div class="mt-5 flex justify-between w-full">
          <div class="w-[35%] flex">
            <span class="text-2xl opacity-75">2025 - Present</span>
          </div>
          <div class="w-full flex flex-col gap-1">
            <!-- Change from w-full to w-[60%] -->
            <h4 class="text-2xl font-bold">
              Front-End Developer Intern - Department of Education
            </h4>
            <p class="text-lg">
              Contributed to the development of the School account feature using
              Vue by integrating APIs for data retrieval and submission.
              Assisted in setting up client-side routing and building responsive
              user interfaces with Tailwind CSS, enhancing the overall
              functionality and user experience of the Special Order
              Application.
            </p>
          </div>
        </div>
        <div class="mt-5 flex justify-between w-full">
          <div class="w-[35%] flex">
            <span class="text-2xl opacity-75">2024 - 2025</span>
          </div>
          <div class="w-full flex flex-col gap-1">
            <!-- Change from w-full to w-[60%] -->
            <h4 class="text-2xl font-bold">
              Full Stack Android Developer (Capstone) - R.Sarabia Optical
            </h4>
            <p class="text-lg">
              Mobile-Based Virtual Eyeglass Frame Fitting Using Augmented
              Reality with Integrated Online Appointment Management System for
              R. Sarabia Optical. A cutting-edge solution combining augmented
              reality (AR) technology to allow users to virtually try on
              eyeglass frames from the comfort of their own homes. This system
              is complemented by an online appointment management feature,
              enabling seamless scheduling for in-store fittings and
              consultations at R. Sarabia Optical, enhancing customer
              convenience and engagement.
            </p>
          </div>
        </div>
      </div>
    </section>
    <section id="projects" class="special-gothic-regular">
      <h3 class="font-bold text-4xl special-gothic-expanded-one-regular">
        Projects
      </h3>
      <div
        class="flex gap-2 mt-5"
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
    <footer class="text-lg w-2/3">
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
</style>
