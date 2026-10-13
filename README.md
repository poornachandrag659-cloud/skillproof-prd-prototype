# SkillProof — AI-Assisted Skill Evidence Portfolio

> A product-management portfolio project: a complete PRD plus a functional, frontend-only prototype for presenting skills with supporting evidence.

SkillProof helps students and early-career professionals turn vague skill claims into structured, reviewable evidence cards. Users can add a skill, describe evidence (project, certificate, code repository, or work sample), track its review status, and preview a shareable public profile.

**Important:** This prototype does not independently verify credentials, authenticate third-party links, or prove that a person owns an artifact. “Evidence added” means the user supplied a reference; it is not a verified credential.

## Project links
- Product requirements: [`PRD.md`](PRD.md)
- Prototype: open [`prototype/index.html`](prototype/index.html) in a browser
- Product assumptions and validation plan: [`docs/validation-plan.md`](docs/validation-plan.md)
- Metrics: [`docs/metrics.md`](docs/metrics.md)

## MVP features
- Demo profile with seeded example skills
- Add a skill and supporting evidence
- Status tracking: Draft, Evidence added, Ready to share
- Search/filter skills
- Profile preview modal
- Local browser persistence via `localStorage`
- Responsive layout for desktop and mobile

## Run locally
No build tools, API keys, database, or backend are required.

1. Download or clone this repository.
2. Open `prototype/index.html` in a modern browser.
3. Add skills and evidence. Your changes are stored in that browser's local storage.
4. Use **Reset demo** to restore the sample data.

For best results, run a static server from the repository root:
```bash
python -m http.server 8000
```
Then open `http://localhost:8000/prototype/`.

## Tech stack
- HTML5
- CSS3
- Vanilla JavaScript
- `localStorage` for demo persistence

## Product decisions
- **Trust over inflated claims:** evidence is user-submitted and clearly labeled as such.
- **Narrow MVP:** no sign-in, AI scoring, scraping, third-party verification, or backend.
- **Portfolio-first:** the prototype demonstrates the core workflow without collecting sensitive personal data.

## Known limitations
- Data stays in the current browser and is not synced across devices.
- Evidence links are not fetched or checked.
- Anyone with access to the browser profile may see locally stored demo data.
- This is a clickable concept prototype, not a production security or identity system.

## Suggested next steps
1. Interview 5 students and 3 internship reviewers.
2. Test whether evidence cards help reviewers assess a skill faster than a plain skills list.
3. Add privacy controls and link validation only after validating the core need.
4. If the concept is validated, design a backend, authentication, abuse reporting, and a transparent review policy.

## Resume bullet
Designed a PRD and built a responsive, interactive prototype for SkillProof, an evidence-based skills portfolio; defined MVP scope, user stories, and measurable activation and review-efficiency metrics.

## License
MIT — see [`LICENSE`](LICENSE).
