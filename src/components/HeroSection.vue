<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const typedTitle = ref('')
const phrases = ['Full Stack Engineer', 'Desktop App Developer', 'Rust Enthusiast', 'Team Lead & Mentor']
let pIdx = 0, cIdx = 0, deleting = false, typingTimer = null, rafId = null

function tick() {
  const phrase = phrases[pIdx]
  if (!deleting) {
    typedTitle.value = phrase.substring(0, cIdx + 1)
    cIdx++
    if (cIdx === phrase.length) {
      deleting = true
      typingTimer = setTimeout(tick, 1800)
      return
    }
    typingTimer = setTimeout(tick, 80)
  } else {
    typedTitle.value = phrase.substring(0, cIdx - 1)
    cIdx--
    if (cIdx === 0) {
      deleting = false
      pIdx = (pIdx + 1) % phrases.length
    }
    typingTimer = setTimeout(tick, 45)
  }
}

function initCanvas() {
  const canvas = document.getElementById('bg-canvas')
  if (!canvas) return
  const ctx = canvas.getContext('2d')

  function resize() {
    canvas.width = window.innerWidth
    canvas.height = window.innerHeight
  }
  resize()
  window.addEventListener('resize', resize, { passive: true })

  const count = 28
  const bubbles = Array.from({ length: count }, () => ({
    x: Math.random() * window.innerWidth,
    y: Math.random() * window.innerHeight,
    r: Math.random() * 7 + 1.5,
    speed: Math.random() * 0.42 + 0.12,
    opacity: Math.random() * 0.32 + 0.04,
    wobblePhase: Math.random() * Math.PI * 2,
    wobbleAmt: Math.random() * 18 + 5,
    wobbleSpeed: (Math.random() - 0.5) * 0.018,
  }))

  function animate() {
    ctx.clearRect(0, 0, canvas.width, canvas.height)

    ctx.strokeStyle = 'rgba(0,180,210,0.025)'
    ctx.lineWidth = 1
    const gSize = 90
    for (let x = 0; x < canvas.width; x += gSize) {
      ctx.beginPath(); ctx.moveTo(x, 0); ctx.lineTo(x, canvas.height); ctx.stroke()
    }
    for (let y = 0; y < canvas.height; y += gSize) {
      ctx.beginPath(); ctx.moveTo(0, y); ctx.lineTo(canvas.width, y); ctx.stroke()
    }

    const grad = ctx.createRadialGradient(canvas.width * 0.15, canvas.height * 0.6, 0, canvas.width * 0.15, canvas.height * 0.6, canvas.width * 0.4)
    grad.addColorStop(0, 'rgba(0,100,130,0.12)')
    grad.addColorStop(1, 'rgba(0,0,0,0)')
    ctx.fillStyle = grad
    ctx.fillRect(0, 0, canvas.width, canvas.height)

    bubbles.forEach(b => {
      b.y -= b.speed
      b.wobblePhase += b.wobbleSpeed
      const xOff = Math.sin(b.wobblePhase) * b.wobbleAmt
      if (b.y + b.r < 0) {
        b.y = canvas.height + b.r
        b.x = Math.random() * canvas.width
      }
      const cx = b.x + xOff

      ctx.beginPath()
      ctx.arc(cx, b.y, b.r, 0, Math.PI * 2)
      ctx.strokeStyle = `rgba(0,212,216,${b.opacity})`
      ctx.lineWidth = 1.2
      ctx.stroke()

      ctx.beginPath()
      ctx.arc(cx - b.r * 0.3, b.y - b.r * 0.3, b.r * 0.28, 0, Math.PI * 2)
      ctx.fillStyle = `rgba(255,255,255,${b.opacity * 0.6})`
      ctx.fill()
    })

    rafId = requestAnimationFrame(animate)
  }
  animate()
}

onMounted(() => {
  initCanvas()
  typingTimer = setTimeout(tick, 600)
})

onBeforeUnmount(() => {
  if (rafId) cancelAnimationFrame(rafId)
  if (typingTimer) clearTimeout(typingTimer)
})
</script>

