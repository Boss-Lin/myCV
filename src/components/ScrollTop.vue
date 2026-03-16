<template>
  <a href="#home" class="top" :style="{ display: showTop ? 'block' : 'none' }">
    <img :src="scrollTopImg" alt="" />
  </a>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import scrollTopImg from '../assets/scroll-top-img.png'

const showTop = ref(false)

function onScroll() {
  showTop.value = window.scrollY > 0
}

onMounted(() => {
  window.addEventListener('scroll', onScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', onScroll)
})
</script>
