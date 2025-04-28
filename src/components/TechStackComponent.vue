<script setup lang="ts">
import { Icon } from '@iconify/vue/dist/iconify.js';
</script>

<template>
    <section id="techStack" class="special-gothic-regular">
        <h3 class="text-4xl opacity-100 font-bold special-gothic-expanded-one-regular">Tech Stack</h3>
        <div class="flex flex-col gap-5">
            <div
                class="mt-5 flex justify-between w-full hover:bg-[#20332A] px-6 py-3 rounded-xl hover:transition hover:duration-700 group">
                <div class="flex flex-col w-full">
                    <div class="flex justify-center items-center">
                        <h3 class="text-xl special-gothic-expanded-one-regular">Frontend</h3>
                    </div>
                    <div class="flex flex-col">
                        <Icon icon="devicon:html5" width="40" height="40" />
                        <p>HTML</p>
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