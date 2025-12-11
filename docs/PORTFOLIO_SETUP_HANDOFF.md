# 🚀 FRAMES Portfolio - Complete Setup Instructions

**Target Repository:** https://github.com/Lizo-RoadTown/Portfolio.git
**Purpose:** Create a Jekyll static site hosted on GitHub Pages to showcase the FRAMES project
**Environment:** GitHub Codespace (preferred) or local development

---

## 📋 OVERVIEW

You are setting up a **Jekyll-based portfolio website** to showcase the FRAMES project (a multi-university research platform for space mission programs). This site will be hosted on GitHub Pages at `https://lizo-roadtown.github.io/Portfolio/`.

**FRAMES** is a research-driven ecosystem that transforms real engineering work—especially in university CubeSat and aerospace programs—into structured learning, organizational insight, and research-grade data. It's a human-AI collaboration framework combining educational research, systems theory, AI architecture, and engineering pedagogy.

---

## 🎯 PROJECT CONTEXT: What is FRAMES?

### Core Identity
FRAMES captures how students and teams **actually think, collaborate, and solve problems** in university space labs, then transforms those practices into:
- 🎓 **Onboarding modules** for new engineers
- 📊 **Analytics** for researchers studying collaboration
- 🔗 **Insights** into organizational resilience and knowledge transfer
- 📈 **Datasets** for understanding decision-making patterns
- 🤖 **Demonstrations** of multi-agent AI working safely with humans

### The Five-Layer Architecture
```
🌐 REAL WORK LAYER
   Team Leads document missions in Notion
              ↓
🤖 AI INTERPRETATION LAYER
   Alpha · Beta · Gamma agents (safe, controlled)
              ↓
💾 CANONICAL DATA LAYER
   Neon PostgreSQL · 37+ Tables
              ↓
┌──────────────┬──────────────┬──────────────┐
📱 Student LMS  📋 Team Tools   📊 Research
   React PWA    Notion Space    Jupyter+MLflow
```

### Key Statistics
- **8 Partner Universities** (Cal Poly Pomona lead, Columbia, Texas State, Virginia Tech, Washington State, U Illinois, Northeastern, Mt. SAC)
- **37+ Database Tables** (Neon PostgreSQL)
- **3 Controlled AI Agents** (Alpha, Beta, Gamma)
- **Tech Stack:** Python 3.9+, React 18+, Flask 3.0, PostgreSQL 15+

### Why FRAMES Exists
University engineering programs struggle with:
- ❌ Uneven student preparation
- ❌ Massive knowledge loss every semester
- ❌ Steep learning curves for new students
- ❌ Fragile continuity between cohorts
- ❌ Repeated reinvention of processes

FRAMES helps programs:
- ✅ **Retain knowledge** across cohorts
- ✅ **Coordinate** effectively across teams
- ✅ **Onboard** new students efficiently
- ✅ **Understand** where systems are strong or fragile

### Theoretical Foundations
1. **Nearly Decomposable Architecture** (Herbert Simon) - Models semi-independent organizational modules
2. **Hybrid Autonomous Organizations** (Champenois & Etzkowitz) - University space labs in boundary spaces
3. **OATutor Pedagogy** - Scaffolding, hint pathways, validation steps
4. **Knowledge Transfer & Organizational Resilience** - Codified vs tacit knowledge tracking

---

## 🛠️ SETUP INSTRUCTIONS

### Step 1: Environment Check
```bash
# Check Ruby version (need 2.7.0+)
ruby --version

# Check gem
gem --version

# Check git
git --version
```

### Step 2: Install Ruby (if needed)

**For Codespace (Ubuntu/Debian):**
```bash
sudo apt-get update
sudo apt-get install -y ruby-full build-essential zlib1g-dev
```

**For Local Windows (if absolutely necessary):**
- Download RubyInstaller with Devkit from https://rubyinstaller.org/downloads/
- Install Ruby+Devkit 3.3.x (x64)
- Run `ridk install` and choose option 3
- This is ~1GB download

**For macOS:**
```bash
brew install ruby
```

### Step 3: Install Jekyll and Bundler
```bash
gem install jekyll bundler
```

### Step 4: Create Jekyll Site
```bash
# Navigate to the repository root
cd /workspaces/Portfolio  # or your local path

# Create Jekyll site (--force allows creation in non-empty directory)
jekyll new . --force
```

### Step 5: Configure for GitHub Pages

Edit `_config.yml` and update/add these lines:
```yaml
title: FRAMES - Framework for Research & Analytics in Mission Engineering Systems
email: eosborn@cpp.edu
description: >-
  A multi-university research platform for space mission programs combining
  educational research, systems theory, AI architecture, and engineering pedagogy.
baseurl: "/Portfolio"
url: "https://lizo-roadtown.github.io"
github_username: Lizo-RoadTown

# Build settings
markdown: kramdown
theme: minima
plugins:
  - jekyll-feed
```

