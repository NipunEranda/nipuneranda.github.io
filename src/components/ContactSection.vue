<template>
  <section id="contact" class="contact">
    <div class="contact-inner">
      <div class="sec-eyebrow reveal" style="text-align: center;">Contact</div>
      <div class="contact-title reveal">Let's work<br>together</div>
      <p class="contact-sub reveal">I'm always open to interesting conversations, collaborations, and new opportunities.</p>
      <div class="contact-links reveal">
        <a href="mailto:namarasekara71@gmail.com" class="c-link">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
          namarasekara71@gmail.com
        </a>
        <a href="https://www.linkedin.com/in/nipunamarasekara" target="_blank" rel="noopener" class="c-link">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
          LinkedIn
        </a>
        <a href="https://github.com/NipunEranda" target="_blank" rel="noopener" class="c-link">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>
          GitHub
        </a>
        <a href="tel:+94711294033" class="c-link">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 12a19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 3.6 1.28h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L7.91 8.69a16 16 0 0 0 6 6l.46-.46a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 21 16.92z"/></svg>
          +94 711 294 033
        </a>
      </div>
      <div class="footer-note reveal">Thirimadura Nipun Eranda Amarasekara · Ambalangoda, Sri Lanka · © 2025</div>
    </div>
  </section>
</template>

<style scoped>
.contact {
  padding: 110px 56px;
  text-align: center;
  background: linear-gradient(180deg, transparent 0%, rgba(0,50,70,0.2) 100%);
  border-top: 1px solid rgba(0,212,216,0.08);
}
.contact-inner { max-width: 700px; margin: 0 auto; }
.contact-title {
  font-family: 'Space Grotesk', sans-serif;
  font-size: clamp(36px, 4vw, 56px);
  font-weight: 700;
  letter-spacing: -2px;
  background: linear-gradient(135deg, #ffffff, #a0d8e8, #00d4d8);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-bottom: 18px;
}
.contact-sub {
  font-size: 17px;
  color: var(--muted);
  margin-bottom: 50px;
  line-height: 1.7;
}
.contact-links {
  display: flex;
  gap: 16px;
  justify-content: center;
  flex-wrap: wrap;
  margin-bottom: 60px;
}
.c-link {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 14px 26px;
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  color: #a8d8e8;
  font-size: 14px;
  font-weight: 500;
  text-decoration: none;
  transition: all 0.25s;
  backdrop-filter: blur(10px);
}
.c-link:hover {
  border-color: rgba(0,212,216,0.5);
  background: rgba(0,212,216,0.1);
  color: var(--teal);
  transform: translateY(-3px);
}
.c-link svg { width: 17px; height: 17px; flex-shrink: 0; }
.footer-note { font-size: 13px; color: #2d5060; }

@media (max-width: 900px) { .contact { padding: 80px 28px; } }
@media (max-width: 560px) {
  .c-link { padding: 12px 18px; font-size: 13px; }
}
</style>
