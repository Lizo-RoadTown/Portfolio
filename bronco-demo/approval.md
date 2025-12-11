---
layout: article
title: Approval & Next Steps - BSL Demo
key: page-bsl-demo-approval
permalink: /bronco-demo/approval/
---

<div style="font-size: 0.9em; margin-bottom: 2em;">
<a href="/Portfolio/bronco-demo/implementation/">← 4. Implementation</a> | <strong>5. Approval & Next Steps</strong>
</div>

---

# Approval & Next Steps

This section outlines the decision framework, approval process, and immediate actions to launch FRAMES at Bronco Space Lab.

---

## Decision Summary

### The Question

**Should Bronco Space Lab deploy FRAMES to predict mission success and prevent knowledge loss?**

### The Evidence

**Problem:** BSL loses ~30% of institutional knowledge each graduation, team leads spend 10+ hrs/week on repetitive training, interface failures emerge too late to fix.

**Solution:** FRAMES maps organizational structure, predicts vulnerabilities 3-6 months in advance, automates onboarding, and manages structured handoffs.

**Investment:** ~$35K over 12 months (phases 1-3)

**Return:** Team lead time savings (~$8K/semester), avoided schedule slips ($15-30K/incident), improved mission success probability, research publication, grant funding opportunities.

**Risk:** Low-medium technical complexity, mitigated by phased approach with exit ramps.

---

## Decision Framework

### Option 1: Full Approval (Recommended)

**Commit to all 3 phases with checkpoints.**

- **Phase 1 (Months 1-3):** Foundation + pilot ($6.4K)
  - *Checkpoint:* If pilot shows <30% improvement, reassess Phase 2
- **Phase 2 (Months 4-6):** Expansion ($17.5K)
  - *Checkpoint:* If Spring handoffs don't reduce knowledge loss, reassess Phase 3
- **Phase 3 (Months 7-12):** Validation ($11.4K)
  - *Outcome:* Research paper + grant applications

**Why This Option:**
- Maximizes impact (full system deployment)
- Enables research validation (publication + grants)
- Positions BSL as leader in organizational prediction
- Checkpoints allow exit if not working

**Risk:** Higher upfront commitment (~$35K total)

---

### Option 2: Pilot Only

**Approve Phase 1 only, decide on Phase 2/3 after pilot.**

- **Phase 1 (Months 1-3):** Foundation + pilot ($6.4K)
  - *Outcome:* LMS pilot, risk assessment, decision point

**Why This Option:**
- Lower risk (small initial investment)
- Proof of concept before full commitment
- See results before deciding

