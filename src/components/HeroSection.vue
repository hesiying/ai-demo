<template>
  <section class="hero" id="hero" @mousemove="handleMouseMove">
    <div class="hero-content container">
      <div class="cartoon-eyes">
        <div class="eye">
          <div class="eyeball" :style="leftEyeStyle"></div>
        </div>
        <div class="eye">
          <div class="eyeball" :style="rightEyeStyle"></div>
        </div>
      </div>
      <h1>Hi, 我是 <span>Bai</span></h1>
      <p>热爱前端开发，专注于创造和复刻简洁美观的用户界面，让每一次点击都成为愉悦的体验。</p>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'

const mouseX = ref(window.innerWidth / 2)
const mouseY = ref(window.innerHeight / 2)
const heroHeight = ref(0)

const handleMouseMove = (e) => {
  const rect = e.currentTarget.getBoundingClientRect()
  heroHeight.value = rect.height
  mouseX.value = e.clientX
  mouseY.value = e.clientY
}

const getEyeStyle = (eyeCenterX, eyeCenterY) => {
  const dx = mouseX.value - eyeCenterX
  const dy = mouseY.value - eyeCenterY
  const distance = Math.sqrt(dx * dx + dy * dy)
  
  if (distance < 10) {
    return { transform: 'translate(-50%, -50%)' }
  }
  
  const maxOffset = 15
  const ratio = Math.min(1, distance / 300)
  const offsetX = (dx / distance) * maxOffset * ratio
  const offsetY = (dy / distance) * maxOffset * ratio
  
  return {
    transform: `translate(calc(-50% + ${offsetX}px), calc(-50% + ${offsetY}px))`
  }
}

const leftEyeStyle = computed(() => {
  return getEyeStyle(window.innerWidth / 2 - 35, window.innerHeight / 2 - 80)
})

const rightEyeStyle = computed(() => {
  return getEyeStyle(window.innerWidth / 2 + 35, window.innerHeight / 2 - 80)
})
</script>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  background: linear-gradient(135deg, #e0e7ff 0%, #f8fafc 100%);
  padding-top: 80px;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.hero-content h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
  color: #1e293b;
}

.hero-content h1 span {
  color: #6366f1;
}

.hero-content p {
  font-size: 1.25rem;
  color: #64748b;
  max-width: 600px;
  margin: 0 auto;
}

.cartoon-eyes {
  display: flex;
  gap: 70px;
  justify-content: center;
  margin-bottom: 1.5rem;
}

.eye {
  width: 60px;
  height: 60px;
  background: #fff;
  border-radius: 50%;
  border: 4px solid #1e293b;
  position: relative;
  overflow: hidden;
  box-shadow: inset 0 0 10px rgba(0,0,0,0.1);
}

.eyeball {
  width: 25px;
  height: 25px;
  background: #1e293b;
  border-radius: 50%;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  transition: transform 0.1s ease-out;
}

.eyeball::after {
  content: '';
  width: 8px;
  height: 8px;
  background: #fff;
  border-radius: 50%;
  position: absolute;
  top: 30%;
  left: 30%;
}

@media (max-width: 768px) {
  .hero-content h1 {
    font-size: 2rem;
  }
  .hero-content p {
    font-size: 1rem;
  }
  
  .cartoon-eyes {
    gap: 50px;
  }
  
  .eye {
    width: 45px;
    height: 45px;
  }
  
  .eyeball {
    width: 18px;
    height: 18px;
  }
}
</style>
