<template>
  <div class="absolute inset-0 overflow-hidden z-0">
    <div
  ref="collage"
  :class="[
    'relative transition-transform duration-100 ease-out',
    isMobile ? 'w-[100vw] h-[100vh]' : 'w-[200vw] h-[200vh]'
  ]"
  :style="transformStyle"
  @mousemove="handleMouse"
>
      <div
        v-for="(img, i) in images"
        :key="i"
        :style="img.style"
        class="absolute group rounded-lg shadow-md overflow-hidden"
      >
        <!-- Immagine colorata, diventa grigia al hover -->
        <img
         :src="img.src"
          class="w-full h-auto transition duration-300 ease-in-out group-hover:grayscale"
        />
        <!-- Layer scuro con scritta -->
        <div
          class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-75 opacity-0 group-hover:opacity-100 transition duration-300 ease-in-out"
        >
          <span class="text-white text-xl font-semibold">{{ img.label }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'

const mouseX = ref(0)
const mouseY = ref(0)
const isMobile = ref(false)
const collage = ref(null)

const handleMouse = (e) => {
  if (isMobile.value) return
  mouseX.value = e.clientX / window.innerWidth
  mouseY.value = e.clientY / window.innerHeight
}

const transformStyle = computed(() => {
  if (isMobile.value) return {}

  const collageWidth = 200 // in vw
  const collageHeight = 200 // in vh

  const offsetX = -(collageWidth - 100) * mouseX.value
  const offsetY = -(collageHeight - 100) * mouseY.value

  return {
    transform: `translate(${offsetX}vw, ${offsetY}vh)`
  }
})

const checkMobile = () => {
  isMobile.value = window.innerWidth < 768
}

onMounted(() => {
  checkMobile()
  window.addEventListener('resize', checkMobile)
})

onUnmounted(() => {
  window.removeEventListener('resize', checkMobile)
})

// ✅ Immagini distribuite artisticamente con etichette
const images = [
  { src: '/animation.jpeg',  style: { top: '6%',   left: '4%',   width: '20vw' }, label: 'Animazione' },
  { src: '/ribs.png',        style: { top: '8%',   left: '38%',  width: '28vw' }, label: 'Ribs' },
  { src: '/pc.jpg',          style: { top: '10%',  left: '75%',  width: '38vw' }, label: 'PC' },
  { src: '/webd.jpg',        style: { top: '38%',  left: '18%',  width: '38vw' }, label: 'Web Design' },
  { src: '/14.png',          style: { top: '45%',  left: '62%',  width: '36vw' }, label: 'Packaging' },
  { src: '/waves.jpg',       style: { top: '72%',  left: '8%',   width: '35vw' }, label: 'Waves' },
  { src: '/interior.png',    style: { top: '74%',  left: '62%',  width: '30vw' }, label: 'Interior' },
]
</script>
