<script setup lang="ts">
import { ref } from 'vue'
import { RouterView, RouterLink } from 'vue-router'

const isLight = ref(false)
function toggleTheme() { isLight.value = !isLight.value }
</script>

<template>
  <div class="app" :class="{ light: isLight }">

    <!-- Animated background -->
    <div class="bg" aria-hidden="true">
      <div class="grid"></div>
      <div class="orb orb-a"></div>
      <div class="orb orb-b"></div>
      <div class="orb orb-c"></div>
    </div>

    <!-- Nav -->
    <nav class="nav">
      <RouterLink to="/" class="nav-link">My Links</RouterLink>
      <RouterLink to="/about" class="nav-link">About Me</RouterLink>
    </nav>

    <!-- Theme toggle -->
    <button class="toggle" @click="toggleTheme" :title="isLight ? 'Switch to dark mode' : 'Switch to light mode'">
      <svg v-if="isLight" viewBox="0 0 24 24" fill="currentColor" width="18" height="18">
        <path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"/>
      </svg>
      <svg v-else viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" width="18" height="18">
        <circle cx="12" cy="12" r="5"/>
        <line x1="12" y1="1" x2="12" y2="3"/>
        <line x1="12" y1="21" x2="12" y2="23"/>
        <line x1="4.22" y1="4.22" x2="5.64" y2="5.64"/>
        <line x1="18.36" y1="18.36" x2="19.78" y2="19.78"/>
        <line x1="1" y1="12" x2="3" y2="12"/>
        <line x1="21" y1="12" x2="23" y2="12"/>
        <line x1="4.22" y1="19.78" x2="5.64" y2="18.36"/>
        <line x1="18.36" y1="5.64" x2="19.78" y2="4.22"/>
      </svg>
    </button>

    <RouterView />

  </div>
</template>

<style>
.app {
  --bg: #0d0d16;
  --card-bg: rgba(255, 255, 255, 0.04);
  --card-border: rgba(255, 255, 255, 0.07);
  --card-hover-bg: rgba(255, 255, 255, 0.08);
  --text: #f0f0f4;
  --text-muted: rgba(240, 240, 244, 0.45);
  --orange: #ff6b35;
  --blue: #4f9cf9;
  --shadow: rgba(0, 0, 0, 0.55);

  min-height: 100vh;
  background: var(--bg);
  color: var(--text);
  font-family: 'Inter', sans-serif;
  position: relative;
  overflow-x: hidden;
  transition: background 0.4s ease, color 0.4s ease;
}

.app.light {
  --bg: #f0ede8;
  --card-bg: rgba(255, 255, 255, 0.65);
  --card-border: rgba(0, 0, 0, 0.08);
  --card-hover-bg: rgba(255, 255, 255, 0.9);
  --text: #1a1828;
  --text-muted: rgba(26, 24, 40, 0.45);
  --shadow: rgba(0, 0, 0, 0.12);
}

/* Background */
.bg {
  position: fixed;
  inset: 0;
  pointer-events: none;
  z-index: 0;
}

.grid {
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(79, 156, 249, 0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(79, 156, 249, 0.04) 1px, transparent 1px);
  background-size: 48px 48px;
}

.app.light .grid {
  background-image:
    linear-gradient(rgba(79, 156, 249, 0.07) 1px, transparent 1px),
    linear-gradient(90deg, rgba(79, 156, 249, 0.07) 1px, transparent 1px);
}

.orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(90px);
  animation: drift 28s ease-in-out infinite;
}
.orb-a {
  width: 500px; height: 500px;
  background: radial-gradient(circle, rgba(255, 107, 53, 0.2) 0%, transparent 70%);
  top: -150px; left: -130px;
}
.orb-b {
  width: 580px; height: 580px;
  background: radial-gradient(circle, rgba(79, 156, 249, 0.14) 0%, transparent 70%);
  bottom: -180px; right: -160px;
  animation-duration: 34s; animation-delay: -14s; animation-direction: reverse;
}
.orb-c {
  width: 320px; height: 320px;
  background: radial-gradient(circle, rgba(255, 107, 53, 0.1) 0%, transparent 70%);
  top: 45%; right: 15%;
  animation-duration: 22s; animation-delay: -7s;
}

@keyframes drift {
  0%, 100% { transform: translate(0, 0) scale(1); }
  25%  { transform: translate(40px, -35px) scale(1.06); }
  50%  { transform: translate(-25px, 45px) scale(0.94); }
  75%  { transform: translate(30px, 20px) scale(1.03); }
}

/* Nav */
.nav {
  position: fixed;
  top: 20px;
  left: 50%;
  transform: translateX(-50%);
  z-index: 10;
  display: flex;
  gap: 4px;
  background: var(--card-bg);
  border: 1px solid var(--card-border);
  border-radius: 100px;
  padding: 4px;
  backdrop-filter: blur(14px);
}

.nav-link {
  padding: 8px 22px;
  border-radius: 100px;
  font-size: 13px;
  font-weight: 500;
  color: var(--text-muted);
  text-decoration: none;
  transition: all 0.25s ease;
  white-space: nowrap;
}

.nav-link:hover {
  color: var(--text);
}

.nav-link.router-link-exact-active {
  background: var(--orange);
  color: #fff;
}

/* Toggle */
.toggle {
  position: fixed;
  top: 20px;
  right: 20px;
  z-index: 10;
  background: var(--card-bg);
  border: 1px solid var(--card-border);
  color: var(--text);
  width: 42px;
  height: 42px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  backdrop-filter: blur(12px);
  transition: all 0.3s ease;
}

.toggle:hover {
  border-color: var(--orange);
  box-shadow: 0 0 20px rgba(255, 107, 53, 0.3);
}
</style>
