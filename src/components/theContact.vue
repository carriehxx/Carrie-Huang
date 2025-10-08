<template>
  <div class="contact">
    <h2>Contact</h2>
    <div class="contact-list">
      <div class="contact-item">
        <i class="bx bx-envelope"></i>
        <div class="contact-info">
          <h3>Email</h3>
          <a href="mailto:carriehuangx02@gmail.com">carriehuangx02@gmail.com</a>
          <br>
          <a href="mailto:carriehuangxin@foxmail.com">carriehuangxin@foxmail.com</a>
        </div>
      </div>
      
      <div class="contact-item">
        <i class="bx bx-phone"></i>
        <div class="contact-info">
          <h3>Phone</h3>
          <span>(+852) 95725272</span>
          <br>
          <span>(+86) 18666513949</span>
        </div>
      </div>
      
      <div class="contact-item">
        <i class="bx bxl-linkedin"></i>
        <div class="contact-info">
          <h3>LinkedIn</h3>
          <a href="https://www.linkedin.com/in/carriehuangxin/" target="_blank">linkedin.com/in/carriehuangxin/</a>
        </div>
      </div>
      
      <div class="contact-item">
        <i class="bx bxl-github"></i>
        <div class="contact-info">
          <h3>GitHub</h3>
          <a href="https://github.com/carriehxx" target="_blank">github.com/carriehxx</a>
        </div>
      </div>
      
      <div class="contact-item">
        <i class="bx bxl-instagram"></i>
        <div class="contact-info">
          <h3>Instagram</h3>
          <a href="https://www.instagram.com/carriehxx/" target="_blank">@carriehxx</a>
        </div>
      </div>
      
      <div class="contact-item">
        <i class="bx bx-file"></i>
        <div class="contact-info">
          <h3>Resume</h3>
          <a href="./assets/resume/Huang_Xin_HKU_Resume.pdf" target="_blank">English version</a>
          <br>
          <a href="./assets/resume/黄鑫_香港大学_个人简历.pdf" target="_blank">Chinese version</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// Simple contact component - no complex JavaScript needed
</script>

<style scoped>
.contact {
  font-family: var(--section-font-family);
  padding: 7rem 2rem;
  width: 100vw;
  min-height: 100vh;
  background: #0d131a;
  color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
}

h2 {
  font-size: 5rem;
  text-align: center;
  margin-bottom: 4rem;
  color: white;
}

.contact-list {
  max-width: 800px;
  width: 100%;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.contact-item {
  background: rgba(13, 19, 26, 0.8);
  border-radius: 15px;
  padding: 2rem;
  border: 1px solid rgba(255, 138, 0, 0.3);
  border-left: 4px solid #ff8a00;
  display: flex;
  align-items: center;
  gap: 1.5rem;
  transition: all 0.3s ease;
}

.contact-item:hover {
  background: rgba(13, 19, 26, 0.9);
  transform: translateY(-2px);
}

.contact-item i {
  font-size: 2.5rem;
  color: #ff8a00;
  min-width: 3rem;
}

.contact-info h3 {
  font-size: 1.4rem;
  color: #ff8a00;
  margin: 0 0 0.5rem 0;
  font-weight: 600;
}

.contact-info a,
.contact-info span {
  color: #e0e0e0;
  text-decoration: none;
  font-size: 1rem;
  transition: color 0.3s ease;
}

.contact-info a:hover {
  color: #ffffff;
}

@media (min-width: 1024px) {
  .contact {
    padding: 7rem 4rem;
  }
  
  .contact-list {
    grid-template-columns: repeat(2, 1fr);
    gap: 2.5rem;
  }
  
  .contact-item {
    padding: 2.5rem;
  }
}

@media (max-width: 768px) {
  h2 {
    font-size: 3rem;
  }
  
  .contact-list {
    grid-template-columns: 1fr;
  }
  
  .contact-item {
    flex-direction: column;
    text-align: center;
    gap: 1rem;
  }
}
</style>
