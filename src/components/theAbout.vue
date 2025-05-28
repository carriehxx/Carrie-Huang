<script setup>
// import infoTag from '../components/infoTag.vue'
var selfIntro = document.querySelectorAll(".intro");
selfIntro.forEach((item) => {
    item.style.padding = `0 0 0 ${Math.random() * 55}rem`;
});
</script>

<template>
  <div class="about" id="about">
    <h2 class="aboutMe">About ME</h2>
    <p class="intro">I am a graduate from the University of Hong Kong</p>
    <p class="intro">My major is Mathematics & Computer Science</p>
    <p class="intro">I am a first-class honor graduate.</p>
    <p class="intro">My skill set includes: Python, SQL, HTML, CSS, JavaScript, Tableau, MatLab, C++</p>
    <p class="intro">My interest: Baking, Badminton, Going to gym</p>
    <p class="intro">My favourite musical: 'Alexander Hamilton', 'Chicago'</p>
    <p class="intro">I am proficient in English, Mandarin and Cantonese</p>
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
  font-size: 5rem;
  font-weight: 400;
  color: var(--section-font-color);
}

.intro {
  font-size: 2rem;
  animation: '2s ease-in-out infinite alternate slidein';
  /* padding-left: 20vw; */
}

@media (min-width: 1024px){
  .about {
    padding: 7rem 4rem;
  }
}

</style>
