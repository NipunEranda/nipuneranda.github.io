<template>
  <div class="sec-full" id="experience">
    <div class="sec-inner">
      <div class="sec-eyebrow reveal">Experience</div>
      <div class="sec-title reveal">Where I've <span>worked</span></div>

      <!-- AvoryX Labs -->
      <div class="exp-company reveal">
        <div class="co-header">
          <div class="co-icon co-icon--ax">AX</div>
          <div>
            <div class="co-name">
              AvoryX Labs
              <a href="https://avoryxlabs.com" target="_blank" rel="noopener" class="co-ext-link">avoryxlabs.com ↗</a>
            </div>
            <div class="co-period">Sri Lanka</div>
          </div>
        </div>
        <div class="roles">
          <div class="role reveal d1">
            <div class="role-title">Founder &amp; Chief Executive Officer</div>
            <div class="role-yr">2026 – Present</div>
          </div>
        </div>
      </div>

      <!-- Typefi -->
      <div class="exp-company reveal">
        <div class="co-header">
          <div class="co-icon">T</div>
          <div>
            <div class="co-name">Typefi Systems</div>
            <div class="co-period">January 2022 – Present · Colombo, Sri Lanka</div>
          </div>
        </div>
        <div class="roles">
          <div class="role reveal d1">
            <div class="role-title">Senior Software Engineer</div>
            <div class="role-yr">2024 – Present</div>
          </div>
          <div class="role reveal d2">
            <div class="role-title">Software Engineer</div>
            <div class="role-yr">2023 · Founder &amp; Team Lead — BIA Team</div>
            <div class="role-yr">2023 – 2024</div>
          </div>
          <div class="role reveal d3">
            <div class="role-title">Associate Software Engineer</div>
            <div class="role-yr">2022 – 2023</div>
          </div>
        </div>
      </div>

      <!-- Victory Information -->
      <div class="exp-company reveal">
        <div class="co-header">
          <div class="co-icon">VI</div>
          <div>
            <div class="co-name">Victory Information</div>
            <div class="co-period">June 2020 – November 2021 · Sri Lanka</div>
          </div>
        </div>
        <div class="roles">
          <div class="role reveal d1">
            <div class="role-title">Associate Software Engineer</div>
            <div class="role-yr">2021</div>
          </div>
          <div class="role reveal d2">
            <div class="role-title">Full Stack Intern</div>
            <div class="role-yr">2020</div>
          </div>
        </div>
      </div>

      <!-- Typefi Products -->
      <div class="sub-lbl reveal">Key Products at Typefi</div>
      <div class="typefi-grid">
        <div class="typefi-item reveal d1">
          <div class="td"></div>
          <div><div class="ti-name">Edifix</div><div class="ti-desc">The online bibliographic reference solution for publishers, service providers, editors, and authors</div></div>
        </div>
        <div class="typefi-item reveal d1">
          <div class="td"></div>
          <div><div class="ti-name">Meridian</div><div class="ti-desc">Reference processing service that integrations edifix for citation processing.</div></div>
        </div>
        <div class="typefi-item reveal d1">
          <div class="td"></div>
          <div><div class="ti-name">Orion Docs</div><div class="ti-desc">Documentation platform maintaining all documents related to Orion and Typefi products.</div></div>
        </div>
        <div class="typefi-item reveal d2">
          <div class="td"></div>
          <div><div class="ti-name">Central Station</div><div class="ti-desc">Unified dashboard to manage multiple proprietary systems and 3rd-party integrations.</div></div>
        </div>
        <div class="typefi-item reveal d3">
          <div class="td"></div>
          <div><div class="ti-name">Blinkenlights</div><div class="ti-desc">Typefi's proprietary load balancer for handling Adobe InDesign Servers at scale.</div></div>
        </div>
        <div class="typefi-item reveal d4">
          <div class="td"></div>
          <div><div class="ti-name">ScriptVault</div><div class="ti-desc">Web application to manage InDesign scripts across all GitHub Typefi organisations.</div></div>
        </div>
        <div class="typefi-item reveal d4">
          <div class="td"></div>
          <div><div class="ti-name">TPS Script</div><div class="ti-desc">Proprietary script builder for building custom InDesign scripts and publish them to script vault.</div></div>
        </div>
        <div class="typefi-item reveal d1">
          <div class="td"></div>
          <div><div class="ti-name">Babel</div><div class="ti-desc">Localization project providing multi-language support for all Typefi products.</div></div>
        </div>
        <div class="typefi-item reveal d2">
          <div class="td"></div>
          <div><div class="ti-name">MyTypefi</div><div class="ti-desc">Client portal for managing Typefi customer tickets and storage facilities.</div></div>
        </div>
        <div class="typefi-item reveal d3">
          <div class="td"></div>
          <div><div class="ti-name">LowTouch</div><div class="ti-desc">Automated license renewal system for Typefi customers.</div></div>
        </div>
        <div class="typefi-item reveal d4">
          <div class="td"></div>
          <div><div class="ti-name">Directory Services</div><div class="ti-desc">Internal application to handle customer access management across Typefi systems.</div></div>
        </div>
        <div class="typefi-item reveal d1">
          <div class="td"></div>
          <div><div class="ti-name">Admin</div><div class="ti-desc">Typefi-wide license management and administration platform.</div></div>
        </div>
        <div class="typefi-item reveal d2">
          <div class="td"></div>
          <div><div class="ti-name">Process</div><div class="ti-desc">Proprietary task-management system handling various internal engineering processes.</div></div>
        </div>
        <div class="typefi-item reveal d2">
          <div class="td"></div>
          <div><div class="ti-name">ITIssues</div><div class="ti-desc">Proprietary support task management system handling OPS requests.</div></div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.exp-company { margin-bottom: 52px; }
