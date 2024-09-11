<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
const props = defineProps({
  tag: String,
  details: String,
  picture: String
})

const windowWidth = ref(window.innerWidth)

const handleResize = () => {
  windowWidth.value = window.innerWidth
}

onMounted(() => {
  window.addEventListener('resize', handleResize)
})

onUnmounted(() => {
  window.removeEventListener('resize', handleResize)
})
</script>

<template>
  <li>
    <div class="image-container" v-if="windowWidth >= 1024">
      <img :src="picture" alt="tag-picture" class="tagImg" />
    </div>
    <div class="details-container">
      <h3 class="tagHeading">{{ tag }}</h3>
      <p v-html="details" class="tagDetail"></p>
    </div>
  </li>
</template>

<style scoped>
li {
  width: 80%;
  margin: 3rem;
  padding: 0.7rem;
  background: linear-gradient(
    86deg,
    var(--about-tag-color) 0% 97%,
    var(--about-background-color) 97.1% 100%
  );
  position: relative;
  transition: all 0.4s ease-in-out;
  display: flex;
  flex-direction: column;
  opacity: 0.3;
}

li:nth-of-type(even) {
  background: linear-gradient(
    -86deg,
    var(--about-tag-color) 0% 97%,
    var(--about-background-color) 97.1% 100%
  );
}

li:hover {
  transform: scale(1.05);
  box-shadow: -1.2rem 1rem 1rem 0.3rem #7489ff53;
  opacity: 1;
}

li:nth-of-type(even):hover {
  box-shadow: 1.2rem 1rem 1rem 0.3rem #7489ff53;
}

.details-container h3 {
  color: var(--about-tag-color);
  background-color: black;
  border-radius: 0.25rem;
  padding: 0.5rem 1.5rem;
  font-size: 2rem;
  margin-top: -2.5rem;
  position: absolute;
  left: -0.5rem;
  transform: rotate(4deg);
  box-shadow: -3px 3px 5px 0.5px #1994ffa7;
}

li:nth-of-type(even) h3 {
  left: auto;
  right: -0.5rem;
  transform: rotate(-4deg);
}

.details-container p {
  margin: 3rem 2rem 3rem 2rem;
  font-size: 1rem;
  color: black;
  line-height: 1.5;
}

li:hover .tagHeading {
  transform: rotate(0);
}

@media (min-width: 1024px) {
  li {
    width: 80%;
    margin: 1.5rem 0 0.5rem 1rem;
    padding: 0.7rem;
    transform: scale(0.85);
    display: grid;
    grid-template-areas:
      'img h3'
      'img p';
    grid-template-columns: auto 1fr;
    gap: 10px;
    align-items: center;
    opacity: 0.3;
  }

  li:nth-of-type(even) {
    grid-template-areas:
      'h3 img'
      'p img';
    grid-template-columns: 1fr auto;
  }

  .image-container {
    grid-area: img;
    height: 18vh;
    aspect-ratio: 1/1;
    margin-right: 1.25em;
    background: linear-gradient(
      -86deg,
      var(--about-background-color) 0 70%,
      var(--about-tag-color) 0% 100%
    );
    transform: rotate(-4deg);
    border-radius: 0.25em;
    overflow: hidden;
    padding: 1em;
    margin-left: -5rem;
  }

  li:nth-of-type(even) .image-container {
    background: linear-gradient(
      86deg,
      var(--about-background-color) 0 70%,
      var(--about-tag-color) 0% 100%
    );
    transform: rotate(4deg);
    margin-right: -5em;
    margin-left: auto;
  }

  .tagImg {
    width: 100%;
    aspect-ratio: 1/1;
    filter: grayscale(1);
    object-fit: cover;
  }

  .details-container {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 1rem;
  }

  li:nth-of-type(even) .details-container {
    align-items: flex-end;
  }

  li:hover .image-container {
    transform: rotate(0);
  }

  li:hover img {
    filter: none;
  }
}
</style>
