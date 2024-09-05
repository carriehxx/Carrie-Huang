<script setup>
import { onMounted, ref } from 'vue'

const items = [
  {
    class: 'instagram',
    icon: 'bx bxl-instagram',
    link: 'https://www.instagram.com/carriehxx/',
    label: '@carriehxx'
  },
  {
    class: 'linkedin',
    icon: 'bx bxl-linkedin',
    link: 'https://www.linkedin.com/in/carriehuangxin/',
    label: '@Xin Huang'
  },
  {
    class: 'github',
    icon: 'bx bxl-github',
    link: 'https://github.com/carriehxx',
    label: '@carriehxx'
  },
  { class: 'phone', icon: 'bx bx-phone', link: '#', label: '(+852) 95725272' },
  {
    class: 'email',
    icon: 'bx bx-envelope',
    link: 'mailto:carriehuangx02@gmail.com',
    label: 'carriehuangx02@gmail.com'
  },
  { class: 'website', icon: 'bx bx-link', link: '#', label: 'Carrie Huang' },
  {
    class: 'resume',
    icon: 'bx bx-file',
    link: '../assets/resume/Huang_Xin_HKU_Resume.pdf',
    label: 'Check my resume'
  }
]

const contactHover = ref([]) // This will hold all list item elements
const contactBackground = ref(null)

onMounted(() => {
  // Attach event listeners to each item in the list after mounting
  contactHover.value.forEach((item) => {
    item.addEventListener('mouseover', () => {
      // Change background color of the hovered item
      item.style.backgroundColor = 'rgb(255, 255, 255, 0.2)'

      // Change the position of the 'contactTitle'
      contactBackground.value.querySelector('.contactTitle').style.top = '20%'

      // Dynamically change the image based on the second class of the item
      const imgClass = item.classList[1]
      contactBackground.value.querySelector('.contactPic').src = `../assets/${imgClass}.jpg`
    })

    item.addEventListener('mouseout', () => {
      // Reset background color
      item.style.backgroundColor = ''

      // Reset the position of the 'contactTitle'
      contactBackground.value.querySelector('.contactTitle').style.top = '50%'

      // Reset the image to the default
      contactBackground.value.querySelector('.contactPic').src = '../assets/contactBack.jpg'
    })
  })
})
</script>

<template>
  <div class="contact">
    <div ref="contactBackground" class="contactMain">
      <h2 class="contactTitle">Contact</h2>
      <img class="contactPic" src="../assets/contactBack.jpg" alt="contactImg" />
    </div>

    <ul class="contactInfo">
      <li v-for="(item, index) in items" :key="index" ref="contactHover" :class="item.class">
        <i :class="item.icon"></i>
        <a :href="item.link" target="_blank" :class="item.class">{{ item.label }}</a>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.contact {
  height: 100vh;
  width: 100vw;
  font-family: var(--section-font-family);
  padding: 7rem 4rem;
  display: flex;
  flex-direction: row;
}

.contactMain {
  width: 50vw;
  position: relative;
}

.contactMain h2 {
  font-size: 4rem;
  font-weight: 400;
  color: rgb(238, 237, 237);
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.contactMain img {
  position: absolute;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -1;
  filter: brightness(0.6);
  top: 0;
  border-radius: 20px;
  transition: all 0.3s ease-in-out;
}

.contactInfo {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  color: rgb(0, 0, 0);
  width: 45vw;
  height: 100%;
  justify-content: center;
}

h2 {
  font-size: 4rem;
  font-weight: 400;
  color: rgb(0, 0, 0);
}

p {
  font-size: 2rem;
}

ul {
  list-style: none;
  font-size: 2rem;
}

.contactItem {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1rem;
  cursor: pointer;
}

i {
  font-size: 2.5rem;
  color: rgb(0, 0, 0);
}

a {
  text-decoration: none;
  color: rgb(173, 173, 0);
  font-weight: 500;
}
</style>
