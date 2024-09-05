<script setup>
import About from '../components/theAbout.vue'
import Experience from '../components/theExperience.vue'
import Contact from '../components/theContact.vue'
import theWelcome from '../components/theWelcome.vue'
</script>

<template>
  <main>
    <theWelcome />

    <section>
      <About />
    </section>

    <section>
      <Experience />
    </section>

    <section>
      <Contact />
    </section>
  </main>
</template>
