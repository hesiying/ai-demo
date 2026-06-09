<template>
  <section class="about" id="about">
    <div class="container">
      <h2 class="section-title">关于我</h2>
      <div class="about-content">
        <div class="about-avatar">
          <i class="fas fa-user"></i>
        </div>
        <div class="about-text">
          <h3>全栈前端开发者</h3>
          <p>从业5年，专注于现代前端技术栈。曾任职于多家互联网公司，参与过多个大型项目的开发。</p>
          <p>热爱技术，关注用户体验，相信好的产品源于对细节的极致追求。</p>
          <div class="about-skills">
            <span class="skill-tag">HTML/CSS</span>
            <span class="skill-tag">JavaScript</span>
            <span class="skill-tag">Vue</span>
            <span class="skill-tag">React</span>
            <span class="skill-tag">Node.js</span>
            <span class="skill-tag">TypeScript</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.section-title {
  font-size: 2rem;
  text-align: center;
  margin-bottom: 3rem;
  color: #1e293b;
}

section {
  padding: 5rem 0;
}

.about {
  background: #ffffff;
}

.about-content {
  display: flex;
  align-items: center;
  gap: 3rem;
  flex-wrap: wrap;
  justify-content: center;
}

.about-avatar {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  background: linear-gradient(135deg, #6366f1 0%, #818cf8 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 4rem;
  color: #ffffff;
  flex-shrink: 0;
}

.about-text {
  max-width: 500px;
}

.about-text h3 {
  margin-bottom: 1rem;
  font-size: 1.5rem;
}

.about-text p {
  color: #64748b;
  margin-bottom: 1rem;
}

.about-skills {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
  margin-top: 1rem;
}

.skill-tag {
  background: #e0e7ff;
  color: #6366f1;
  padding: 0.4rem 1rem;
  border-radius: 20px;
  font-size: 0.85rem;
  font-weight: 500;
}
</style>
