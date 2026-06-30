<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const scrolled = ref(false)
const activeSection = ref('hero')
const mobileOpen = ref(false)

const links = [
  { id: 'about', label: 'About' },
  { id: 'experience', label: 'Experience' },
  { id: 'skills', label: 'Skills' },
  { id: 'projects', label: 'Projects' },
  { id: 'education', label: 'Education' },
  { id: 'contact', label: 'Contact' },
]

function onScroll() {
  scrolled.value = window.scrollY > 70
}

let sectionObserver
onMounted(() => {
  window.addEventListener('scroll', onScroll, { passive: true })

  sectionObserver = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) activeSection.value = e.target.id
    })
  }, { threshold: 0.35 })

  const ids = ['hero', 'about', 'experience', 'skills', 'projects', 'education', 'contact']
  ids.forEach(id => {
    const el = document.getElementById(id)
    if (el) sectionObserver.observe(el)
  })
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', onScroll)
  if (sectionObserver) sectionObserver.disconnect()
})
</script>

<template>
  <nav :class="['nav', { 'nav--scrolled': scrolled }]">
    <a href="#hero" class="nav-logo">
      <img src="../assets/logo-white.png" width="40"/>
    </a>

    <div :class="['nav-links', { 'nav-links--open': mobileOpen }]">
      <a
        v-for="link in links"
        :key="link.id"
        :href="`#${link.id}`"
        :class="['nav-link', { active: activeSection === link.id }]"
        @click="mobileOpen = false"
      >{{ link.label }}</a>
    </div>

    <button class="hamburger" :class="{ open: mobileOpen }" @click="mobileOpen = !mobileOpen" aria-label="Toggle menu">
      <span /><span /><span />
    </button>
  </nav>
</template>

<style scoped>
.nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 1000;
  padding: 18px 56px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  transition: all 0.35s ease;
}
.nav--scrolled {
  background: rgba(5,14,28,0.92);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border-bottom: 1px solid rgba(0,212,216,0.12);
}
.nav-logo {
  font-family: 'Space Grotesk', sans-serif;
  font-weight: 700;
  font-size: 22px;
  background: linear-gradient(135deg, #00d4d8, #00e5a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  letter-spacing: -0.5px;
  text-decoration: none;
  flex-shrink: 0;
}
.nav-links {
  display: flex;
  gap: 36px;
  align-items: center;
}
.nav-link {
  font-size: 14px;
  font-weight: 500;
  color: var(--muted);
  text-decoration: none;
  transition: color 0.2s;
  position: relative;
  padding-bottom: 2px;
}
.nav-link::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0;
  width: 0;
  height: 1.5px;
  background: var(--teal);
  transition: width 0.25s;
}
.nav-link:hover, .nav-link.active { color: var(--teal); }
.nav-link:hover::after, .nav-link.active::after { width: 100%; }

.hamburger {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 4px;
  z-index: 1001;
}
.hamburger span {
  display: block;
  width: 24px;
  height: 2px;
  background: var(--teal);
  border-radius: 2px;
  transition: all 0.3s;
  transform-origin: center;
}
.hamburger.open span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
.hamburger.open span:nth-child(2) { opacity: 0; }
.hamburger.open span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

@media (max-width: 900px) {
  .nav { padding: 16px 28px; }
  .nav-links { gap: 18px; }
}
@media (max-width: 560px) {
  .hamburger { display: flex; }
  .nav-links {
    display: none;
    position: fixed;
    top: 0; left: 0; right: 0;
    padding-top: 72px;
    background: rgba(5,14,28,0.97);
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    flex-direction: column;
    padding-bottom: 28px;
    gap: 0;
    border-bottom: 1px solid rgba(0,212,216,0.12);
  }
  .nav-links--open { display: flex; }
  .nav-link {
    padding: 14px 28px;
    font-size: 16px;
  }
  .nav-link::after { display: none; }
}
</style>
