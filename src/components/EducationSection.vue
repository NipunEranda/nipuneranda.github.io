<template>
  <section id="education" class="sec">
    <div class="sec-eyebrow reveal">Education</div>
    <div class="sec-title reveal">Academic <span>background</span></div>

    <div class="edu-card reveal">
      <div>
        <div class="edu-degree">BSc (Hons) in<br>Information Technology</div>
        <div class="edu-uni">Sri Lanka Institute of Information Technology</div>
        <div class="edu-period">November 2017 – December 2021 · Malabe, Sri Lanka</div>
        <div class="gpa-badge">⬡ GPA: 3.19 / 4.00</div>
      </div>
      <div class="research-card">
        <div class="res-label">Final Year Research · IEEE Publication</div>
        <div class="res-title">Project Zone: An Advanced Undergraduate Project Management System for Software Development</div>
        <div class="res-venue">
          University of Colombo School of Computing · ICTer 2021<br>
          <span class="res-published">Published on IEEE Xplore</span>
        </div>
      </div>
    </div>

    <div class="sub-lbl reveal" style="margin-top: 60px;">Referees</div>
    <div class="ref-grid">
      <div class="ref-card reveal d1">
        <div class="ref-name">Ms. Uthpala Samarakoon</div>
        <div class="ref-role">Senior Lecturer</div>
        <div class="ref-inst">Sri Lanka Institute of Information Technology</div>
        <div class="ref-contact">
          <a href="tel:0777237653">0777237653</a> · <a href="mailto:uthpala.s@sliit.lk">uthpala.s@sliit.lk</a>
        </div>
      </div>
      <div class="ref-card reveal d2">
        <div class="ref-name">Mr. Roshan Jayawardana</div>
        <div class="ref-role">Assistant Lecturer</div>
        <div class="ref-inst">Sri Lanka Institute of Information Technology</div>
        <div class="ref-contact">
          <a href="tel:0716086393">0716086393</a> · <a href="mailto:Roshan.j@sliit.lk">Roshan.j@sliit.lk</a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.edu-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 20px;
  padding: 40px;
  display: grid;
  grid-template-columns: 3fr 2fr;
  gap: 48px;
  align-items: start;
  backdrop-filter: blur(10px);
}
.edu-degree {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 22px;
  font-weight: 600;
  color: #e0f0f8;
  margin-bottom: 8px;
  line-height: 1.3;
}
.edu-uni { font-size: 15px; color: var(--teal); margin-bottom: 6px; }
.edu-period { font-size: 13px; color: var(--muted); margin-bottom: 18px; }
.gpa-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 9px 18px;
  background: rgba(0,229,160,0.1);
  border: 1px solid rgba(0,229,160,0.25);
  border-radius: 9px;
  font-size: 14px;
  font-weight: 600;
  color: var(--aqua);
}
.research-card {
  background: rgba(0,212,216,0.05);
  border: 1px solid rgba(0,212,216,0.18);
  border-radius: 14px;
  padding: 24px;
}
.res-label {
  font-size: 10px;
  font-weight: 600;
  letter-spacing: 2.5px;
  text-transform: uppercase;
  color: var(--teal);
  margin-bottom: 10px;
}
.res-title {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 14px;
  font-weight: 600;
  color: #b8d8e8;
  line-height: 1.55;
  margin-bottom: 12px;
}
.res-venue { font-size: 12px; color: var(--muted); }
.res-published { margin-top: 6px; display: block; }

/* Referees */
.ref-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
}
.ref-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 14px;
  padding: 24px;
  backdrop-filter: blur(8px);
}
.ref-name {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 15px;
  font-weight: 600;
  color: #e0f0f8;
  margin-bottom: 4px;
}
.ref-role { font-size: 13px; color: var(--teal); margin-bottom: 4px; }
.ref-inst { font-size: 12px; color: var(--muted); margin-bottom: 10px; }
.ref-contact { font-size: 12px; color: var(--muted); }
.ref-contact a { color: var(--teal); text-decoration: none; }
.ref-contact a:hover { text-decoration: underline; }

@media (max-width: 900px) {
  .edu-card { grid-template-columns: 1fr; gap: 24px; padding: 28px; }
  .ref-grid { grid-template-columns: 1fr; }
}
</style>
