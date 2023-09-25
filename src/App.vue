<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Presentation from './components/Presentation.vue';
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <Presentation/>
</template>

<style scoped>
header {
  line-height: 1.5;
}

@media (min-width: 1920px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }
}
</style>
