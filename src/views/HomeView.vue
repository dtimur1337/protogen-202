<script setup lang="ts">
const links = [
  {
    id: 'px500',
    platform: '500px',
    handle: 'dtimur',
    url: 'https://500px.com/p/dtimur?view=photos',
    color: '#1cbf4e',
  },
  {
    id: 'insta1',
    platform: 'Instagram',
    handle: '@creo.works',
    url: 'https://www.instagram.com/creo.works',
    color: '#e1306c',
  },
  {
    id: 'insta2',
    platform: 'Instagram',
    handle: '@awscreo',
    url: 'https://www.instagram.com/awscreo',
    color: '#e1306c',
  },
  {
    id: 'artstation',
    platform: 'ArtStation',
    handle: 'awscreo',
    url: 'https://www.artstation.com/awscreo',
    color: '#13aff0',
  },
  {
    id: 'linkedin',
    platform: 'LinkedIn',
    handle: 'timur-dzhambinov',
    url: 'https://www.linkedin.com/in/timur-dzhambinov/',
    color: '#0a66c2',
  },
]
</script>

<template>
  <main class="main">

    <!-- Profile -->
    <div class="profile">
      <div class="avatar">
        <img class="avatar-photo" src="/Self_portrait_1x1.jpeg" alt="Timur Dzhambinov" />
        <div class="avatar-ring"></div>
      </div>
      <h1 class="name">Timur Dzhambinov</h1>
      <p class="subtitle">UX Architect</p>
    </div>

    <!-- Social cards -->
    <div class="cards">
      <a
        v-for="link in links"
        :key="link.id"
        :href="link.url"
        class="card"
        target="_blank"
        rel="noopener noreferrer"
      >
        <span class="icon" :style="{ color: link.color }">
          <!-- 500px -->
          <svg v-if="link.id === 'px500'" viewBox="0 0 24 24" fill="currentColor" width="26" height="26">
            <circle cx="12" cy="12" r="11" fill="none" stroke="currentColor" stroke-width="1.5"/>
            <text x="12" y="15.5" text-anchor="middle" font-size="6.5" font-weight="700" fill="currentColor" font-family="Inter, sans-serif">500px</text>
          </svg>
          <!-- Instagram -->
          <svg v-else-if="link.platform === 'Instagram'" viewBox="0 0 24 24" fill="currentColor" width="24" height="24">
            <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
          </svg>
          <!-- ArtStation -->
          <svg v-else-if="link.id === 'artstation'" viewBox="0 0 24 24" fill="currentColor" width="24" height="24">
            <path d="M0 17.723l2.027 3.505h.001a2.424 2.424 0 0 0 2.164 1.333h13.457l-2.792-4.838H0zm24 .025c0-.484-.143-.927-.388-1.302L15.728 2.24a2.424 2.424 0 0 0-2.142-1.289H9.419L21.598 22.54l1.92-3.325c.378-.637.482-.919.482-1.467zm-11.129-3.462L7.428 4.858l-5.444 9.428h10.887z"/>
          </svg>
          <!-- LinkedIn -->
          <svg v-else-if="link.id === 'linkedin'" viewBox="0 0 24 24" fill="currentColor" width="24" height="24">
            <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
          </svg>
        </span>

        <div class="card-text">
          <span class="card-platform">{{ link.platform }}</span>
          <span class="card-handle">{{ link.handle }}</span>
        </div>

        <span class="card-arrow">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" width="16" height="16">
            <line x1="5" y1="12" x2="19" y2="12"/>
            <polyline points="12 5 19 12 12 19"/>
          </svg>
        </span>
      </a>
    </div>

    <!-- Footer -->
    <footer class="footer">
      Made with <span class="accent">Claude</span>
    </footer>

  </main>
</template>

<style scoped>
.main {
  position: relative;
  z-index: 1;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 80px 20px 48px;
}

.profile {
  text-align: center;
  margin-bottom: 44px;
}

.avatar {
  position: relative;
  width: 120px;
  height: 120px;
  margin: 0 auto 20px;
}

.avatar-photo {
  position: absolute;
  inset: 4px;
  width: calc(100% - 8px);
  height: calc(100% - 8px);
  border-radius: 50%;
  object-fit: cover;
  z-index: 1;
}

.avatar-ring {
  position: absolute;
  inset: 0;
  border-radius: 50%;
  border: 2px solid transparent;
  background:
    linear-gradient(var(--bg), var(--bg)) padding-box,
    linear-gradient(135deg, var(--orange), var(--blue)) border-box;
  animation: spin-ring 8s linear infinite;
}

@keyframes spin-ring {
  to { transform: rotate(360deg); }
}

.name {
  font-size: clamp(22px, 5vw, 28px);
  font-weight: 700;
  margin: 0 0 8px;
  background: linear-gradient(130deg, var(--text) 55%, var(--orange) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.subtitle {
  font-size: 12px;
  font-weight: 400;
  color: var(--text-muted);
  letter-spacing: 3px;
  text-transform: uppercase;
  margin: 0;
}

.cards {
  width: 100%;
  max-width: 480px;
  display: flex;
  flex-direction: column;
  gap: 14px;
}

.card {
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 16px 20px;
  background: var(--card-bg);
  border: 1px solid var(--card-border);
  border-radius: 14px;
  text-decoration: none;
  color: var(--text);
  backdrop-filter: blur(14px);
  transform: perspective(700px) rotateX(7deg);
  box-shadow:
    0 8px 0 -1px rgba(0, 0, 0, 0.35),
    0 16px 24px var(--shadow);
  transition:
    transform 0.35s cubic-bezier(0.4, 0, 0.2, 1),
    box-shadow 0.35s cubic-bezier(0.4, 0, 0.2, 1),
    background 0.35s ease,
    border-color 0.35s ease;
}

.card:hover {
  transform: perspective(700px) rotateX(0deg) translateY(-5px);
  background: var(--card-hover-bg);
  border-color: rgba(255, 107, 53, 0.35);
  box-shadow:
    0 20px 40px var(--shadow),
    0 0 0 1px rgba(255, 107, 53, 0.12),
    0 0 35px rgba(255, 107, 53, 0.08);
}

.icon {
  width: 42px;
  height: 42px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.card-text {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 3px;
}

.card-platform {
  font-size: 15px;
  font-weight: 600;
}

.card-handle {
  font-size: 12px;
  color: var(--text-muted);
}

.card-arrow {
  color: var(--text-muted);
  display: flex;
  align-items: center;
  transition: color 0.3s ease, transform 0.3s ease;
}

.card:hover .card-arrow {
  color: var(--orange);
  transform: translateX(4px);
}

.footer {
  margin-top: 52px;
  font-size: 12px;
  color: var(--text-muted);
  letter-spacing: 1px;
}

.accent {
  color: var(--orange);
  font-weight: 500;
}
</style>
