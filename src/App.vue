<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref, onMounted, onUnmounted, computed, watch } from 'vue'

const menuToggle = ref(false)
const windowWidth = ref(window.innerWidth)
const navbar = ref(null)

const isMobile = computed(() => windowWidth.value < 1024)

function handleResize() {
  windowWidth.value = window.innerWidth
}

function handleScroll() {
  if (navbar.value && !isMobile.value) {
    const scrollTop = window.scrollY
    const opacity = 1 - scrollTop / window.innerHeight
    navbar.value.style.display = opacity < 0.4 ? 'flex' : 'none'
  }
}

watch(menuToggle, (newVal) => {
  if (newVal) {
    document.body.classList.add('no-scroll') // 禁用滚动
  } else {
    document.body.classList.remove('no-scroll') // 恢复滚动
  }
})

onMounted(() => {
  window.addEventListener('resize', handleResize)
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('resize', handleResize)
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <div class="navbar" ref="navbar">
    <!-- 移动设备时显示菜单按钮 -->
    <div v-show="isMobile" @click="menuToggle = !menuToggle" class="menu">
      <i class="bx bx-menu" v-if="!menuToggle"></i>
      <i class="bx bx-x" v-else></i>
    </div>
    <!-- 非移动设备或菜单按钮被点击时显示导航栏 -->
    <nav v-if="!isMobile || menuToggle" class="menuContent">
      <RouterLink to="/" @click="menuToggle = false">HOME</RouterLink>
      <RouterLink to="/about" @click="menuToggle = false">ABOUT</RouterLink>
      <RouterLink to="/experience" @click="menuToggle = false">EXPERIENCE</RouterLink>
      <RouterLink to="/contact" @click="menuToggle = false">CONTACT</RouterLink>
    </nav>
  </div>

  <RouterView />
</template>

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
  align-items: flex-end;
}

.menu i {
  color: rgba(255, 255, 255, 0.955);
  font-size: 3rem;
  transition: all 0.3s ease-in-out;
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
  background: var(--nav-background);
  padding: 1.5rem;
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
  color: rgb(237, 255, 146);
}

nav a:hover {
  color: rgb(222, 250, 208);
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
    display: none;
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
