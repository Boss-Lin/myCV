<template>
  <section class="skill" id="skill">
    <h1 class="heading">my <span>skill</span></h1>

    <div class="row">
      <div class="counter">
        <div v-for="group in skillGroups" :key="group.category" class="box">
          <span>{{ group.category }}</span>
          <h3 v-for="item in group.items" :key="item">{{ item }}</h3>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const skillGroups = [
  {
    category: 'programming language',
    items: ['Java', 'PHP', 'HTML', 'CSS', 'JavaScript'],
  },
  {
    category: 'database',
    items: ['Oracle', 'MySQL', 'PostgreSQL', 'MS SQL'],
  },
  {
    category: 'framework',
    items: ['spring boot', 'Struts', 'Servlet', 'Tapestry', 'Laravel'],
  },
  {
    category: 'other tools',
    items: ['docker', 'rabbitmq'],
  },
]
</script>
