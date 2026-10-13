# SkillProof — AI-Assisted Skill Evidence Portfolio

SkillProof helps students and early-career professionals connect skill claims to supporting projects, GitHub repositories, certificates, and work samples.

> **Trust note:** This frontend prototype does not verify credentials, identity, artifact ownership, or proficiency. Evidence is user-submitted and is not a verified credential.

## Project files

- [Product requirements](PRD.md)
- [Interactive prototype](prototype/index.html)
- [Validation plan](validation-plan.md)
- [Metrics](metrics.md)

## Run locally

No build tools, API keys, database, or backend are required.

1. Clone or download the repository.
2. Open `prototype/index.html` in a modern browser; or run a local static server from the repository root:

   ```bash
   python -m http.server 8000
   ```

3. Open `http://localhost:8000/prototype/`.

## MVP features

- Demo profile with sample skills
- Add, edit, and delete skill cards
- Self-reported level, evidence type, URL, notes, and status
- Search and status filtering
- Profile preview
- Browser-local persistence using `localStorage`
- Reset-to-demo action
- Responsive desktop and mobile layout
- URL protocol validation and safe text rendering

## Tech stack

- HTML5
- CSS3
- Vanilla JavaScript
- `localStorage` for demo persistence

## Limitations

- Data remains in the current browser and does not sync across devices.
- Evidence URLs are not fetched or verified.
- Anyone with access to the same browser profile may see locally stored data.
- This is a portfolio prototype, not a production identity or security system.
- Do not enter confidential or sensitive personal information.

## Suggested validation

Test skill creation, editing, deletion, search, status filters, URL validation, reload persistence, reset confirmation, profile preview, empty states, keyboard controls, and mobile layout.

## License

MIT — see [LICENSE](LICENSE).
