<template>
  <header :class="{ toggle: menuOpen }">
    <div class="user">
      <img :src="profileImg" alt="林意翔" />
      <h3 class="name">林意翔</h3>
      <p class="post">java engineer</p>
    </div>

    <nav class="navbar">
      <ul>
        <li><a href="#home" @click="closeMenu">home</a></li>
        <li><a href="#skill" @click="closeMenu">skill</a></li>
        <li><a href="#experience" @click="closeMenu">work experience</a></li>
      </ul>
    </nav>
  </header>

  <div id="menu" class="fas fa-bars" :class="{ 'fa-times': menuOpen }" @click="toggleMenu"></div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import profileImg from '../assets/個人照.jpg'

const menuOpen = ref(false)

function toggleMenu() {
  menuOpen.value = !menuOpen.value
}

function closeMenu() {
  menuOpen.value = false
}

function onScroll() {
  menuOpen.value = false
}

onMounted(() => {
  window.addEventListener('scroll', onScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', onScroll)
})
</script>
