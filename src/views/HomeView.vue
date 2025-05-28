<script setup>
import {useRouter} from 'vue-router'
import About from '../components/theAbout.vue'
import Experience from '../components/theExperience.vue'
import Contact from '../components/theContact.vue'
import theWelcome from '../components/theWelcome.vue'
import navigatorBar from '../components/navigatorBar.vue'
</script>

<template>
  <main>
    <navigatorBar />
    <theWelcome id="home" />
    <About id = 'about'/>
    <Experience id = 'experience'/>
    <Contact id = 'contact'/>
  </main>
</template>