### Step 6: Test Locally
```bash
# Build and serve the site
bundle exec jekyll serve --host 0.0.0.0

# You should see output like:
# Server address: http://0.0.0.0:4000/Portfolio/
# Server running... press ctrl-c to stop.
```

**In Codespace:** Click the "Open in Browser" prompt
**Locally:** Navigate to `http://localhost:4000/Portfolio/`

### Step 7: Commit and Push
```bash
git add .
git commit -m "Initial Jekyll site setup for FRAMES portfolio"
git push -u origin main
```

### Step 8: Enable GitHub Pages

1. Go to https://github.com/Lizo-RoadTown/Portfolio/settings/pages
2. Under "Source", select:
   - **Branch:** `main`
   - **Folder:** `/ (root)`
3. Click **Save**
4. Wait 1-2 minutes for deployment
5. Visit `https://lizo-roadtown.github.io/Portfolio/`

---

## 📝 CONTENT TO SHOWCASE

### Primary Content Source
The FRAMES project lives at: `C:\Users\LizO5\Frames-Python\FRAMES-Python\`

### Key Documentation Files to Reference
Located in the FRAMES-Python repository:

**System Architecture:**
- `README.md` - Comprehensive project overview (560 lines)
- `.github/copilot-instructions.md` - Project overview and workflows
- `canon/system_overview_v_2.md` - Full system design
- `canon/DATABASE_SCHEMA.md` - Database structure
- `canon/STUDENT_LMS.md` - Student application spec
- `canon/RESEARCHER_PLATFORM.md` - Research platform spec

**Agent System:**
- `canon/agent_interaction_script_v_2.md` - Agent coordination protocols
- `AGENTIC_FLOW_ARCHITECTURE.md` - Agent flow details
- `AGENT_OMEGA_ARCHITECTURE.md` - Agent architecture
- `FIVE_AGENT_SYSTEM_ROLES.md` - Agent roles explained

**Educational Framework:**
- `canon/module_definition_v_2.md` - Module structure specification
- `docs/EDUCATIONAL_FRAMEWORK.md` - LMS module philosophy

**Database & Backend:**
- `backend/db_models.py` - SQLAlchemy models (20+ tables)
- `backend/app.py` - Main Flask API (2071 lines, 50+ routes)
- `backend/energy_engine.py` - Risk factor calculation engine

### Content Structure for Portfolio

Create the following pages:

#### 1. **Home Page** (`index.md`)
- Project overview
- Key statistics (8 universities, 37+ tables, 3 agents)
- Visual architecture diagram
- "Why FRAMES Exists" section
- Link to GitHub repo

#### 2. **About Page** (`about.md`)
- Detailed project description
- Theoretical foundations
- Partner universities
- Contact information (eosborn@cpp.edu)

#### 3. **Architecture Page** (`architecture.md`)
- Five-layer system architecture
- Technology stack details
- Database schema overview
- Agent system explanation

#### 4. **Applications Page** (`applications.md`)
- Student LMS (React PWA)
- Team Lead Workspace (Notion)
- Researcher Platform (Jupyter + MLflow + Superset)

#### 5. **Documentation Page** (`documentation.md`)
- Links to canonical docs
- Developer resources
- Research references

#### 6. **Roadmap Page** (`roadmap.md`)
- Current features
- Planned enhancements
- Research goals

---

## 🎨 CUSTOMIZATION RECOMMENDATIONS

### Theme Options
The default `minima` theme is clean, but consider:
- **just-the-docs** - Great for documentation-heavy sites
- **minimal-mistakes** - Professional portfolio theme
- **academicpages** - Designed for academic portfolios

To change theme:
```ruby
# In _config.yml
theme: jekyll-theme-minimal
# or for GitHub Pages remote themes:
remote_theme: pages-themes/minimal@v0.2.0
```

### Color Scheme
Match FRAMES branding from README badges:
- Python: `#3776AB`
- React: `#61DAFB`
- Flask: `#000000`
- PostgreSQL: `#4169E1`
- Status Green: `#4CAF50`

### Recommended Plugins
Add to `_config.yml`:
```yaml
plugins:
  - jekyll-feed
  - jekyll-seo-tag
  - jekyll-sitemap
  - jekyll-github-metadata
```

Install:
```bash
bundle add jekyll-seo-tag jekyll-sitemap jekyll-github-metadata
```

---

## 📊 CONTENT EXTRACTION TASKS

