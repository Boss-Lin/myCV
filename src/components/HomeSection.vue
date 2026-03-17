<template>
  <section class="home" id="home">
    <h3>HELLO THERE !</h3>
    <h1>I'M <span>林意翔</span></h1>
    <p>I have almost 4 years of work experience.</p>
    <p>Let me quickly introduce.</p>
    <div class="home-buttons">
      <a href="#skill">
        <button class="btn">my skill <i class="fas fa-user"></i></button>
      </a>
      <button class="btn" @click="downloadCV">
        download CV <i class="fas fa-download"></i>
      </button>
    </div>
  </section>
</template>

<script setup>
function downloadCV() {
  window.print()
}
</script>
