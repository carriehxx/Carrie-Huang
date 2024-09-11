<template>
  <div class="contact">
    <div class="contactMain">
      <h2 class="contactTitle">Get In Touch</h2>
    </div>

    <div class="cardContainer" ref="cardContainer">
      <div
        v-for="(item, index) in items"
        :key="index"
        class="card"
        :style="{ background: item.background }"
      >
        <a :href="item.link" target="_blank" class="card-link">
          <i :class="item.icon">{{ item.class }}</i>
          {{ item.label }}
        </a>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const currentIdx = ref(0)
const items = [
  {
    class: 'Instagram',
    icon: 'bx bxl-instagram',
    link: 'https://www.instagram.com/carriehxx/',
    label: '@carriehxx',
    background:
      'radial-gradient(49% 81% at 45% 47%, #FFED0345 0%, #073AFF00 100%),radial-gradient(113% 91% at 17% -2%, #FF1F00FF 1%, #FF000000 99%),radial-gradient(142% 91% at 83% 7%, #FF00D6FF 1%, #FF000000 99%),radial-gradient(142% 91% at -6% 74%, #FAFF00FF 1%, #FF000000 99%),radial-gradient(142% 91% at 111% 84%, #8D00FFFF 0%, #FF0000FF 100%)'
  },
  {
    class: 'Linkedin',
    icon: 'bx bxl-linkedin',
    link: 'https://www.linkedin.com/in/carriehuangxin/',
    label: '@Xin Huang',
    background: 'linear-gradient(67deg, #0072b1 0%, #71C4FFFF 98%)'
  },
  {
    class: 'Github',
    icon: 'bx bxl-github',
    link: 'https://github.com/carriehxx',
    label: '@carriehxx',
    background: '#FFFFFFFF'
  },
  {
    class: 'Phone',
    icon: 'bx bx-phone',
    link: '#',
    label: '(+852) 95725272',
    background: 'linear-gradient(90deg, #71FF84FF 0%, #71C4FFFF 100%)'
  },
  {
    class: 'Email',
    icon: 'bx bx-envelope',
    link: 'mailto:carriehuangx02@gmail.com',
    label: 'carriehuangx02@gmail.com',
    background: 'linear-gradient(90deg, #FFA971FF 0%, #FFF971FF 100%)'
  },
  {
    class: 'Website',
    icon: 'bx bx-link',
    link: '#',
    label: 'Carrie Huang',
    background: 'linear-gradient(90deg, #A100FFFF 0%, #FFFFFFFF 100%)'
  },
  {
    class: 'Resume',
    icon: 'bx bx-file',
    link: './assets/resume/Huang_Xin_HKU_Resume.pdf',
    label: 'Check my resume',
    background:
      'radial-gradient(49% 81% at 45% 47%, #FFFFFF45 0%, #073AFF00 100%),radial-gradient(113% 91% at 17% -2%, #009EFFFF 1%, #FF000000 99%),radial-gradient(142% 91% at 83% 7%, #00FFB9FF 1%, #FF000000 99%),radial-gradient(142% 91% at -6% 74%, #00A2FFFF 1%, #FF000000 99%),radial-gradient(142% 91% at 111% 84%, #00FF03FF 0%, #FF0000FF 100%)'
  }
]

let scrollInterval

onMounted(() => {
  duplicateCards()
  pauseAutoScroll()
  startAutoScroll()
})

onUnmounted(() => {
  clearInterval(scrollInterval)
})

function duplicateCards() {
  const container = document.querySelector('.cardContainer')
  const cards = document.querySelectorAll('.card')
  cards.forEach((card) => {
    const cloneFirst = card.cloneNode(true)
    const cloneLast = card.cloneNode(true)
    container.appendChild(cloneFirst)
  })
}

function startAutoScroll() {
  const container = document.querySelector('.cardContainer')
  const cardWidth = document.querySelector('.card').offsetWidth
  console.log(cardWidth)
  let scrollAmount = 0

  scrollInterval = setInterval(() => {
    scrollAmount += cardWidth
    container.scrollTo({
      left: scrollAmount,
      behavior: 'smooth'
    })
    
    if (scrollAmount >= container.scrollWidth / 2) {
      setTimeout(() => {
        container.scrollTo({
          left: 0, 
          behavior: 'auto' 
        })
        scrollAmount = 0
      }, 500)
    }
  }, 3000)
}

function pauseAutoScroll() {
  const container = document.querySelector('.cardContainer')
  container.addEventListener('mouseover', () => {
    clearInterval(scrollInterval)
  })
  container.addEventListener('touchstart', () => {
    clearInterval(scrollInterval)
  })

  container.addEventListener('mouseout', () => {
    startAutoScroll()
  })
  container.addEventListener('touchend', () => {
    startAutoScroll()
  })
}
</script>

<style scoped>
.contact {
  max-width: 100vw;
  width: 100vw;
  height: 100vh;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  align-content: center;
  font-family: var(--section-font-family);
}

.contactMain {
  margin-bottom: 2rem;
}

.contactTitle {
  font-size: 3rem;
  color: azure;
  font-weight: bold;
}

.cardContainer {
  display: flex;
  overflow-x: scroll;
  scroll-snap-type: x mandatory;
  scroll-behavior: smooth;
  scrollbar-width: none;
  width: 100%;
  max-width: 100vw;
  height: 350px;
  position: relative;
}

.cardContainer::-webkit-scrollbar {
  display: none;
}

.card {
  display: flex;
  flex: 0 0 auto;
  min-width: 300px;
  width: 45%;
  height: 100%;
  margin-right: 15px; 
  border-radius: 15px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  align-items: center;
  justify-content: center;
  scroll-snap-align: start;
  transition: transform 0.5s ease-in-out;
}

.card-link {
  text-decoration: none;
  color: rgb(0, 0, 0);
  display: flex;
  flex-direction: column;
  align-content: center;
  justify-content: center;
  font-size: 1.5rem;
  width: 100%;
  height: 85%;
  transition: all 0.3s ease-in-out;
}

.card-link:hover {
  font-size: 1.8rem;
}

.card-link i {
  font-size: 2rem;
  margin-bottom: 2rem;
}

@media (min-width: 1024px) {
  .cardContainer {
    width: 50%;
    left: 50%;
    transform: translate(-50%);
  }
}
</style>
