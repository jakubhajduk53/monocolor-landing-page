<script setup lang="ts">
import { ref, onMounted, onUnmounted } from "vue";

const hue = ref(275);
const isRotating = ref(false);
let intervalId: ReturnType<typeof setInterval> | null = null;

const updateHue = () => {
  document.documentElement.style.setProperty(
    "--main-hue",
    hue.value.toString()
  );
};

const toggleRotation = () => {
  isRotating.value = !isRotating.value;

  if (isRotating.value) {
    intervalId = setInterval(() => {
      hue.value = (hue.value + 1) % 360;
      updateHue();
    }, 50);
  } else if (intervalId) {
    clearInterval(intervalId);
    intervalId = null;
  }
};

onMounted(() => updateHue());
onUnmounted(() => {
  if (intervalId) clearInterval(intervalId);
});
</script>

<template>
  <div
    class="flex flex-col w-full h-full p-1 md:p-3 bg-main-000 text-main-900 font-roboto"
  >
    <header
      class="flex flex-wrap justify-around items-center h-[50px] max-h-[10vh] bg-main-200"
    >
      <div class="text-base md:text-xl">MONOCOLOR</div>
      <div class="flex gap-3 md:gap-5">
        <a href="#" class="cursor-pointer">Work</a>
        <a href="#" class="cursor-pointer">Services & pricing</a>
        <a href="#" class="cursor-pointer">Socials</a>
        <a href="#" class="cursor-pointer">About</a>
      </div>
      <button class="cursor-pointer">Order template</button>
    </header>
    <main class="flex-1 flex items-center justify-center bg-main-300">
      <div class="w-[25vw] h-full bg-main-400" />
      <div class="flex w-full flex-col items-center text-center justify-center">
        <p class="text-3xl md:text-5xl">Innovative monocolor templates</p>
        <p class="text-xl md:text-3xl text-main-700">
          Crafted with passion and powered by the latest technology
        </p>
      </div>
      <div class="w-[25vw] h-full bg-main-400" />
    </main>
    <footer
      class="flex justify-center items-center text-center h-[50px] max-h-[10vh] bg-main-200"
    >
      <p>
        Monocolor Design Hue:
        <input
          type="number"
          min="0"
          max="360"
          v-model.number="hue"
          @input="updateHue"
          class="w-[7ch] rounded px-2"
        />
        <button
          class="underline underline-offset-4 cursor-pointer"
          @click="toggleRotation"
        >
          Color Rotation {{ isRotating ? "On" : "Off" }}
        </button>
      </p>
    </footer>
  </div>
</template>

<style scoped></style>
