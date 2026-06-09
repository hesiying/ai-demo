<template>
  <section class="contact" id="contact">
    <div class="container">
      <h2 class="section-title">联系我</h2>
      <div class="contact-content">
        <p class="contact-email">
          <i class="fas fa-envelope"></i>
          hello@example.com
        </p>
        <div class="social-links">
          <a v-for="link in socialLinks" :key="link.name" :href="link.url" :title="link.name">
            <i :class="link.icon"></i>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { socialLinks } from '@/data/portfolio'
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

.contact {
  background: linear-gradient(135deg, #e0e7ff 0%, #f8fafc 100%);
}

.contact-content {
  text-align: center;
}

.contact-email {
  font-size: 1.25rem;
  color: #1e293b;
  margin-bottom: 2rem;
}

.contact-email i {
  color: #6366f1;
  margin-right: 0.5rem;
}

.social-links {
  display: flex;
  justify-content: center;
  gap: 1.5rem;
}

.social-links a {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: #ffffff;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #1e293b;
  font-size: 1.25rem;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
}

.social-links a:hover {
  transform: translateY(-5px);
  box-shadow: 0 12px 40px rgba(0, 0, 0, 0.15);
  color: #6366f1;
}
</style>
