<template>
  <div class="experience">
    <h2>Experience</h2>
    <div class="experience-list">
      <div class="experience-item">
        <div class="experience-header">
          <h3>AI Model & System Research Intern</h3>
          <span class="duration">Sept 2025 - Present</span>
        </div>
        <div class="company">Centre for Artificial Intelligence and Robotics (CAIR), Hong Kong Institute of Science & Innovation, Chinese Academy of Sciences</div>
        <div class="description">
          <ul>
            <li>Participated in research on continual learning algorithms for medical scenarios, assisting in addressing long-tail and forgetting problems.</li>
            <li>Assisted in continual fine-tuning and reinforcement fine-tuning methods for MLLMs, including model architecture improvements and training strategy experiments.</li>
            <li>Conducted experimental analysis and data organization & Supported the drafting of technical documents and research papers.</li>
          </ul>
        </div>
      </div>

      <div class="experience-item">
        <div class="experience-header">
          <h3>Algorithm Intern</h3>
          <span class="duration">Jul 2025 - Aug 2025</span>
        </div>
        <div class="company">ZETA VISTA - IT Department, Shenzhen, China</div>
        <div class="description">
          <ul>
            <li>Designed and developed a child face recognition and classification application leveraging FaceNet, enhancing photo-classification efficiency on the Family-School interaction platform.</li>
            <li>Addressed high facial similarity challenges by implementing a pre-recognition image quality evaluator, utilizing an Inception-ResNet V1 model pre-trained on VGGFace2 and CASIA-Webface as the feature extractor, and applying adaptive thresholding.</li>
            <li>Engineered an AI Agent Workflow based on DIFY to automate photo album generation.</li>
          </ul>
        </div>
      </div>

      <div class="experience-item">
        <div class="experience-header">
          <h3>Research Assistant</h3>
          <span class="duration">Nov 2024 - Mar 2025</span>
        </div>
        <div class="company">University of Hong Kong - HKU Business School</div>
        <div class="description">
          <ul>
            <li>Analyzed complex mathematical problems and formalized proofs for theorems/lemmas within operations management models, optimizing contracts and strategic decisions under constraints.</li>
            <li>Employed Linear Programming and optimization techniques (e.g., KKT conditions, Gradient Descent) to solve resource allocation and supply chain challenges.</li>
            <li>Enhanced expertise in mathematical modeling and data-driven decision-making.</li>
          </ul>
        </div>
      </div>

      <div class="experience-item">
        <div class="experience-header">
          <h3>Algorithm Research Intern</h3>
          <span class="duration">Jun 2024 - Aug 2024</span>
        </div>
        <div class="company">University of Alberta - Experiments with Graph Signal Processing</div>
        <div class="description">
          <ul>
            <li>Investigated the feasibility of replacing Multi-Layer Perceptrons (MLPs) with Kolmogorov-Arnold Networks (KANs) – utilizing learnable univariate nonlinear functions instead of linear weights – through data analysis and experimental evaluation.</li>
            <li>Conducted systematic Fourier and Wavelet analysis on user-product interaction data for recommendation system; compared B-spline, Fourier, and Wavelet bases within the KAN model, demonstrating wavelet bases' superior performance in enhancing model expressiveness.</li>
            <li>Explored integrating hypergraphs with the KAN architecture to model complex user-product relationships, aiming to develop a recommendation system outperforming classical models (e.g., NGCF, LightGCN).</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.experience {
  font-family: var(--section-font-family);
  padding: 7rem 2rem;
  width: 100vw;
  background: #0d131a;
  color: white;
}

h2 {
  font-size: 5rem;
  text-align: center;
  margin-bottom: 4rem;
  color: white;
}

.experience-list {
  max-width: 1000px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.experience-item {
  background: rgba(13, 19, 26, 0.8);
  border-radius: 15px;
  padding: 2rem;
  border: 1px solid rgba(255, 138, 0, 0.3);
  border-left: 4px solid #ff8a00;
  transition: all 0.3s ease;
}

.experience-item:hover {
  background: rgba(13, 19, 26, 0.9);
  transform: translateY(-2px);
}

.experience-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
  flex-wrap: wrap;
  gap: 1rem;
}

.experience-header h3 {
  font-size: 2.2rem;
  color: #ff8a00;
  margin: 0;
}

.duration {
  background: rgba(255, 138, 0, 0.2);
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-weight: 600;
  border: 1px solid rgba(255, 138, 0, 0.5);
  color: #ff8a00;
}

.company {
  font-size: 1.2rem;
  color: #aaaaaa;
  margin-bottom: 1rem;
  font-weight: 600;
}

.description {
  font-size: 1rem;
  line-height: 1.6;
  color: #e0e0e0;
  margin: 0;
}

.description ul {
  margin: 0;
  padding-left: 1.5rem;
}

.description li {
  margin-bottom: 0.8rem;
  list-style-type: disc;
}

.description li:last-child {
  margin-bottom: 0;
}

.project-link {
  color: #cccccc;
  text-decoration: none;
  font-weight: 600;
  border-bottom: 1px solid #cccccc;
  transition: color 0.3s ease;
}

.project-link:hover {
  color: #ffffff;
}

@media (min-width: 1024px) {
  .experience {
    padding: 7rem 4rem;
  }
  
  .experience-list {
    gap: 2.5rem;
  }
  
  .experience-item {
    padding: 2.5rem;
  }
}

@media (max-width: 768px) {
  h2 {
    font-size: 3rem;
  }
  
  .experience-header {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .experience-header h3 {
    font-size: 1.5rem;
  }
}
</style>
