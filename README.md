# Suno v6 Song Studio

A browser-based workstation for creating Suno music-style instructions and lyric-writing prompts.

## Version numbering and commit policy

**Every commit to `main` must increment the app's version number by 0.001 (one thousandth).**

- Use the format `MAJOR.MINOR.PATCH`, with a **three-digit patch field**.
- Keep the major and minor numbers unchanged for routine commits; increment the final three-digit field by exactly one for **each commit**, including documentation, bug fixes, and interface changes.
- For example: `v1.1.000` → `v1.1.001` → `v1.1.002`.
- If the patch field reaches `999`, increment the minor number and reset the patch field to `000`.
- Before committing, update the visible version badge in `index.html` (and any other version references) so it matches the new version.
- Include the version in the commit message where practical, e.g. `v1.1.003 — Improve tooltip behavior`.
- When preparing multiple commits, advance the version once per commit, not once per work session or feature.

**Baseline:** The existing `v1.1` UI label corresponds to `v1.1.000` prior to adopting this policy. The first commit after adopting the policy is `v1.1.001`.

> Note: This is a repository workflow rule. GitHub does not enforce or perform version increments automatically unless a separate workflow or hook is installed.
