<script setup>
const props = defineProps({
  tag: String,
  details: String,
  picture: String
})
</script>

<template>
  <li>
    <div class="image-container">
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
  margin: 1.5rem 0 0.5rem 1rem;
  padding: 0.7rem;
  background: linear-gradient(
    86deg,
    var(--about-tag-color) 0% 97%,
    var(--about-background-color) 97.1% 100%
  );
  position: relative;
  transform: scale(0.85);
  transition: all 0.4s ease-in-out;

  display: grid;
  grid-template-areas:
    'img h3'
    'img p';
  grid-template-columns: auto 1fr;
  gap: 10px;
  align-items: center;

  opacity: 0.3;
}

li .image-container {
  grid-area: img;
}

li .tagHeading {
  grid-area: h3;
}

li .tagDetail {
  grid-area: p;
}

li:nth-of-type(even) {
  margin: 1.5rem 0 0.5rem 1rem;
  background: linear-gradient(
    -86deg,
    var(--about-tag-color) 0% 97%,
    var(--about-background-color) 97.1% 100%
  );
  position: relative;
  transform: scale(0.85);
  transition: all 0.4s ease-in-out;
  grid-template-areas:
    'h3 img'
    'p img';
  grid-template-columns: 1fr auto;
  gap: 10px;
  align-items: center;
}

li .image-container {
  height: 18vh;
  aspect-ratio: 1/1;
  margin-right: 1.25em;
  background: linear-gradient(
    -86deg,
    var(--about-background-color) 0 70%,
    var(--about-tag-color) 0% 100%
  );
  transform: rotate(-4deg);
  transition: all 0.4s ease-in-out;
  border-radius: 0.25em;
  overflow: hidden;
  margin-left: -5em;
  padding: 1em;
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

li:hover {
  transform: scale(1.05);
  box-shadow: -1.2rem 1rem 1rem 0.3rem #3a5900a7;
}

li:nth-of-type(even):hover {
  box-shadow: 1.2rem 1rem 1rem 0.3rem #3a5900a7;
}

.tagImg {
  width: 100%;
  aspect-ratio: 1/1;
  filter: grayscale(1);
  object-fit: cover;
}

.details-container {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: flex-start;
  gap: 2rem;
  padding: 1rem;
  transition: all 0.4s ease-in-out;
}

li:nth-of-type(even) .details-container {
  justify-content: start;
  align-items: flex-end;
  gap: 2rem;
}

.details-container h3 {
  color: var(--about-tag-color);
  background-color: black;
  border-radius: 0.25rem;
  padding: 0.5rem 1.5rem;
  font-size: 2.5rem;
  margin-top: -2.5rem;
  position: absolute;
  left: -1.5rem;
  transform: rotate(4deg);
  transform-origin: left bottom;
  box-shadow: -3px 3px 5px 0.5px #3a5900a7;
}

li:nth-of-type(even) h3 {
  left: auto;
  transform: rotate(-4deg);
  transform-origin: right bottom;
  box-shadow: 3px 3px 5px 0.5px #3a5900a7;
}

.details-container p {
  margin: 3rem 2rem 3rem 2rem;
  font-size: 1.5rem;
  color: black;
  line-height: 1.5;
}

@media (min-width: 1024px) {
  li:hover {
    transform: scale(1.005);
    opacity: 1;
  }

  li:hover .image-container {
    transform: rotate(0);
    padding: 0.5rem;
  }

  li:hover .tagHeading {
    transform: rotate(0);
  }
  li:hover img {
    filter: none;
  }
}
</style>
