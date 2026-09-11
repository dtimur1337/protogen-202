<script setup lang="ts">
const skills = [
  'Design Systems', 'AI Powered Workflows', 'Complex User Experiences',
  'Visual Design', 'Branding', 'Discovery & Workshops',
  'User Workflows', 'Photography', '3D Modeling', 'Motion Design',
]

const tools = [
  'Figma', 'Claude', 'Kiro', 'Miro', 'Blender', 'Plasticity 3D', 'Adobe Suite',
]
</script>

<template>
  <main class="main">
    <div class="container">

      <div class="profile">
        <div class="avatar">
          <img class="avatar-photo" src="/Self_portrait_1x1.jpeg" alt="Timur Dzhambinov" />
          <div class="avatar-ring"></div>
        </div>
        <h1 class="name">Timur Dzhambinov</h1>
        <p class="subtitle">UX Architect</p>
      </div>

      <div class="card">
        <p class="bio">
          I'm a UX designer with a strong visual design foundation and nearly two decades of experience
          in the industry. I've led design on large, complex projects across healthcare staffing and
          public/government sectors.
        </p>
        <p class="bio">
          My passion is working closely with stakeholders to uncover the <em>real</em> problems —
          not just the stated ones — and crafting solutions that hold up under scrutiny. I specialize
          in building complex design systems and optimized workflows, including leveraging AI to
          accelerate front-end component development and make design-to-dev handoffs faster and smoother.
        </p>
      </div>

      <div class="card">
        <div class="section">
          <h2 class="section-title">Skills</h2>
          <div class="tags">
            <span class="tag" v-for="skill in skills" :key="skill">{{ skill }}</span>
          </div>
        </div>
        <div class="divider"></div>
        <div class="section">
          <h2 class="section-title">Tools</h2>
          <div class="tags">
            <span class="tag tag-tool" v-for="tool in tools" :key="tool">{{ tool }}</span>
          </div>
        </div>
      </div>

    </div>
  </main>
</template>

<style scoped>
.main {
  position: relative;
  z-index: 1;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 80px 20px 48px;
}

.container {
  width: 100%;
  max-width: 480px;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

/* Profile */
.profile {
  text-align: center;
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
  margin: 0 0 4px;
}

/* Bio card */
.card {
  background: var(--card-bg);
  border: 1px solid var(--card-border);
  border-radius: 16px;
  padding: 28px;
  backdrop-filter: blur(14px);
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.bio {
  font-size: 15px;
  line-height: 1.75;
  color: var(--text);
  margin: 0;
}

.bio em {
  font-style: italic;
  color: var(--orange);
}

.section {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.section-title {
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--text-muted);
  margin: 0;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.tag {
  font-size: 13px;
  font-weight: 500;
  padding: 6px 14px;
  border-radius: 100px;
  background: rgba(255, 107, 53, 0.08);
  border: 1px solid rgba(255, 107, 53, 0.2);
  color: var(--text);
  transition: all 0.2s ease;
}

.tag:hover {
  background: rgba(255, 107, 53, 0.15);
  border-color: rgba(255, 107, 53, 0.4);
}

.tag-tool {
  background: rgba(79, 156, 249, 0.08);
  border-color: rgba(79, 156, 249, 0.2);
}

.tag-tool:hover {
  background: rgba(79, 156, 249, 0.15);
  border-color: rgba(79, 156, 249, 0.4);
}

.divider {
  height: 1px;
  background: var(--card-border);
}
</style>
