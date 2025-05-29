<script setup>
import { onMounted } from 'vue';

onMounted(()=>{
  if (window.innerWidth > 1024) {
    var selfIntro = document.querySelectorAll(".intro");
    selfIntro.forEach((item) => {
        item.style.padding = '0 0 0 calc('+Math.random()+'* 10vw';
        item.style.setProperty('font-size','2rem')
        item.style.setProperty('animation-delay', Math.random()*3+'s')
    });
  }
})
</script>

<template>
  <div class="about" id="about">
    <h2 class="aboutMe">About ME</h2>
    <p class="intro">I am a graduate from <strong>the University of Hong Kong</strong> </p>
    <p class="intro">My major is <strong>Mathematics and Computer Science</strong></p>
    <p class="intro">I am a <strong>first-class honor</strong> graduate.</p>
    <p class="intro">My skill set includes: <strong>Python, SQL, HTML, CSS, JavaScript, Tableau, MatLab, C++</strong></p>
    <p class="intro">My interest: <strong>Baking, Badminton, Going to gym</strong></p>
    <p class="intro">My favourite musical: <strong>'Alexander Hamilton', 'Chicago'</strong></p>
    <p class="intro">I am proficient in <strong>English, Mandarin and Cantonese</strong></p>
  </div>
</template>

<style scoped>
.about {
  background-color: var(--section-background-color);
  display: flex;
  flex-direction: column;
  align-content: center;
  justify-content: space-around;
  /* gap: 2rem; */
  height: auto;
  width: 100vw;
  height: 100vh;
  font-family: var(--section-font-family);
  padding: 7rem 2rem;
  color: var(--section-font-color);
}

h2 {
  font-size: 4rem;
  font-weight: 400;
  color: var(--section-font-color);
}

.intro {
  font-size: 1rem;
  animation: float 10s ease-in-out infinite reverse;
  text-align: center;
}

.intro::before {
      content: '';
      position: absolute;
      /* top: 0; */
      left: 0;
      bottom: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent,rgba(202, 255, 231, 0.1), rgba(205, 255, 232, 0.511), rgba(202, 255, 231, 0.1), transparent);
      z-index: -1;
      opacity: 0.7;
    }

.intro strong {
  color: rgb(190, 255, 153);
  font-weight: 600;
}


@keyframes float {
  0%, 100% {
    transform: translateY(0) translateX(0);
  }
  25% {
    transform: translateY(-1rem) translateX(5rem);
  }
  50% {
    transform: translateY(-0.6rem) translateX(3rem);
  }
  75% {
    transform: translateY(0.3rem) translateX(-3rem);
  }
}


@media (min-width: 1024px){
  .about {
    padding: 7rem 4rem;
  }
}

</style>
