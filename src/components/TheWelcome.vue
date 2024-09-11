<script setup>
import photoAlbum from '../components/photoAlbum.vue'

window.addEventListener('scroll', () => {
  const header = document.querySelector('header')
  // header.classList.toggle('sticky', window.scrollY > 0)

  // 获取滚动高度
  const scrollTop = window.scrollY
  // adjusting the image opacity according to the scrolled distance
  const opacity = 1 - scrollTop / window.innerHeight
  header.style.opacity = Math.max(opacity, 0)
})
</script>

<template>
  <header>
    <photoAlbum />

    <div class="greeting">
      <h1>Hi, welcome to my profolio!</h1>
      <p>I'm <span>Carrie Huang</span>, nice to meet you ~</p>
    </div>
  </header>
</template>

<style scoped>
header {
  position: relative;
  display: flex;
  flex-direction: column;
  height: 100vh;
  align-items: left;
  justify-content: center;
  gap: 3rem;
}

.greeting {
  text-align: left;
  font-size: 2rem;
  color: white;
  font-weight: 600;
  display: flex;
  flex-direction: column;
  gap: 2rem;

  font-family: var(--header-font-family);
  font-weight: 1200;
  text-shadow: rgb(255, 255, 242) 0 0 8px;
}

.greeting span {
  color: rgb(206, 250, 180);
}

@media (min-width: 1024px) {
  header {
    display: flex;
    flex-direction: column;
    width: 100vw;
    place-items: center;
    height: 100vh;
    position: relative;
  }

  .greeting::after {
    content: '';
    width: 150px;
    height: 150px;
    position: absolute;
    background-image: url('./assets/chevrons-down-regular-48.png');
    background-size: cover;
    background-repeat: no-repeat;
    bottom: 10%;
    left: 50%;
    opacity: 0.7;
    color: white;
    animation: bounce 2s infinite;
  }

  @keyframes bounce {
    0%,
    20%,
    50%,
    80%,
    100% {
      transform: translate(-50%, 0);
    }
    40% {
      transform: translate(-50%, -30px);
    }
    60% {
      transform: translate(-50%, -15px);
    }
  }

  .greeting {
    padding: 0 1rem;
    text-align: left;
    font-size: 3.5rem;
  }

  .greeting p {
    font-size: 3rem;
    overflow: hidden;
    white-space: nowrap;
    padding: 0 2rem;
    margin: 0 auto;
    opacity: 0;
    animation:
      typingp 3.5s steps(40, end),
      blink-caret 0.75s step-end infinite;
    animation-delay: 3.5s;
    animation-fill-mode: forwards;
  }

  /* creating a typewriter effect for the greetings */

  .greeting h1 {
    overflow: hidden;
    white-space: nowrap;
    padding: 0 2rem;
    margin: 0 auto;
    animation:
      typingh1 3.5s steps(40, end),
      blink-caret 0.75s step-end infinite;
  }

  @keyframes typingh1 {
    0% {
      width: 0%;
    }
    1% {
      border-right: 8px solid yellow;
    }
    99.9% {
      width: 100%;
      border-right: 8px solid yellow;
    }
    100% {
      border: none;
    }
  }

  @keyframes typingp {
    0% {
      width: 0%;
      opacity: 1;
    }
    1% {
      border-right: 8px solid yellow;
    }
    100% {
      width: 65%;
      opacity: 1;
      border-right: 8px solid yellow;
    }
  }

  @keyframes blink-caret {
    from,
    to {
      border-color: transparent;
    }
    50% {
      border-color: yellow;
    }
  }
}
</style>
