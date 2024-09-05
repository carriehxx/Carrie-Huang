<template>
  <div class="experience">
    <h2>My Experience</h2>
    <ul class="timeline">
      <li class="experienceBlock">
        <time datetime="2024-08">Aug 2024</time>
        <span>Beyond The Pivot</span> - Saga Volunteer (Department of IT)
      </li>
      <li class="experienceBlock">
        <time datetime="2024-06">Jun 2024 - Aug 2024</time>
        <span>University of Alberta</span> -Research Intern (Department of Mathematical and
        Statistical Science)
      </li>
      <li class="experienceBlock">
        <time datetime="2023-9">Sept 2023 - Dec 2023</time>
        <span>The University of Hong Kong</span> - Student Teaching Assistant (Department of
        Mathematics)
      </li>
      <li class="experienceBlock">
        <time datetime="2021-09 - 2023-06">Sept 2021 - June 2023</time>
        <span>The University of Hong Kong</span> - Cambridge-HKU Joint Education Track (Faculty of
        Science)
      </li>
    </ul>
  </div>
</template>

<style scoped>
.experience {
  font-family: var(--section-font-family);
  padding: 7rem 4rem;
  width: 100vw;
}

ul {
  display: grid;
}

li {
  list-style: none;
}

@media (min-width: 1024px) {
  h2 {
    font-size: 4rem;
    text-align: left;
    margin-bottom: 3rem;
  }

  ul {
    grid-template-columns: repeat(3, 350px);
    justify-content: center;
    background: linear-gradient(
      90deg,
      var(--experience-tag-color1) 0 50%,
      var(--experience-tag-color2) 50% 100%
    );

    border-radius: 20px;
  }

  li {
    grid-column: span 2;
    text-align: center;
    color: var(--experience-font-color);
    border: 20px solid #0000;
    background:
      linear-gradient(var(--experience-content-background) 0 0) content-box,
      linear-gradient(var(--experience-tag-color1) 0 0) padding-box,
      linear-gradient(90deg, #0000 0% 70%, var(--experience-divider-color) 70% 100%) border-box;
    line-height: 1.5;
    font-size: 2rem;
    border-radius: 60px;
    padding: 20px;

    position: relative;
  }

  li:nth-of-type(even) {
    grid-column-end: -1;
    background:
      linear-gradient(var(--experience-content-background) 0 0) content-box,
      linear-gradient(var(--experience-tag-color2) 0 0) padding-box,
      linear-gradient(90deg, var(--experience-divider-color) 0 30%, #0000 30% 100%) border-box;
  }

  li:not(:first-child) {
    margin-top: -20px;
  }

  span {
    font-weight: bold;
  }

  time {
    position: absolute;
    right: calc(100% + 50px);
    top: 50%;
    width: 70%;
    text-align: right;
    color: var(--experience-content-background);
  }

  li:nth-of-type(odd) time {
    position: absolute;
    right: auto;
    left: calc(100% + 50px);
    text-align: left;
  }

  time:before {
    content: '';
    position: absolute;
    height: 10px;
    top: calc(50% - 5px);
    right: calc(100% + 5px);
    width: 65px;
    background: repeating-linear-gradient(-90deg, var(--experience-tag-color1) 0 5px, #0000 0 10px)
      50%/100% 2px no-repeat;
  }

  li:nth-of-type(even) time:before {
    position: absolute;
    right: auto;
    left: calc(100% + 5px);
    background: repeating-linear-gradient(-90deg, var(--experience-tag-color2) 0 5px, #0000 0 10px)
      50%/100% 2px no-repeat;
  }
}
</style>
