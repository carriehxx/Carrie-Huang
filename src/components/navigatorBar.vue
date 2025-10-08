<template>
<main class="navbar" ref="navbar">
  <div>
    <div v-show="isMobile" @click="menuToggle = !menuToggle" class="menu">
      <i class="bx bx-menu" v-if="!menuToggle"></i>
      <i class="bx bx-x" v-else></i>
    </div>
    <nav v-if="!isMobile || menuToggle" class="menuContent">
      <a href="#" @click.prevent="scrollToSection('#home')">Home</a>
      <a href="#" @click.prevent="scrollToSection('#education')">Education</a>
      <a href="#" @click.prevent="scrollToSection('#experience')">Experience</a>
      <a href="#" @click.prevent="scrollToSection('#contact')">Contact</a>
    </nav>
  </div>
</main>
</template>

<script setup>
import { useRouter } from 'vue-router'
import { ref, onMounted, onUnmounted, computed, watch } from 'vue'

const menuToggle = ref(false)
const windowWidth = ref(window.innerWidth)
const navbar = ref(null)
const isMobile = computed(() => windowWidth.value < 1024)
const router = useRouter()

function scrollToSection(sectionid) {
  menuToggle.value = false
  // router.push({path: '/', hash: sectionid })
  window.location.hash = sectionid;
  // console.log(sectionid)
  const element = document.querySelector(sectionid)
  if (element) {
    // 添加容错机制
    setTimeout(() => {
      element.scrollIntoView({ 
        behavior: 'smooth',
        block: 'start' 
      });
    }, 50);
  }
}

function handleResize() {
  windowWidth.value = window.innerWidth
}

function handleScroll() {
  if (!navbar.value || isMobile.value) return;
  
  const scrollTop = window.scrollY;
  navbar.value.style.display = 'flex'; 
  
  const opacity = 1 - Math.min(scrollTop / 200, 0.6);
  navbar.value.style.background = `rgba(var(--nav-background), ${opacity})`;
}

// handle background opecity when menu toggle
function menubackground() {
  if (window.innerWidth < 1024 && menuToggle.value) {
    const navigatorBackground = document.querySelector('.navbar')
    navigatorBackground.style.background = 'rgba(0, 0, 0, 0.445)';
    navigatorBackground.style.backdropFilter = 'blur(2px)';
  }
}

watch(menuToggle, (newVal) => {
  if (newVal) {
    document.body.classList.add('no-scroll') 
    menubackground()
  } else {
    document.body.classList.remove('no-scroll')
  }
})

onMounted(() => {
  window.addEventListener('resize', handleResize)
  window.addEventListener('scroll', handleScroll)
  if (window.location.hash) {
    const target = document.querySelector(window.location.hash);
    target?.scrollIntoView();
  }
})

onUnmounted(() => {
  window.removeEventListener('resize', handleResize)
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
.no-scroll {
  overflow: hidden;
}

.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  display: flex;
  flex-direction: column;
  align-items: start;
  padding: 1rem 1rem;
}

.menu i {
  color: rgba(255, 255, 255, 0.955);
  font-size: 3rem;
  transition: all 0.3s ease-in-out;
  width: 100vw;
}

nav {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-family: var(--section-font-family);
  font-size: 2rem;
  /* padding: 1.5rem; */
  gap: 1.7rem;
  border-radius: 10px;
  opacity: 1;
  transition: all 0.4s ease-in-out;
}

nav a {
  font-weight: 1000;
  text-decoration: none;
  color: rgb(255, 255, 255);
}

nav a.router-link-exact-active {
  color: var(--accent-color);
}

nav a:hover {
  color: var(--accent-color);
  transform: scale(1.05);
}

nav.v-enter-active,
nav.v-leave-active {
  transition:
    opacity 0.4s ease,
    transform 0.4s ease;
}

nav.v-enter-from,
nav.v-leave-to {
  opacity: 0;
  transform: translateY(-20px);
}

@media (min-width: 1024px) {
  .navbar {
    display: flex;
    align-items: center;
    justify-content: right;
    background-color: var(--nav-background);
    height: auto;
    padding: 0.5rem 1.5rem;
  }

  nav {
    justify-content: right;
    text-shadow: rgba(201, 201, 201, 0.418) 0 0 5px;
    margin-left: -1rem;
    flex-direction: row;
    background-color: transparent;
    padding: 0.6rem 0;
    height: auto;
  }

  nav a.router-link-exact-active {
    font-weight: 700;
  }

  nav a.router-link-exact-active:hover {
    background-color: transparent;
  }

  nav a {
    display: inline-block;
    padding: 0 2rem;
    border-left: 2px solid;
    font-weight: 700;
    font-size: 2rem;
  }

  nav a:first-of-type {
    border: 0;
  }
}
</style>