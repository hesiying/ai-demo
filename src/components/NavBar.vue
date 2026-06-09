<template>
  <nav>
    <a href="#" class="logo">Portfolio</a>
    <input type="checkbox" id="menu-toggle" v-model="isMenuOpen">
    <label for="menu-toggle" class="hamburger">
      <span></span>
      <span></span>
      <span></span>
    </label>
    <ul class="nav-links">
      <li><a href="#hero" @click="isMenuOpen = false">首页</a></li>
      <li><a href="#portfolio" @click="isMenuOpen = false">作品</a></li>
      <li><a href="#about" @click="isMenuOpen = false">关于</a></li>
      <li><a href="#contact" @click="isMenuOpen = false">联系</a></li>
    </ul>
  </nav>
</template>

<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)
</script>

<style scoped>
nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  padding: 1rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  z-index: 1000;
}

.logo {
  font-size: 1.5rem;
  font-weight: 700;
  color: #6366f1;
  text-decoration: none;
}

.nav-links {
  display: flex;
  gap: 2rem;
  list-style: none;
}

.nav-links a {
  text-decoration: none;
  color: #1e293b;
  font-weight: 500;
  transition: color 0.3s;
}

.nav-links a:hover {
  color: #6366f1;
}

.hamburger {
  display: none;
  flex-direction: column;
  gap: 5px;
  cursor: pointer;
  padding: 5px;
}

.hamburger span {
  width: 25px;
  height: 3px;
  background: #1e293b;
  border-radius: 2px;
  transition: all 0.3s;
}

#menu-toggle {
  display: none;
}

@media (max-width: 768px) {
  .hamburger {
    display: flex;
  }

  .nav-links {
    position: fixed;
    top: 60px;
    left: 0;
    right: 0;
    background: #ffffff;
    flex-direction: column;
    align-items: center;
    padding: 2rem;
    gap: 1.5rem;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
    transform: translateY(-150%);
    transition: transform 0.3s ease;
  }

  #menu-toggle:checked ~ .nav-links {
    transform: translateY(0);
  }

  #menu-toggle:checked ~ .hamburger span:nth-child(1) {
    transform: rotate(45deg) translate(6px, 6px);
  }

  #menu-toggle:checked ~ .hamburger span:nth-child(2) {
    opacity: 0;
  }

  #menu-toggle:checked ~ .hamburger span:nth-child(3) {
    transform: rotate(-45deg) translate(6px, -6px);
  }
}
</style>
