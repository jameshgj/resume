# Resume Website — Claude Code Context

Interactive resume website for **James H.G. Jones** (Product Lead), hosted on GitHub Pages.
Live: https://jameshgj.github.io/resume/ · Repo: https://github.com/jameshgj/resume (branch `main`)

James updates his resume by talking to Claude. Every content change must update BOTH the
interactive site and the printable resume, then push to `main` (auto-deploys via Pages).

## Files (these three are everything)
- `index.html` — THE website. Single file, all HTML/CSS/JS inline. Footer holds the version number.
- `resume-template.html` — THE printable resume. Embedded in the site as a live iframe preview,
  and printed by the "Save as PDF" button. NO version number lives here.
- `James_Jones_Resume.pdf` — legacy static PDF, no longer linked from the site. Ignore unless asked.

## Download mechanism (current)
Site shows `resume-template.html` in an iframe (`#resumeFrame`). The "Save as PDF" button calls
`resumeFrame.contentWindow.print()` — the browser print dialog generates the PDF on demand.
There is no static PDF to regenerate.

## Update workflow (every resume change)
1. Edit `index.html` (interactive site) AND `resume-template.html` (printable resume) — keep in sync.
2. Bump the footer version in `index.html`: `v1.XX` → increment XX by exactly 1.
3. Confirm the new version number with James before pushing.
4. Commit and push to `main`.

## Versioning (important to James)
- Format `v1.XX`, increment by +1 only (never jump — James dislikes "stupid high" numbers).
- Always update the footer version in `index.html` and state the number in your reply when pushing.
- Current version: see `index.html` footer (`foot-version`). As of this file: v1.16. Next: v1.17.

## Push
James prefers pushing from the command line with git. The push URL needs his GitHub PAT —
it is NOT stored in this repo for security. Get it from James's project config / local handoff doc:
    git push https://jameshgj:<PAT>@github.com/jameshgj/resume.git main

## Content source material (not in repo)
Resume bullets come from James's Google performance notes (accomplishments + peer quotes),
kept locally outside this repo. Keep non-sanitized versions OUT of the public repo.
