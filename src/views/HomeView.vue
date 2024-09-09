<script setup>
import About from '../components/theAbout.vue'
import Experience from '../components/theExperience.vue'
import Contact from '../components/theContact.vue'
import theWelcome from '../components/theWelcome.vue'
</script>

<template>
  <main>
    <theWelcome id="home" />

    <section id="about">
      <About />
    </section>

    <section id="experience">
      <Experience />
    </section>

    <section id="contact">
      <Contact />
    </section>
  </main>
</template>
