<template>
  <div class="education">
    <h2>Education</h2>
    <div class="education-content">
      <div class="education-item">
        <div class="education-header">
          <h3>Master of Science in Computer Science</h3>
          <span class="duration">Sept 2025 - Jul 2026</span>
        </div>
        <div class="education-details">
          <p class="degree">University of Hong Kong - School of Computing and Data Science</p>
          <!-- <p class="honors">Dean's Honours List in Faculty of Science</p> -->
          <div class="courses">
            <h4>Key Courses:</h4>
            <p>Natural Language Processing, Deep Learning, Data Mining, Introduction to Unmanned System, Digital Signal Processing and Computer Vision</p>
          </div>
        </div>
      </div>

      <div class="education-item">
        <div class="education-header">
          <h3>Bachelor of Science in Mathematics</h3>
          <span class="duration">Sept 2021 - Jul 2025</span>
        </div>
        <div class="education-details">
          <p class="degree">University of Hong Kong - Major: Mathematics; Minor: Computer Science</p>
          <p class="honors">First Class Honors Graduate (Top 10% of BSc)
            <br>
            Dean's Honours List in Faculty of Science
          </p>
          <p class="gpa">Cumulative GPA: 3.64/4.3</p>
          <div class="courses">
            <h4>Key Courses:</h4>
            <div class="course-categories">
              <div class="course-category">
                <strong>Mathematics:</strong> Operations Research, Probability and Statistics, Scientific Computing, Differential Equations, Optimization, Numerical Analysis, Financial Calculus, Game Theory, Functional Analysis, Linear Algebra I & II
              </div>
              <div class="course-category">
                <strong>Computer Science:</strong> Algorithm Design, Data Structure and Algorithm, Artificial Intelligence, Database Management
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <div class="skills-section">
        <h3>Skills</h3>
        <div class="skills-grid">
          <div class="skill-category">
            <h4>Programming Languages</h4>
            <div class="skill-tags">
              <span class="skill-tag">Python</span>
              <!-- <span class="skill-tag">JavaScript</span> -->
              <span class="skill-tag">C++</span>
              <span class="skill-tag">SQL</span>
            </div>
          </div>
          <div class="skill-category">
            <h4>Web Technologies</h4>
            <div class="skill-tags">
              <!-- <span class="skill-tag">HTML</span>
              <span class="skill-tag">CSS</span> -->
              <span class="skill-tag">Vue.js</span>
            </div>
          </div>
          <div class="skill-category">
            <h4>Tools & Software</h4>
            <div class="skill-tags">
              <span class="skill-tag">Tableau</span>
              <span class="skill-tag">MatLab</span>
              <span class="skill-tag">MySQL</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.education {
  font-family: var(--section-font-family);
  padding: 7rem 2rem;
  width: 100vw;
  min-height: 100vh;
  background: #0d131a;
  color: white;
}

h2 {
  font-size: 5rem;
  text-align: center;
  margin-bottom: 4rem;
  color: white;
  font-weight: 600;
}

.education-content {
  max-width: 1200px;
  margin: 0 auto;
}

.education-item {
  background: rgba(13, 19, 26, 0.8);
  backdrop-filter: blur(10px);
  border-radius: 20px;
  padding: 2rem;
  margin-bottom: 3rem;
  border: 1px solid rgba(255, 138, 0, 0.3);
  border-left: 4px solid #ff8a00;
}

.education-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1.5rem;
  flex-wrap: wrap;
  gap: 1rem;
}

.education-header h3 {
  font-size: 3rem;
  margin: 0;
  color: #ff8a00;
}

.duration {
  background: rgba(255, 138, 0, 0.2);
  padding: 0.5rem 1rem;
  border-radius: 25px;
  font-weight: 600;
  border: 1px solid rgba(255, 138, 0, 0.5);
  color: #ff8a00;
}

.education-details p {
  font-size: 1.2rem;
  margin: 0.8rem 0;
  line-height: 1.6;
}

.degree {
  font-size: 1.5rem;
  font-weight: 600;
  color: #e0e0e0;
}

.honors {
  color: #aaaaaa;
  font-weight: 600;
}

.program {
  color: #b0b0b0;
  font-style: italic;
}

.gpa {
  color: #aaaaaa;
  font-weight: 600;
  font-size: 1.1rem;
}

.courses {
  margin-top: 1.5rem;
}

.courses h4 {
  color: #cccccc;
  font-size: 1.2rem;
  margin-bottom: 1rem;
}

.course-categories {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.course-category {
  background: rgba(60, 60, 60, 0.5);
  padding: 1rem;
  border-radius: 10px;
  border-left: 3px solid #666666;
}

.course-category strong {
  color: #cccccc;
  display: block;
  margin-bottom: 0.5rem;
}

.skills-section {
  background: rgba(13, 19, 26, 0.8);
  backdrop-filter: blur(10px);
  border-radius: 20px;
  padding: 2rem;
  border: 1px solid rgba(255, 138, 0, 0.3);
  border-left: 4px solid #ff8a00;
}

.skills-section h3 {
  font-size: 3rem;
  margin-bottom: 2rem;
  color: #ff8a00;
  text-align: center;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.skill-category h4 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  color: #e0e0e0;
}

.skill-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.8rem;
}

.skill-tag {
  background: rgba(255, 138, 0, 0.2);
  color: #ff8a00;
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-weight: 600;
  border: 1px solid rgba(255, 138, 0, 0.5);
  transition: all 0.3s ease;
}

.skill-tag:hover {
  background: rgba(255, 138, 0, 0.3);
  transform: translateY(-2px);
}

@media (min-width: 1024px) {
  .education {
    padding: 7rem 4rem;
  }
  
  .education-header {
    flex-direction: row;
  }
  
  .skills-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media (max-width: 768px) {
  h2 {
    font-size: 3rem;
  }
  
  .education-header {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .education-header h3 {
    font-size: 2rem;
  }
  
  .skills-grid {
    grid-template-columns: 1fr;
  }
  
  .course-categories {
    gap: 0.8rem;
  }
  
  .course-category {
    padding: 0.8rem;
  }
}
</style>
