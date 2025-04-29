<script setup>
import { onMounted, ref } from 'vue'
import gsap from 'gsap'

const particleCount = 100
const particles = ref([])

onMounted(() => {
  particles.value.forEach((el) => {
    if (!el) return
    gsap.set(el, {
      width: Math.random() * 3 + 1,
      height: Math.random() * 3 + 1,
      opacity: Math.random(),
      left: Math.random() * window.innerWidth,
      top: Math.random() * window.innerHeight,
    })

    gsap.to(el, {
      y: window.innerHeight,
      duration: Math.random() * 10 + 10,
      opacity: 0,
      repeat: -1,
      ease: 'none',
    })
  })
})
</script>

<template>
  <div class="fixed inset-0 z-0 pointer-events-none">
    <div
      v-for="(_, i) in particleCount"
      :key="i"
      ref="particles"
      class="absolute rounded-full bg-white"
    />
  </div>
</template>
