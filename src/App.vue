<script setup>
import DressCode from './components/DressCode.vue';
import Location from './components/Location.vue';
import WishList from './components/WishList.vue';
import WelcomeMessage from './components/WelcomeMessage.vue';
import SendVideo from './components/SendVideo.vue';
import FrontPage from './components/FrontPage.vue';
import Invitation from './components/Invitation.vue'
</script>

<template>
  <WelcomeMessage/>
  <Invitation/>
  <FrontPage/>
  <Location />
  <DressCode/>
  <SendVideo/>
  <WishList/>  
  
</template>

<style scoped>
header {
  line-height: 1.5;
}

.background-music{
  position: fixed;
  bottom: 20px;
  right: 20px; 
  z-index: 999; 
}

@media (min-width: 1920px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }
}
</style>