<template>
  <section id="hero" class="hero">
    <canvas id="bg-canvas" class="hero-canvas"></canvas>
    <div class="hero-content">
      <div class="hero-left">
        <div class="hero-badge">
          <div class="hero-badge-dot"></div>
          CEO @ AvoryX Labs · Senior SE @ Typefi Systems
        </div>
        <h1 class="hero-name">Nipun<br>Amarasekara</h1>
        <div class="hero-title-row">
          <span class="hero-title">{{ typedTitle }}</span>
          <span class="cursor"></span>
        </div>
        <div class="hero-location">
          <div class="loc-dot"></div>
          Ambalangoda, Sri Lanka
        </div>
        <p class="hero-bio">Full-stack engineer with 5+ years of professional experience building scalable web, desktop and mobile applications. Passionate about performance, developer tooling, and shipping products that matter.</p>
        <div class="hero-ctas">
          <a href="#contact" class="btn-primary">Get in touch →</a>
          <a href="#projects" class="btn-outline">View projects</a>
        </div>
        <div class="hero-socials">
          <a href="mailto:namarasekara71@gmail.com" class="soc-link">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
            namarasekara71@gmail.com
          </a>
          <a href="https://www.linkedin.com/in/nipunamarasekara" target="_blank" rel="noopener" class="soc-link">
            <svg viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
            LinkedIn
          </a>
          <a href="https://github.com/NipunEranda" target="_blank" rel="noopener" class="soc-link">
            <svg viewBox="0 0 24 24" fill="currentColor"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>
            GitHub
          </a>
        </div>
      </div>

      <div class="hero-visual">
        <div class="avatar-wrap">
          <div class="ring r1"></div>
          <div class="ring r2"></div>
          <div class="ring r3"></div>
          <div class="orbit"><div class="orbit-dot"></div></div>
          <div class="orbit orbit2"><div class="orbit-dot orbit-dot--aqua"></div></div>
          <div class="avatar-core">
            <img src="../assets/profile.jpg" alt="Nipun Amarasekara" class="avatar-photo" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  overflow: hidden;
  background:
    radial-gradient(ellipse at 15% 60%, rgba(0,70,100,0.45) 0%, transparent 55%),
    radial-gradient(ellipse at 85% 20%, rgba(0,80,90,0.25) 0%, transparent 50%),
    #050e1c;
}
.hero-canvas {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
}
.hero-content {
  position: relative;
  z-index: 2;
  max-width: 1240px;
  margin: 0 auto;
  padding: 130px 56px 80px;
  display: grid;
  grid-template-columns: 3fr 2fr;
  gap: 60px;
  align-items: center;
  width: 100%;
}
.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(0,212,216,0.09);
  border: 1px solid rgba(0,212,216,0.28);
  border-radius: 100px;
  padding: 6px 16px;
  font-size: 12px;
  font-weight: 500;
  color: var(--teal);
  margin-bottom: 28px;
}
.hero-badge-dot {
  width: 7px;
  height: 7px;
  background: var(--aqua);
  border-radius: 50%;
  flex-shrink: 0;
  animation: pulse-dot 2.2s infinite;
}
.hero-name {
  font-family: 'Space Grotesk', sans-serif;
  font-size: clamp(40px, 5.5vw, 70px);
  font-weight: 700;
  line-height: 1.04;
  letter-spacing: -2.5px;
  background: linear-gradient(135deg, #ffffff 0%, #a8dce8 35%, #00d4d8 68%, #00e5a0 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-bottom: 16px;
}
.hero-title-row {
  display: flex;
  align-items: center;
  gap: 4px;
  margin-bottom: 10px;
  min-height: 32px;
}
.hero-title {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 20px;
  font-weight: 400;
  color: var(--teal);
}
.cursor {
  display: inline-block;
  width: 2px;
  height: 22px;
  background: var(--teal);
  animation: blink 1s step-end infinite;
  vertical-align: middle;
  margin-left: 2px;
}
.hero-location {
  font-size: 14px;
  color: var(--muted);
  display: flex;
  align-items: center;
  gap: 7px;
  margin-bottom: 26px;
}
.loc-dot {
  width: 6px;
  height: 6px;
  background: var(--aqua);
  border-radius: 50%;
  flex-shrink: 0;
}
.hero-bio {
  font-size: 16px;
  line-height: 1.8;
  color: #7aadcc;
  max-width: 540px;
  margin-bottom: 36px;
}
.hero-ctas {
  display: flex;
  gap: 14px;
  flex-wrap: wrap;
  margin-bottom: 36px;
}
.hero-socials {
  display: flex;
  gap: 22px;
  flex-wrap: wrap;
}
.soc-link {
  color: var(--muted);
  font-size: 13.5px;
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 7px;
  transition: color 0.2s;
}
.soc-link:hover { color: var(--teal); }
.soc-link svg { width: 16px; height: 16px; flex-shrink: 0; }

/* Avatar */
.hero-visual {
  display: flex;
  align-items: center;
  justify-content: center;
}
.avatar-wrap {
  position: relative;
  width: 300px;
  height: 300px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.ring {
  position: absolute;
  border-radius: 50%;
  border: 1px solid rgba(0,212,216,0.2);
  animation: ring-breathe 4s ease-in-out infinite;
}
.r1 { width: 100%; height: 100%; animation-delay: 0s; }
.r2 { width: 78%; height: 78%; border-color: rgba(0,229,160,0.18); animation-delay: 0.6s; }
.r3 { width: 58%; height: 58%; animation-delay: 1.2s; }
.orbit {
  position: absolute;
  width: 100%;
  height: 100%;
  animation: orbit-spin 12s linear infinite;
}
.orbit-dot {
  position: absolute;
  top: 0; left: 50%;
  width: 8px; height: 8px;
  margin-left: -4px; margin-top: -4px;
  background: var(--teal);
  border-radius: 50%;
  box-shadow: 0 0 8px var(--teal);
}
.orbit2 {
  animation: orbit-spin 8s linear infinite reverse;
  width: 78%; height: 78%;
  top: 11%; left: 11%;
}
.orbit-dot--aqua {
  background: var(--aqua);
  box-shadow: 0 0 8px var(--aqua);
}
.avatar-core {
  width: 52%;
  height: 52%;
  border-radius: 50%;
  border: 2px solid rgba(0,212,216,0.45);
  overflow: hidden;
  box-shadow: 0 0 50px rgba(0,212,216,0.18);
}
.avatar-photo {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center top;
  display: block;
}

@media (max-width: 900px) {
  .hero-content {
    grid-template-columns: 1fr;
    padding: 110px 28px 60px;
  }
  .hero-visual { display: none; }
}
@media (max-width: 560px) {
  .hero-badge { font-size: 11px; }
  .hero-socials { gap: 14px; }
  .soc-link { font-size: 12px; }
}
</style>
