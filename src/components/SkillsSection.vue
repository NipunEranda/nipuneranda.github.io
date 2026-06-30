<script setup>
const categories = [
  {
    label: 'Core Languages',
    delay: 'd1',
    tags: [
      { text: 'JavaScript', hi: true },
      { text: 'TypeScript', hi: true },
      { text: 'Rust', hi: true },
      { text: 'Java' },
      { text: 'C#' },
    ],
  },
  {
    label: 'Frontend & Desktop',
    delay: 'd2',
    tags: [
      { text: 'Vue.js', hi: true },
      { text: 'React', hi: true },
      { text: 'Nuxt' },
      { text: 'React Native' },
      { text: 'Electron' },
      { text: 'Tauri' },
    ],
  },
  {
    label: 'Backend & APIs',
    delay: 'd3',
    tags: [
      { text: 'Node.js', hi: true },
      { text: 'Spring' },
      { text: 'Quarkus' },
      { text: 'Flask' },
      { text: 'REST APIs' },
      { text: 'MQTT' },
    ],
  },
  {
    label: 'Data & Cloud',
    delay: 'd4',
    tags: [
      { text: 'MySQL', hi: true },
      { text: 'MongoDB' },
      { text: 'SQLite' },
      { text: 'Firebase' },
      { text: 'AWS' },
      { text: 'Azure' },
      { text: 'Heroku' },
      { text: 'Netlify' },
    ],
  },
  {
    label: 'DevOps & Tooling',
    delay: 'd1',
    tags: [
      { text: 'Docker', hi: true },
      { text: 'Terraform' },
      { text: 'Azure Kubernetes' },
      { text: 'GitHub Actions' },
      { text: 'AWS CodeCommit' },
      { text: 'AWS S3' },
    ],
  },
  {
    label: 'Soft Skills',
    delay: 'd2',
    tags: [
      { text: 'Leadership', hi: true },
      { text: 'Communication', hi: true },
      { text: 'Team Collaboration' },
      { text: 'English' },
      { text: 'Sinhala' },
    ],
  },
]
</script>

<template>
  <section id="skills" class="sec">
    <div class="sec-eyebrow reveal">Skills</div>
    <div class="sec-title reveal">Technical <span>stack</span></div>
    <div class="skills-grid">
      <div v-for="cat in categories" :key="cat.label" :class="['skill-cat', 'reveal', cat.delay]">
        <div class="sk-label">{{ cat.label }}</div>
        <div class="sk-tags">
          <span v-for="tag in cat.tags" :key="tag.text" :class="['sk-tag', { hi: tag.hi }]">{{ tag.text }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.skills-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 24px;
}
.skill-cat {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 28px;
  backdrop-filter: blur(10px);
  transition: border-color 0.2s;
}
.skill-cat:hover { border-color: rgba(0,212,216,0.32); }
.sk-label {
  font-size: 10.5px;
  font-weight: 600;
  letter-spacing: 2.5px;
  text-transform: uppercase;
  color: var(--teal);
  margin-bottom: 16px;
}
.sk-tags { display: flex; flex-wrap: wrap; gap: 8px; }
.sk-tag {
  padding: 6px 14px;
  background: rgba(0,212,216,0.08);
  border: 1px solid rgba(0,212,216,0.2);
  border-radius: 100px;
  font-size: 13px;
  font-weight: 500;
  color: #a8d8e8;
  transition: all 0.2s;
  cursor: default;
}
.sk-tag:hover {
  background: rgba(0,212,216,0.17);
  border-color: rgba(0,212,216,0.5);
  color: var(--teal);
}
.sk-tag.hi {
  background: rgba(0,229,160,0.09);
  border-color: rgba(0,229,160,0.28);
  color: #00e5a0;
}

@media (max-width: 900px) { .skills-grid { grid-template-columns: 1fr; } }
</style>
