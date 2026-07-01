<template>
  <section id="about" class="sec">
    <div class="sec-eyebrow reveal">About</div>
    <div class="sec-title reveal">Who I <span>am</span></div>
    <div class="about-grid">
      <div class="about-text reveal">
        <p>I'm a Senior Software Engineer at Typefi Systems, where I've spent 3+ years building and maintaining a suite of proprietary enterprise tools, also the founding member and team lead of the BIA team. Prior to that, I worked at Victory Information where i've gained valuable experience in desktop & web development.</p>
        <p>I thrive in environments that challenge me to wear multiple hats — from architecting backend services in Rust and Java, to crafting polished UIs with Vue and React, to shipping cross-platform desktop apps with Electron and Tauri.</p>
        <p>Outside of work, I'm constantly exploring: whether it's IoT systems, containerization automation, or building my own tools to solve real problems. I believe the best engineers are the ones who never stop building.</p>
      </div>
      <div class="stats-grid reveal d1">
        <div class="stat-card">
          <span class="stat-num">5+</span>
          <div class="stat-lbl">Years Experience</div>
        </div>
        <div class="stat-card">
          <span class="stat-num">CEO</span>
          <div class="stat-lbl">AvoryX Labs</div>
        </div>
        <div class="stat-card">
          <span class="stat-num">12+</span>
          <div class="stat-lbl">Personal Projects</div>
        </div>
        <div class="stat-card">
          <span class="stat-num">3.19</span>
          <div class="stat-lbl">GPA (BSc Hons)</div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-grid {
  display: grid;
  grid-template-columns: 3fr 2fr;
  gap: 72px;
  align-items: start;
}
.about-text {
  font-size: 17px;
  line-height: 1.82;
  color: #7aadcc;
}
.about-text p { margin-bottom: 22px; }
.about-text p:last-child { margin-bottom: 0; }

.stats-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 18px;
}
.stat-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 14px;
  padding: 24px 20px;
  text-align: center;
  backdrop-filter: blur(10px);
  transition: border-color 0.2s, transform 0.2s;
}
.stat-card:hover {
  border-color: rgba(0,212,216,0.38);
  transform: translateY(-4px);
}
.stat-num {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 38px;
  font-weight: 700;
  background: linear-gradient(135deg, #00d4d8, #00e5a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  display: block;
  margin-bottom: 4px;
}
.stat-lbl {
  font-size: 12px;
  color: var(--muted);
  font-weight: 500;
  letter-spacing: 0.3px;
}

@media (max-width: 900px) {
  .about-grid { grid-template-columns: 1fr; gap: 36px; }
}
</style>
