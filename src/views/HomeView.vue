<script setup>
import {useRouter} from 'vue-router'
import Education from '../components/theEducation.vue'
import Experience from '../components/theExperience.vue'
import Contact from '../components/theContact.vue'
import theWelcome from '../components/theWelcome.vue'
import navigatorBar from '../components/navigatorBar.vue'
</script>

<template>
  <main>
    <navigatorBar />
    <theWelcome id="home" />
    <Education id="education" />
    <Experience id="experience" />
    <Contact id="contact" />
  </main>
</template>
