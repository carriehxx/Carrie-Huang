<script setup>
import infoTag from '../components/infoTag.vue'
</script>

<template>
  <div class="about" id="about">
    <h2 class="aboutMe">About ME</h2>
    <p class="intro">I am a recent graduate from the University of Hong Kong, majoring in Mathmatics and Computer Science. </p>
    
  </div>
</template>

<style scoped>
.about {
  background-color: var(--section-background-color);
  display: flex;
  flex-direction: column;
  gap: 2rem;
  height: auto;
  width: 100vw;
  font-family: var(--section-font-family);
  padding: 7rem 2rem;
  color: var(--section-font-color);
}

h2 {
  font-size: 2rem;
  font-weight: 400;
  color: var(--section-font-color);
}

p {
  font-size: 1.5rem;
}

.personalInfo {
  width: 100%;
  padding-left: 0;
}

@media (min-width: 1024px){
  .about {
    padding: 7rem 4rem;
  }
}

</style>
