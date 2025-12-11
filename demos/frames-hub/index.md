---
layout: article
title: FRAMES @ Bronco Space Lab
key: page-frames-hub
permalink: /frames-hub/
---

<style>
.hero-section {
  text-align: center;
  padding: 3em 1em 2em;
  background: linear-gradient(135deg, #1e3a8a 0%, #3b82f6 100%);
  color: white;
  margin: -2em -2em 3em -2em;
  border-radius: 0 0 16px 16px;
}

.hero-section h1 {
  font-size: 2.5em;
  margin: 0 0 0.5em 0;
  color: white;
}

.hero-section p {
  font-size: 1.2em;
  opacity: 0.95;
  max-width: 600px;
  margin: 0 auto;
}

.app-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2em;
  margin: 3em 0;
}

.app-card {
  background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
  border: 2px solid #cbd5e1;
  border-radius: 12px;
  padding: 2em;
  text-align: center;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.app-card:hover {
  transform: translateY(-4px);
  border-color: #3b82f6;
  box-shadow: 0 8px 24px rgba(59, 130, 246, 0.2);
}

.app-card.available {
  background: linear-gradient(135deg, #ecfdf5 0%, #d1fae5 100%);
  border-color: #10b981;
}

.app-card.coming-soon {
  background: linear-gradient(135deg, #fef3c7 0%, #fde68a 100%);
  border-color: #f59e0b;
}

.app-icon {
  font-size: 3em;
  margin-bottom: 0.5em;
}

.app-card h3 {
  margin: 0.5em 0;
  font-size: 1.5em;
  color: #1e293b;
}

.app-card p {
  color: #475569;
  margin: 1em 0;
  line-height: 1.6;
}

.app-button {
  display: inline-block;
  background: #3b82f6;
  color: white !important;
  padding: 0.75em 2em;
  border-radius: 8px;
  text-decoration: none !important;
  font-weight: 600;
  transition: all 0.3s ease;
  margin-top: 1em;
}

.app-button:hover {
  background: #2563eb;
  transform: scale(1.05);
}

.app-button.coming-soon-btn {
  background: #94a3b8;
  cursor: not-allowed;
}

.app-button.coming-soon-btn:hover {
  background: #94a3b8;
  transform: none;
}

.status-badge {
  display: inline-block;
  padding: 0.4em 1em;
  border-radius: 20px;
  font-size: 0.85em;
  font-weight: 600;
  margin-bottom: 1em;
}

.status-badge.live {
  background: #10b981;
  color: white;
}

.status-badge.coming {
  background: #f59e0b;
  color: white;
}

.announcements-section {
  background: #f1f5f9;
  border-left: 4px solid #3b82f6;
  padding: 1.5em;
  border-radius: 8px;
  margin: 3em 0;
}

.announcements-section h2 {
  margin-top: 0;
  color: #1e293b;
}

.quick-links {
  display: flex;
  justify-content: center;
  gap: 2em;
  margin: 2em 0;
  flex-wrap: wrap;
}

.quick-links a {
  color: #3b82f6;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
}

.quick-links a:hover {
  color: #2563eb;
  text-decoration: underline;
}

@media (max-width: 768px) {
  .hero-section h1 {
    font-size: 2em;
  }

  .app-grid {
    grid-template-columns: 1fr;
  }
}
</style>

<div class="hero-section">
  <h1>🚀 FRAMES @ Bronco Space Lab</h1>
  <p>Framework for Research & Analytics in Mission Engineering Systems</p>
  <p style="font-size: 0.9em; margin-top: 1em; opacity: 0.85;">Your central hub for predictive mission success tools</p>
</div>

---

## Welcome to FRAMES

Access the tools that help Bronco Space Lab predict mission success, streamline onboarding, and preserve institutional knowledge across student rotations.

---

<div class="app-grid">

<!-- Student LMS -->
<div class="app-card coming-soon">
  <div class="app-icon">📚</div>
  <span class="status-badge coming">Coming Soon</span>
  <h3>Student LMS</h3>
  <p>Personalized learning paths tailored to your experience level. Get onboarded faster with adaptive content and competency validation.</p>
  <ul style="text-align: left; color: #64748b; font-size: 0.9em;">
    <li>Customized learning modules</li>
    <li>Progress tracking</li>
    <li>Interactive assessments</li>
    <li>Offline-capable (PWA)</li>
  </ul>
  <a href="#" class="app-button coming-soon-btn">Launch LMS</a>
</div>

<!-- Team Dashboard -->
<div class="app-card coming-soon">
  <div class="app-icon">📊</div>
  <span class="status-badge coming">Coming Soon</span>
  <h3>Team Dashboard</h3>
  <p>Real-time risk visualization and knowledge mapping. See interface health, upcoming transitions, and mission success probability.</p>
  <ul style="text-align: left; color: #64748b; font-size: 0.9em;">
    <li>Risk heat maps</li>
    <li>Knowledge concentration alerts</li>
    <li>Handoff tracking</li>
    <li>Mission success gauge</li>
  </ul>
  <a href="#" class="app-button coming-soon-btn">Launch Dashboard</a>
</div>

<!-- Analytics Platform -->
<div class="app-card coming-soon">
  <div class="app-icon">🔬</div>
  <span class="status-badge coming">Coming Soon</span>
  <h3>Analytics Platform</h3>
  <p>Research-grade data visualization and predictive model validation. Explore multi-semester trends and interface-outcome correlations.</p>
  <ul style="text-align: left; color: #64748b; font-size: 0.9em;">
    <li>Multi-semester visualization</li>
    <li>Predictive model validation</li>
    <li>Cohort comparisons</li>
    <li>Export for publications</li>
  </ul>
  <a href="#" class="app-button coming-soon-btn">Launch Analytics</a>
</div>

</div>

---

## 📢 Announcements

<div class="announcements-section">
  <h2>Latest Updates</h2>
  <p><strong>December 2024:</strong> FRAMES hub now live! Applications coming soon as we complete Phase 1 deployment.</p>
  <p><em>Check back here for system updates, new features, and important announcements.</em></p>
</div>

---

## Quick Links

<div class="quick-links">
  <a href="/Portfolio/bronco-demo/">📖 About FRAMES (Demo for Lab Director)</a>
  <a href="https://github.com/Lizo-RoadTown/FRAMES-Python" target="_blank">💻 GitHub Repository</a>
  <a href="/Portfolio/">🏠 Main Portfolio</a>
  <a href="mailto:eosborn@cpp.edu">📧 Contact Support</a>
</div>

---

## Getting Started

**New to FRAMES?**
1. **Students:** When the LMS launches, you'll receive an email with your login credentials
2. **Team Leads:** Dashboard access will be granted by the lab director
3. **Researchers:** Analytics platform requires IRB approval and data access permissions

**Need Help?**
- Technical issues: [GitHub Issues](https://github.com/Lizo-RoadTown/FRAMES-Python/issues)
- Questions about FRAMES: [eosborn@cpp.edu](mailto:eosborn@cpp.edu)
- Lab Director inquiries: See the [full demo walkthrough](/Portfolio/bronco-demo/)

---

<div style="text-align: center; padding: 2em; background: #f8fafc; border-radius: 8px; margin-top: 3em;">
  <h3 style="margin-top: 0;">🛠️ System Status</h3>
  <p style="color: #64748b;">Phase 1 deployment in progress. All applications currently in development.</p>
  <p style="font-size: 0.9em; color: #94a3b8; margin-bottom: 0;">Last updated: December 2024</p>
</div>

---

<div style="text-align: center; margin-top: 3em; font-size: 0.9em; color: #94a3b8;">
  <p>FRAMES @ Bronco Space Lab | Cal Poly Pomona</p>
  <p>Framework for Research & Analytics in Mission Engineering Systems</p>
</div>
