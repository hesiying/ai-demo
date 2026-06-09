<template>
  <section id="portfolio">
    <div class="container">
      <h2 class="section-title">我的作品</h2>
      <div class="portfolio-grid">
        <div class="card" v-for="item in portfolioData" :key="item.id">
          <div class="card-image">
            <i :class="item.icon"></i>
          </div>
          <div class="card-content">
            <h3>{{ item.title }}</h3>
            <p>{{ item.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { portfolioData } from '@/data/portfolio'
</script>

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

.portfolio-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.card {
  background: #ffffff;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 40px rgba(0, 0, 0, 0.15);
}

.card-image {
  width: 100%;
  height: 200px;
  background: linear-gradient(135deg, #c7d2fe 0%, #e0e7ff 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  color: #6366f1;
  font-size: 3rem;
}

.card-content {
  padding: 1.5rem;
}

.card-content h3 {
  margin-bottom: 0.5rem;
  color: #1e293b;
}

.card-content p {
  color: #64748b;
  font-size: 0.95rem;
}
</style>
