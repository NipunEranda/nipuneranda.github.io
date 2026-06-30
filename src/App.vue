<script setup>
import { ref, onMounted } from 'vue'
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import ExperienceSection from './components/ExperienceSection.vue'
import SkillsSection from './components/SkillsSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import EducationSection from './components/EducationSection.vue'
import ContactSection from './components/ContactSection.vue'

const showScrollTop = ref(false)

onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) e.target.classList.add('visible')
    })
  }, { threshold: 0.08, rootMargin: '0px 0px -40px 0px' })

  document.querySelectorAll('.reveal').forEach(el => observer.observe(el))

  window.addEventListener('scroll', () => {
    showScrollTop.value = window.scrollY > 500
  }, { passive: true })
})

function scrollToTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}
</script>

<template>
  <div>
    <NavBar />
    <HeroSection />
    <div class="divider"></div>
    <AboutSection />
    <div class="divider"></div>
    <ExperienceSection />
    <div class="divider"></div>
    <SkillsSection />
    <div class="divider"></div>
    <ProjectsSection />
    <div class="divider"></div>
    <EducationSection />
    <div class="divider"></div>
    <ContactSection />

    <button
      class="scroll-top"
      :class="{ show: showScrollTop }"
      @click="scrollToTop"
      aria-label="Scroll to top"
    >
      <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#00d4d8" stroke-width="2.5">
        <polyline points="18 15 12 9 6 15"/>
      </svg>
    </button>
  </div>
</template>

<style>
.scroll-top {
  position: fixed;
  bottom: 32px;
  right: 32px;
  width: 44px;
  height: 44px;
  background: linear-gradient(135deg, rgba(0,212,216,0.2), rgba(0,229,160,0.15));
  border: 1px solid rgba(0,212,216,0.3);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.3s, transform 0.2s;
  z-index: 999;
  backdrop-filter: blur(10px);
}
.scroll-top:hover {
  transform: translateY(-3px);
  border-color: rgba(0,212,216,0.6);
}
.scroll-top.show {
  opacity: 1;
  pointer-events: auto;
}
</style>
