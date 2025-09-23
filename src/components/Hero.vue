<template>
  <section class="relative w-full h-screen bg-black overflow-hidden">
    <Backgroundlayer/>
    <h1 class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 text-[8vw] font-bold tracking-wide z-10 text-white">
      PortfolIO
    </h1>
     <!-- Messaggio Scroll in fondo -->
    <div class="absolute bottom-6 left-1/2 transform -translate-x-1/2 z-20">
      <div class="flex items-center gap-2 text-gray-300 text-sm animate-bounce">
        <span class="bg-white text-black px-3 py-1 rounded-full shadow-md">Scroll</span>
        <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
        </svg>
      </div>
    </div>
  </section>
</template>

<script setup>
import Backgroundlayer from './Backgroundlayer.vue';
</script>