**Risk:** May not capture full value (onboarding alone doesn't address handoffs or prediction)

---

### Option 3: Defer

**Delay decision pending [specific condition].**

**Why This Option:**
- Resource constraints (personnel, budget)
- Other priorities take precedence
- Need more information

**Risk:** Knowledge loss continues, next graduation cycle loses more expertise, BSL mission risk remains unquantified

---

## Recommended Decision: Option 1 (Full Approval with Checkpoints)

**Rationale:**
- Problem is urgent (Spring 2025 graduations approaching)
- Phased approach mitigates risk
- Research opportunity (NSF/NASA grants)
- BSL becomes case study for other universities

---

## Approval Checklist

Before proceeding, lab director approval required for:

- [ ] **Phase 1 Budget** — $6.4K for foundation + pilot (Months 1-3)
- [ ] **Data Access** — Notion workspace + GitHub organization API credentials
- [ ] **IRB Protocol** — Research participation consent (in progress)
- [ ] **Personnel** — Grad student assignment (20 hrs/week)
- [ ] **Faculty Time** — Lab director review time (2 hrs/week)
- [ ] **Student Participation** — Pilot cohort volunteers (Power team recommended)

**Optional (but helpful):**
- [ ] **Phase 2/3 Budget** — Conditional approval pending Phase 1 success
- [ ] **External Funding** — Support for NSF/NASA grant applications
- [ ] **Multi-University Expansion** — BSL as lead site for partner institutions

---

## Immediate Next Steps (If Approved)

### Week 1: Kickoff

**Actions:**
1. **Technical Setup**
   - Provision Neon PostgreSQL database
   - Configure OpenAI API access
   - Set up development environment

2. **Data Access**
   - Lab director provides Notion admin credentials
   - GitHub organization admin adds API access
   - Elizabeth granted read-only permissions

3. **Personnel**
   - Recruit grad student (ideally someone with Python + React experience)
   - Schedule kickoff meeting with lab director + team leads
   - Identify pilot cohort (Power team recommended)

**Deliverables:**
- Database operational
- MCP servers reading Notion + GitHub
- Grad student onboarded

---

### Weeks 2-4: Team Structure Mapping

**Actions:**
1. **Interviews**
   - 2-hour sessions with each subsystem lead
   - Map team members, roles, expertise
   - Identify interfaces and current health

2. **Data Entry**
   - Populate database with BSL structure
   - Import existing documentation
   - Tag knowledge artifacts

3. **Baseline Assessment**
   - Generate first risk assessment report
   - Identify high-risk interfaces
   - Flag knowledge concentration points

**Deliverables:**
- Complete organizational map
- First risk assessment for lab director review

---

### Weeks 5-8: Student LMS Pilot

**Actions:**
1. **Content Creation**
   - Convert existing BSL documentation to LMS modules
   - Create 3-5 foundational modules (CubeSat basics, BSL mission overview, subsystem intro)
   - Develop competency quizzes

2. **Pilot Deployment**
   - Deploy React PWA to pilot cohort (Power team)
   - Monitor progress, gather feedback
   - Iterate on content and UX

3. **Evaluation**
   - Measure time to productivity vs. historical baseline
   - Survey user satisfaction
   - Identify gaps for Phase 2 expansion

**Deliverables:**
- LMS operational with pilot cohort
- Pilot evaluation report
- Go/no-go decision for Phase 2

---

### Weeks 9-12: Phase 1 Wrap-Up

**Actions:**
1. **Report Findings**
   - Present pilot results to lab director
   - Demonstrate LMS to full team
   - Share risk assessment insights

2. **Decision Point**
   - Evaluate Phase 1 success criteria
   - Decide on Phase 2 commitment
   - Adjust budget/timeline if needed

3. **Prepare Phase 2**
   - If approved: begin Beta agent development
   - If deferred: document lessons learned, pause

**Deliverables:**
- Phase 1 completion report
- Phase 2 readiness (if approved)

---

## Long-Term Vision (Months 13+)

**If FRAMES succeeds at BSL:**

1. **Multi-University Expansion**
   - Deploy at 7 partner universities
   - Comparative analysis across programs
   - Generalize predictive model

2. **Grant Funding**
   - NSF Engineering Education Centers (~$500K-2M)
   - NASA STRI (Space Technology Research Institutes, ~$15M/5 years)
   - Industry partnerships (commercial space companies)

3. **Commercial Licensing**
   - Open-source core platform
   - Paid cloud-hosted version for non-research users
   - Consulting services for implementation

4. **Broader Impact**
   - NASA centers (JPL, Goddard, etc.)
   - Commercial space (SpaceX, Blue Origin, etc.)
   - Any organization with complex emergent tech + rotating personnel

**BSL's Role:**
- Reference implementation site
- Co-author on publications
- Potential royalties/revenue sharing on commercial licensing

---

## Questions & Answers

### "What if Phase 1 doesn't show results?"

**Answer:** Built-in exit ramp. If pilot doesn't reduce onboarding time by ≥30% or students report poor UX, we pause Phase 2, analyze why, and either fix issues or gracefully shut down.

**No sunk cost fallacy—data and learnings still valuable for research.**

---

### "How much lab director time is really required?"

**Answer:**
- **Phase 1:** 2 hrs/week (review reports, approve access)
- **Phase 2:** 3 hrs/week (dashboard review, handoff oversight)
- **Phase 3:** 1 hr/week (check-ins, research collaboration)

**Most work done by Elizabeth + grad student. Lab director provides strategic guidance, not day-to-day execution.**

---

### "What about data privacy and student consent?"

**Answer:**
- IRB protocol already in progress (research ethics approval)
- Students consent before participation (voluntary)
- FERPA-compliant from ground up
- Audit trails on all data access
- Students can request data deletion

**No data shared outside BSL without IRB approval and de-identification.**

---

### "What if predictions are wrong?"

**Answer:**
- Phase 3 explicitly validates accuracy (predicted vs. actual)
- Early expectations: better than random (≥70% accuracy)
- Model improves over time as data accumulates
- Predictions are *support tools*, not replacements for human judgment

**Lab director always makes final decisions—FRAMES provides evidence, not mandates.**

---

### "Can we customize for BSL's specific needs?"

**Answer:** Absolutely. System designed to be adaptable:
- Custom learning modules (BSL-specific procedures)
- Interface definitions (your subsystems, not generic)
- Risk thresholds (what counts as "high risk" for BSL)
- Dashboard widgets (show what lab director cares about)

**Phase 1 mapping captures BSL's unique structure—system molds to you, not vice versa.**

---

### "What happens if Elizabeth leaves or becomes unavailable?"

**Answer:**
- Code is open-source (GitHub: Lizo-RoadTown/FRAMES-Python)
- Documentation comprehensive (architecture, API, setup)
- Grad student trained as backup
- Partner universities can provide continuity
- System designed to run with minimal maintenance once deployed

**Goal: sustainable beyond any single person.**

---

## Approval Signature

**I, [Lab Director Name], approve the following:**

- [ ] **Option 1:** Full deployment (Phases 1-3) with checkpoints
- [ ] **Option 2:** Pilot only (Phase 1), decide later
- [ ] **Option 3:** Defer pending [specific condition]

**Budget Approved:** $__________ (Phase 1: $6.4K recommended)

**Data Access Granted:** [ ] Yes [ ] No

**IRB Consent Process:** [ ] Approved [ ] Pending

**Personnel Assigned:** [ ] Grad student identified [ ] TBD

**Start Date:** __________

**Signature:** _______________________ **Date:** _______

---

## Contact for Questions

**Elizabeth Osborn** | Project Lead
Cal Poly Pomona
[eosborn@cpp.edu](mailto:eosborn@cpp.edu)

**Office Hours:** [Schedule 30-min call](mailto:eosborn@cpp.edu?subject=FRAMES BSL Demo Follow-Up)

---

## Additional Resources

**Full Portfolio Site:** [lizo-roadtown.github.io/Portfolio](/Portfolio/)

**Technical Repository:** [github.com/Lizo-RoadTown/FRAMES-Python](https://github.com/Lizo-RoadTown/FRAMES-Python)

**Research References:**
- Simon, H. A. (1962). The Architecture of Complexity
- Pham, M., et al. (2024). The Any% Method (CubeSat program persistence)
- Champenois & Etzkowitz (2018). Hybrid Autonomous Organizations

**Related Work:**
- [Predictive Model Details](/Portfolio/predictive-model/)
- [For Researchers](/Portfolio/researchers/)
- [For Administrators](/Portfolio/administrators/)

---

<div style="background: #059669; color: white; padding: 2em; border-radius: 8px; margin: 3em 0; text-align: center;">
<h2 style="margin-top: 0; color: white;">Thank You for Reviewing the FRAMES Demo</h2>
<p style="font-size: 1.1em;">This platform represents an opportunity to transform how university space programs predict and prevent mission failures.</p>
<p style="margin-bottom: 0;"><strong>Questions? Let's talk:</strong> <a href="mailto:eosborn@cpp.edu" style="color: white; text-decoration: underline;">eosborn@cpp.edu</a></p>
</div>

---

<div style="text-align: center; margin-top: 3em; font-size: 1.1em;">
<a href="/Portfolio/bronco-demo/">← Back to Demo Home</a> | <a href="/Portfolio/">Main Portfolio Site →</a>
</div>
