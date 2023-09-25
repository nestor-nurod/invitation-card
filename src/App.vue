<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Location from './components/Location.vue';
import Presentation from './components/Presentation.vue';
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <audio autoplay>
  <source src="/audio/Legendarios.mp3" type="audio/mpeg">
</audio>
  <Presentation/>
  <Location/>
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
