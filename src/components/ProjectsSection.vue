<script setup>
const projects = [
  {
    icon: '💕',
    name: 'Lovora',
    desc: 'Affordable and safe dating platform. Full iOS & Android native app development with a Rust-powered backend server.',
    tech: ['React Native', 'Rust', 'iOS', 'Android'],
    link: null,
  },
  {
    icon: '📊',
    name: 'System Dash',
    desc: 'Lightweight system dashboard to monitor processes and system usage in real time. Built with Rust and Vue.js for blazing-fast performance.',
    tech: ['Rust', 'Vue.js', 'Tauri'],
    link: 'https://github.com/NipunEranda/SystemDash',
  },
  {
    icon: '🌍',
    name: 'Localizer',
    desc: 'Web application to manage and edit localization files for GitHub projects — a developer-first i18n tool.',
    tech: ['Vue.js', 'Node.js', 'GitHub API'],
    link: 'https://github.com/NipunEranda/localizer',
  },
  {
    icon: '🏠',
    name: 'Smart House IOT',
    desc: 'Light management system using MQTT and Flask API with a static web app front-end. Full IoT home automation solution.',
    tech: ['MQTT', 'Flask', 'Python', 'IoT'],
    link: 'https://github.com/NipunEranda/Smart-House-IOT',
  },
  {
    icon: '☁️',
    name: 'Vault',
    desc: 'ElectronJS desktop application to manage files stored in Azure Blob Storage with a clean, intuitive interface.',
    tech: ['Electron', 'Azure Blob', 'Node.js'],
    link: 'https://github.com/NipunEranda/Vault',
  },
  {
    icon: '🔄',
    name: 'CompareXML',
    desc: "Alternative solution for DeltaXignia's XML comparison — a faster, open approach built with Rust and Vue JS.",
    tech: ['Rust', 'Vue.js', 'XML'],
    link: null,
  },
  {
    icon: '🐳',
    name: 'Docker Initiations',
    desc: '3-tier web app containerization with Docker and deployment automation via Terraform. Targets Azure Kubernetes cluster.',
    tech: ['Docker', 'Terraform', 'Azure AKS'],
    link: 'https://github.com/NipunEranda/Docker-Initiations',
  },
  {
    icon: '🧮',
    name: 'Code Complexity Calculator',
    desc: 'Web app to calculate cyclomatic complexity of a given program source code, supporting C++ and Java with multi-file upload.',
    tech: ['JavaScript', 'C++', 'Java'],
    link: 'https://github.com/NipunEranda/CodeComplexityCalculator',
  },
  {
    icon: '🚂',
    name: 'Train Schedule',
    desc: 'Android app to search train timetables, create custom schedules not in the official database, and set journey alarms.',
    tech: ['Android', 'Java', 'SQLite'],
    link: 'https://github.com/NipunEranda',
  },
]

const delays = ['d1', 'd2', 'd3']
</script>

<template>
  <div class="sec-full" id="projects">
    <div class="sec-inner">
      <div class="sec-eyebrow reveal">Projects</div>
      <div class="sec-title reveal">Personal <span>projects</span></div>
      <div class="proj-grid">
        <div
          v-for="(proj, i) in projects"
          :key="proj.name"
          :class="['proj-card', 'reveal', delays[i % 3]]"
        >
          <div class="proj-icon">{{ proj.icon }}</div>
          <div class="proj-name">{{ proj.name }}</div>
          <div class="proj-desc">{{ proj.desc }}</div>
          <div class="proj-tech">
            <span v-for="t in proj.tech" :key="t" class="tech-chip">{{ t }}</span>
          </div>
          <a v-if="proj.link" :href="proj.link" target="_blank" rel="noopener" class="proj-link">View on GitHub →</a>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.proj-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 22px;
}
.proj-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 26px;
  display: flex;
  flex-direction: column;
  position: relative;
  overflow: hidden;
  backdrop-filter: blur(10px);
  transition: all 0.3s ease;
}
.proj-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 2px;
  background: linear-gradient(90deg, #00d4d8, #00e5a0);
  opacity: 0;
  transition: opacity 0.3s;
}
.proj-card:hover {
  border-color: rgba(0,212,216,0.38);
  transform: translateY(-7px);
  box-shadow: 0 22px 44px rgba(0,0,0,0.28), 0 0 22px rgba(0,212,216,0.09);
}
.proj-card:hover::before { opacity: 1; }
.proj-icon { font-size: 26px; margin-bottom: 14px; }
.proj-name {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 16px;
  font-weight: 600;
  color: #e0f0f8;
  margin-bottom: 8px;
}
.proj-desc { font-size: 13px; line-height: 1.66; color: var(--muted); flex: 1; margin-bottom: 18px; }
.proj-tech { display: flex; flex-wrap: wrap; gap: 6px; margin-bottom: 14px; }
.tech-chip {
  padding: 3px 10px;
  background: rgba(0,212,216,0.07);
  border-radius: 100px;
  font-size: 11px;
  font-weight: 500;
  color: #5a8899;
  border: 1px solid rgba(0,212,216,0.12);
}
.proj-link {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  font-size: 13px;
  font-weight: 500;
  color: var(--teal);
  text-decoration: none;
  transition: gap 0.2s;
  margin-top: auto;
}
.proj-link:hover { gap: 10px; }

@media (max-width: 900px) { .proj-grid { grid-template-columns: repeat(2, 1fr); } }
@media (max-width: 560px) { .proj-grid { grid-template-columns: 1fr; } }
</style>