### From README.md
- [ ] Extract project badges
- [ ] Extract "What Is FRAMES?" section
- [ ] Extract "Why FRAMES Exists" section
- [ ] Extract architecture diagram (convert to Mermaid or SVG)
- [ ] Extract stakeholder table
- [ ] Extract tech stack details

### From Canonical Docs
- [ ] Extract system overview from `canon/system_overview_v_2.md`
- [ ] Extract database schema highlights from `canon/DATABASE_SCHEMA.md`
- [ ] Extract agent roles from agent docs
- [ ] Extract module structure from `canon/module_definition_v_2.md`

### From Code
- [ ] Count total lines of code
- [ ] List main technologies used
- [ ] Document API endpoints (from `backend/app.py`)
- [ ] Document database models (from `backend/db_models.py`)

---

## 🔧 TROUBLESHOOTING

### Common Issues

**Issue:** `ruby: command not found`
**Solution:** Install Ruby (see Step 2)

**Issue:** `Could not locate Gemfile or .bundle/ directory`
**Solution:** Run `bundle init` then `bundle add jekyll`

**Issue:** GitHub Pages not updating
**Solution:** Check Actions tab for build errors, ensure `baseurl` and `url` are correct

**Issue:** Site works locally but broken on GitHub Pages
**Solution:** Verify `baseurl: "/Portfolio"` in `_config.yml`, use `{{ site.baseurl }}` prefix for all internal links

**Issue:** Theme not loading
**Solution:** Use `remote_theme` instead of `theme` for GitHub Pages compatibility

---

## 📚 USEFUL REFERENCES

### Jekyll Documentation
- Official docs: https://jekyllrb.com/docs/
- GitHub Pages guide: https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll
- Liquid templating: https://shopify.github.io/liquid/

### FRAMES Resources
- Main README: `../Frames-Python/FRAMES-Python/README.md`
- Canonical docs: `../Frames-Python/FRAMES-Python/canon/`
- Backend code: `../Frames-Python/FRAMES-Python/backend/`
- Database models: `../Frames-Python/FRAMES-Python/backend/db_models.py`

### Design Inspiration
- https://academicpages.github.io/
- https://jekyllthemes.io/
- https://github.com/topics/portfolio-website

---

## ✅ SUCCESS CRITERIA

Your setup is complete when:
- [ ] Jekyll builds without errors (`bundle exec jekyll build`)
- [ ] Site serves locally at `http://localhost:4000/Portfolio/`
- [ ] Site is live at `https://lizo-roadtown.github.io/Portfolio/`
- [ ] Home page displays FRAMES project overview
- [ ] Navigation works between pages
- [ ] Styling looks professional
- [ ] All internal links work (use `{{ site.baseurl }}`)

---

## 📧 CONTACT & HANDOFF

**Project Lead:** Elizabeth Osborn
**Email:** eosborn@cpp.edu
**Institution:** Cal Poly Pomona
**GitHub:** https://github.com/Lizo-RoadTown

**Next Steps After Basic Setup:**
1. Create custom layout based on FRAMES branding
2. Add project screenshots (if available)
3. Write detailed content for each page
4. Add analytics tracking (Google Analytics)
5. Set up custom domain (if desired)
6. Create blog section for project updates

---

## 🤖 AGENT HANDOFF NOTES

**Context:** This Jekyll site is being created to showcase the FRAMES project, which is a sophisticated multi-university research platform. The content should emphasize:
1. **Academic rigor** - This is serious research work
2. **Multi-stakeholder value** - Students, faculty, researchers, developers all benefit
3. **Technical sophistication** - Multi-agent AI, complex database, full-stack architecture
4. **Real-world impact** - Solving actual problems in university engineering programs

**Tone:** Professional, academic, but accessible. Avoid jargon where possible. Use visuals to explain complex concepts.

**Priority Content:**
1. Clear explanation of what FRAMES does and why it matters
2. Visual architecture diagram
3. Partner universities and scale (8 universities is impressive)
4. Technical stack and capabilities
5. Links to live demo or screenshots (if available)

**Files to Create First:**
1. `index.md` - Home page with overview
2. `about.md` - Detailed "what and why"
3. `architecture.md` - Technical deep dive
4. `_config.yml` - Site configuration

**Design Considerations:**
- Use the badge colors from README for consistency
- Include university logos if available
- Create a visual representation of the 5-layer architecture
- Add "Layer 2" expandable sections like in the README for progressive disclosure

---

**Generated:** 2025-01-30
**For Repository:** https://github.com/Lizo-RoadTown/Portfolio.git
**Source Project:** FRAMES-Python (C:\Users\LizO5\Frames-Python\FRAMES-Python)
