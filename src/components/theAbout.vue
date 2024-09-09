<script setup>
import infoTag from '../components/infoTag.vue'
</script>

<template>
  <div class="about">
    <h2 class="aboutMe">About ME</h2>
    <p class="intro">I am a ...</p>
    <ul class="personalInfo">
      <infoTag
        :tag="'HKUer'"
        :details="'I am going to be a Year 4 undergraduate at <a href=\'https://www.hku.hk/\' target=\'_blank\'>the University of Hong Kong</a>. My first major is Mathematics, and second major is Computer Sciences. I enjoy solving problems and learning new things!'"
        :picture="'/src/assets/hku.webp'"
      />
      <infoTag
        :tag="'Life Experiencer'"
        :details="'Apart from studying, I have many hobbies and interests including doing sports, baking and writing! I love playing badminton, frisbee, going hiking, making bread and cakes!!'"
        :picture="'/src/assets/lifeExperiencer.png'"
      />
      <infoTag
        :tag="'Explorer'"
        :details="'I love trying novel things. This summer I had a research internship in Canada, learning and researching on things that I had never got in touch with before.'"
        :picture="'/src/assets/explorer.webp'"
      />
      <infoTag
        :tag="'Learner'"
        :details="'Currently I am learning tools on frontend development, and I am also interested in learning more on Deep Learning and Artificial Intelligence.'"
        :picture="'/src/assets/learner.jpg'"
      />
    </ul>
  </div>
</template>

<style scoped>
.about {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  height: auto;
  width: 100vw;
  font-family: var(--section-font-family);
  padding: 7rem 4rem;
  color: var(--section-font-color);
}

h2 {
  font-size: 4rem;
  font-weight: 400;
  color: var(--section-font-color);
}

p {
  font-size: 2rem;
}

.personalInfo {
  width: 100%;
}
</style>
