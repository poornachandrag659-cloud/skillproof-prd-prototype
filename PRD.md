# Product Requirements Document (PRD): SkillProof

- **Version:** 1.0
- **Status:** Portfolio concept / prototype
- **Product type:** Responsive web app
- **Primary audience:** Students and early-career professionals
- **Platform:** Web
- **Owner:** Product portfolio project

## 1. Executive summary

SkillProof is an evidence-based skills portfolio that helps students and early-career professionals present what they can do, not just list technologies on a résumé. Users create skill cards and attach supporting artifacts such as project links, GitHub repositories, certificates, or work samples. A profile preview makes the information easier to scan.

The MVP is a frontend prototype. It records information locally and does not independently verify identity, artifact ownership, or skill proficiency.

## 2. Problem statement

Early-career candidates often list skills such as Python, SQL, or product thinking without showing a consistent, easy-to-review proof point for each claim. Recruiters and interviewers may have limited time to find relevant evidence across multiple links and documents.

**Problem hypothesis:** A structured, evidence-linked profile can help candidates communicate their skills more clearly and help reviewers locate relevant examples faster.

This is a hypothesis to validate, not a proven market finding.

## 3. Target users and personas

### Persona A — Student / early-career candidate
- **Context:** Applying for internships or entry-level roles.
- **Need:** Organize projects, certificates, and examples around specific skills.
- **Pain points:** Evidence is scattered across GitHub, course platforms, and résumé files; unsure what proof to show.
- **Desired outcome:** A concise profile that makes relevant work easy to scan.

### Persona B — Hiring reviewer / interviewer
- **Context:** Reviewing applicants with limited time.
- **Need:** Quickly find examples relevant to a role.
- **Pain points:** Skills lists can be hard to evaluate; evidence may require multiple clicks.
- **Desired outcome:** Clear skill-to-evidence mapping without exaggerated verification claims.

## 4. Goals and non-goals

### Goals
1. Enable a first-time user to add one skill and supporting evidence in under 3 minutes during usability testing.
2. Have at least 70% of usability-test participants successfully create a skill card without facilitator help.
3. Have at least 4 of 5 reviewer-test participants report that the profile preview makes evidence easier to locate than a plain skills list.

These are proposed validation targets, not measured results.

### Non-goals
- Automatically proving that a user owns a GitHub account or certificate.
- Ranking candidates or predicting hiring outcomes.
- Replacing a résumé, LinkedIn, applicant tracking system, or formal credential provider.

## 5. User stories

1. As a student, I want to add a skill and a supporting project link so that I can show where I used the skill.
2. As a candidate, I want to group evidence under individual skills so that reviewers can understand the connection quickly.
3. As a candidate, I want to see which skills still need evidence so that I can improve my profile before sharing it.
4. As a reviewer, I want to scan a clean profile preview so that I can locate relevant examples with fewer clicks.
5. As a user, I want to edit or remove a skill card so that my profile stays accurate and current.

## 6. MVP scope

### Included
- Sample candidate profile
- Create skill card with skill name, level, evidence type, URL, and short note
- Status labels: Draft, Evidence added, Ready to share
- Search and status filtering
- Edit and delete cards
- Profile preview
- Local browser persistence
- Reset-to-demo action
- Responsive desktop/mobile layout and empty states

### Out of scope
- Accounts, authentication, cloud sync, and collaboration
- AI-generated skill scoring or résumé ranking
- Automated verification of credentials or external links
- Recruiter messaging, job matching, payments, and analytics backend

## 7. Functional requirements

| ID | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| FR-1 | View dashboard | P0 | Dashboard displays skill cards and summary counts |
| FR-2 | Add skill | P0 | Valid skill name creates a card |
| FR-3 | Attach evidence reference | P0 | User can choose evidence type and add a URL/note |
| FR-4 | Edit and delete | P0 | User can update or remove a card after confirmation |
| FR-5 | Search and filter | P1 | Search matches skill names and notes; status filter narrows cards |
| FR-6 | Profile preview | P1 | Preview shows skill names and user-submitted evidence references |
| FR-7 | Persist locally | P1 | Reloading the same browser retains data |
| FR-8 | Reset demo | P1 | User can restore sample cards after confirmation |

## 8. UX requirements

- Use plain language and avoid implying external verification.
- Make the primary action (“Add a skill”) visually prominent.
- Keep forms short and provide inline validation.
- Display empty states when no cards match a search.
- Use semantic HTML, keyboard-accessible controls, visible focus states, and responsive layouts.
- External evidence links should open in a new tab with safe `rel` attributes.

## 9. Data model

### SkillCard
- `id`: unique string
- `name`: required string
- `level`: Beginner, Intermediate, or Advanced (self-reported)
- `evidenceType`: Project, GitHub, Certificate, Work sample, or Other
- `url`: optional URL supplied by user
- `note`: optional description
- `status`: Draft, Evidence added, or Ready to share
- `createdAt`: ISO timestamp

### Privacy
The prototype stores cards in the browser's local storage. Do not enter private, confidential, or sensitive personal information. A production version would need explicit consent, deletion/export controls, access controls, retention rules, and a threat model.

## 10. Success metrics

### North-star candidate metric
**Evidence-backed profile completion rate:** percentage of activated users who create at least 3 skill cards and attach at least one evidence reference to each.

### Supporting metrics
- Activation: percentage adding their first skill within the first session.
- Time to first evidence: median time from opening the app to adding an evidence reference.
- Task success: percentage completing a skill card without help.
- Reviewer usability: time taken to locate a relevant evidence item in a moderated test.
- Trust comprehension: percentage of users who correctly understand that submitted evidence is not automatically verified.

### Guardrails
- Users must not confuse “evidence added” with “credential verified.”
- Track qualitative confusion and accessibility issues during tests.
- Do not use profile completion as a proxy for candidate quality.

## 11. Risks and mitigations

| Risk | Mitigation |
|---|---|
| Users assume claims are verified | Label references as user-submitted; avoid verification badges |
| Low-quality or misleading evidence | Future version could add reporting and transparent review controls |
| Privacy concerns | Keep prototype local; provide delete/reset; avoid sensitive data |
| Low candidate motivation | Test value with students before building more features |
| Reviewers ignore the profile | Run a comparative usability test against a plain skills list |

## 12. Release plan

### Prototype (current)
Static frontend, sample data, local persistence, and profile preview.

### Validation
Conduct 5 candidate usability sessions and 5 reviewer sessions. Record task completion, time on task, comprehension, and qualitative feedback.

### Post-validation
Prioritize only validated needs. Potential follow-on work: shareable hosted profiles, account management, privacy controls, link checks, and reviewer feedback — each subject to security and trust design.

## 13. Open questions to validate
- Which evidence types are most useful to reviewers?
- Is a standalone profile useful, or is an exportable résumé section more valuable?
- What wording best distinguishes submitted evidence from verified credentials?
- Would candidates maintain the profile after completing an application?
