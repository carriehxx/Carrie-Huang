<template>
  <div class="experience">
    <h2>My Experience</h2>
    <ul class="timeline" aria-label="Experience Timeline">
      <li class="experienceBlock" aria-label="August 2024 - Saga Volunteer (Department of IT)">
        <time datetime="2024-08">Aug 2024</time>
        <span>Beyond The Pivot</span> - Saga Volunteer (Department of IT)
      </li>
      <li
        class="experienceBlock"
        aria-label="June 2024 - August 2024, Research Intern at University of Alberta"
      >
        <time datetime="2024-06-01">Jun 2024 - Aug 2024</time>
        <span>University of Alberta</span> - Research Intern (Department of Mathematical and
        Statistical Science)
      </li>
      <li
        class="experienceBlock"
        aria-label="September 2023 - December 2023, Student Teaching Assistant at The University of Hong Kong"
      >
        <time datetime="2023-09">Sept 2023 - Dec 2023</time>
        <span>The University of Hong Kong</span> - Student Teaching Assistant (Department of
        Mathematics)
      </li>
      <li
        class="experienceBlock"
        aria-label="September 2021 - June 2023, Cambridge-HKU Joint Education Track"
      >
        <time datetime="2021-09">Sept 2021 - June 2023</time>
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

h2 {
  font-size: 4rem;
  text-align: left;
  margin-bottom: 3rem;
  color: white;
}

ul {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
}

li {
  list-style: none;
  background: var(--experience-background-gradient2);
  border-radius: 20px;
  padding: 20px;
  transition:
    transform 0.3s ease,
    box-shadow 0.3s ease;
  position: relative;
}

li:nth-of-type(even) {
  background: var(--experience-background-gradient3);
}

li:hover {
  transform: scale(1.05);
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
}

time {
  display: block;
  font-size: 1.2rem;
  font-weight: bold;
  color: #555;
  margin-bottom: 10px;
}

span {
  font-weight: bold;
}

@media (min-width: 1024px) {
  ul {
    grid-template-columns: repeat(3, 320px);
    justify-content: center;
    background: var(--experience-background-gradient);
    gap: 20px;
  }

  li {
    grid-column: span 2;
    text-align: center;
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

  time {
    position: absolute;
    right: calc(100% + 50px);
    top: 50%;
    width: 50%;
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
    background: var(--experience-border-style);
  }

  li:nth-of-type(even) time:before {
    position: absolute;
    right: auto;
    left: calc(100% + 5px);
    background: repeating-linear-gradient(
        -90deg,
        var(--experience-tag-color2) 0 5px,
        transparent 0 10px
      )
      50%/100% 2px no-repeat;
  }
}

@media (max-width: 1024px) {
  ul {
    grid-template-columns: 1fr;
    padding: 0;
    position: relative;
  }

  ul::before {
    content: '';
    position: absolute;
    top: -30px;
    left: 50%;
    width: 10px;
    height: 120%;
    background: linear-gradient(180deg, rgb(155, 98, 33) 0, #dedede00 100%);
  }

  li {
    padding: 10px;
    font-size: 1.5rem;
  }

  time {
    position: relative;
    left: 0;
    right: 0;
    text-align: center;
  }

  li:nth-of-type(even),
  li:nth-of-type(odd) time:before {
    content: none;
  }

  li:hover {
    transform: rotate3d(0, 1, 0.2, 20deg);
  }

  li:nth-of-type(even):hover {
    transform: rotate3d(0, 1, 0.2, -20deg);
  }
}
</style>
