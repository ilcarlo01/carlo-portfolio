<template>
  <!-- Navbar container -->
  <nav class="fixed top-4 left-1/2 transform -translate-x-1/2 z-40 w-[90%] max-w-xl bg-white/50 backdrop-blur-md rounded-full shadow-md px-6 py-3 flex justify-center items-center">

    <!-- Desktop Links -->
    <ul class="hidden sm:flex gap-6 text-sm font-medium text-black">
      <li><a href="#" class="hover:text-blue-300 transition">Web design</a></li>
      <li><a href="#" class="hover:text-blue-300 transition">Branding</a></li>
      <li><a href="#" class="hover:text-blue-300 transition">Animazione</a></li>
      <li><a href="#" class="hover:text-blue-300 transition">Contatti</a></li>
    </ul>

    <!-- Burger Icon (mobile only) -->
    <button @click="menuOpen = true" class="sm:hidden text-black text-3xl z-50">
      ☰
    </button>
  </nav>

  <!-- Fullscreen Mobile Menu -->
  <div v-if="menuOpen" class="fixed inset-0 z-50 bg-black/90 backdrop-blur-md flex flex-col justify-center items-center gap-8 text-white text-xl">
    <button @click="menuOpen = false" class="absolute top-6 right-6 text-4xl">✕</button>
    <a href="#" @click="menuOpen = false" class="hover:text-blue-300 transition">Projekte</a>
    <a href="#" @click="menuOpen = false" class="hover:text-blue-300 transition">Agentur</a>
    <a href="#" @click="menuOpen = false" class="hover:text-blue-300 transition">Journal</a>
    <a href="#" @click="menuOpen = false" class="hover:text-blue-300 transition">Kontakt</a>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const menuOpen = ref(false)
</script>