.co-header {
  display: flex;
  align-items: flex-start;
  gap: 18px;
  margin-bottom: 24px;
}
.co-icon {
  width: 48px;
  height: 48px;
  background: linear-gradient(135deg, rgba(0,212,216,0.18), rgba(0,229,160,0.1));
  border: 1px solid rgba(0,212,216,0.3);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Space Grotesk', sans-serif;
  font-weight: 700;
  font-size: 13px;
  color: var(--teal);
  flex-shrink: 0;
}
.co-icon--ax {
  background: linear-gradient(135deg, rgba(2,187,178,0.25), rgba(0,229,160,0.15));
  border-color: rgba(2,187,178,0.4);
  color: #02bbb2;
}
.co-name {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 20px;
  font-weight: 600;
  color: #e0f0f8;
  margin-bottom: 3px;
  display: flex;
  align-items: center;
  gap: 12px;
  flex-wrap: wrap;
}
.co-ext-link {
  font-size: 12px;
  color: #02bbb2;
  text-decoration: none;
  padding: 3px 10px;
  border: 1px solid rgba(2,187,178,0.3);
  border-radius: 100px;
  font-family: 'DM Sans', sans-serif;
  font-weight: 500;
  transition: background 0.2s;
}
.co-ext-link:hover { background: rgba(2,187,178,0.1); }
.co-period { font-size: 13px; color: var(--muted); }

/* Roles */
.roles {
  padding-left: 32px;
  border-left: 2px solid rgba(0,212,216,0.18);
  display: flex;
  flex-direction: column;
  gap: 16px;
}
.role {
  position: relative;
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  padding: 18px 22px;
  backdrop-filter: blur(8px);
  transition: border-color 0.2s, transform 0.2s;
}
.role::before {
  content: '';
  position: absolute;
  left: -39px;
  top: 50%;
  transform: translateY(-50%);
  width: 9px;
  height: 9px;
  background: var(--teal);
  border-radius: 50%;
  box-shadow: 0 0 10px rgba(0,212,216,0.6);
}
.role:hover { border-color: rgba(0,212,216,0.35); transform: translateX(5px); }
.role-title {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 15px;
  font-weight: 600;
  color: var(--teal);
  margin-bottom: 3px;
}
.role-yr { font-size: 12px; color: var(--muted); }

/* Typefi products */
.typefi-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px;
}
.typefi-item {
  background: rgba(8,22,40,0.5);
  border: 1px solid rgba(0,212,216,0.1);
  border-radius: 12px;
  padding: 18px 22px;
  display: flex;
  gap: 14px;
  align-items: flex-start;
  transition: all 0.2s;
}
.typefi-item:hover {
  border-color: rgba(0,212,216,0.28);
  background: rgba(10,28,50,0.6);
}
.td {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--teal), var(--aqua));
  flex-shrink: 0;
  margin-top: 7px;
}
.ti-name {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 14px;
  font-weight: 600;
  color: #b8d8e8;
  margin-bottom: 4px;
}
.ti-desc { font-size: 12px; color: var(--muted); line-height: 1.6; }

@media (max-width: 900px) {
  .typefi-grid { grid-template-columns: 1fr; }
}
</style>
