<script setup lang="ts"></script>

<template>
  <div class="flex flex-col w-full h-full p-3 md:p-5 bg-main-000 text-main-900">
    <header
      class="flex flex-wrap justify-around items-center h-[50px] max-h-[10vh] bg-main-200"
    >
      <div>icon</div>
      <div class="flex gap-3 md:gap-5">
        <p>Work</p>
        <p>Services & Pricing</p>
        <p>Socials</p>
        <p>About</p>
      </div>
      <button>Order template</button>
    </header>
    <main class="flex-1 flex items-center justify-center bg-main-300">
      <div class="w-[25vw] h-full bg-main-400" />
      <div class="flex w-full flex-col items-center text-center justify-center">
        <p class="text-3xl md:text-5xl">Innovative monocolor templates</p>
        <p class="text-xl md:text-3xl text-main-700">
          Crafted with passion and powered by the latest technology
        </p>
        <div class="flex justify-center items-center gap-3 md:gap-5">
          <button>Consult</button>
          <button>View pricing</button>
        </div>
      </div>
      <div class="w-[25vw] h-full bg-main-400" />
    </main>
    <footer
      class="flex justify-around items-center h-[50px] max-h-[10vh] bg-main-200"
    >
      <p>2025 Jakub Hajduk</p>
      <p>Monocolor Design H:275</p>
    </footer>
  </div>
</template>

<style scoped></style>
