<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref, onMounted, onUnmounted, computed } from 'vue'

// 定义菜单切换状态
const menuToggle = ref(false)
// 定义窗口宽度
const windowWidth = ref(window.innerWidth)
// 定义导航栏
const navbar = ref(null)

// 计算是否为移动设备
const isMobile = computed(() => windowWidth.value < 1024)

// 监听窗口大小变化
function handleResize() {
  windowWidth.value = window.innerWidth
}

// 监听页面滚动
function handleScroll() {
  if (navbar.value && !isMobile.value) {
    const scrollTop = window.scrollY
    const opacity = 1 - scrollTop / window.innerHeight
    navbar.value.style.display = opacity < 0.4 ? 'flex' : 'none'
  }
}

// 组件挂载时添加监听事件
onMounted(() => {
  window.addEventListener('resize', handleResize)
  window.addEventListener('scroll', handleScroll)
})

// 组件卸载时移除监听事件
onUnmounted(() => {
  window.removeEventListener('resize', handleResize)
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <div class="navbar" ref="navbar">
    <!-- 移动设备时显示菜单按钮 -->
    <div v-show="isMobile" @click="menuToggle = !menuToggle" class="menu">
      <i class="bx bx-menu"></i>
    </div>
    <!-- 非移动设备或菜单按钮被点击时显示导航栏 -->
    <nav v-show="!isMobile || menuToggle">
      <RouterLink to="/">HOME</RouterLink>
      <RouterLink to="/about">ABOUT</RouterLink>
      <RouterLink to="/experience">EXPERIENCE</RouterLink>
      <RouterLink to="/contact">CONTACT</RouterLink>
    </nav>
  </div>

  <RouterView />
</template>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  padding: 0.5rem 1.5rem;
  z-index: 1000;
  transition: all 0.3s;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}

.menu i {
  color: rgba(255, 255, 255, 0.955);
  font-size: 3rem;
}

nav {
  width: 100%;
  text-align: center;
  justify-content: center;
  font-family: var(--header-font-family);
  font-size: 2rem;
  transition: all 0.3s;

  display: flex;
  flex-direction: column;
  background-color: hsla(69, 32%, 92%, 0.9);
  padding: 0.5rem 1.5rem;
  gap: 1.7rem;
  border-radius: 10px;
}

nav a {
  font-weight: 1000;
  text-decoration: none;
  color: rgb(136, 152, 103);
}

nav a.router-link-exact-active {
  color: rgb(40, 100, 12);
}

nav a:hover {
  color: rgb(40, 100, 12);
  transform: scale(1.05);
}
@media (min-width: 1024px) {
  .navbar {
    display: none;
    align-items: center;
    justify-content: right;
    background-color: hsla(72, 76%, 90%, 0.815);
  }

  nav {
    justify-content: right;
    text-shadow: rgba(201, 201, 201, 0.418) 0 0 5px;
    margin-left: -1rem;
    flex-direction: row;
    background-color: transparent;
    padding: 0.6rem 0;
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
    font-size: 1.5rem;
  }

  nav a:first-of-type {
    border: 0;
  }
}
</style>
