# Riposte des programmes

Source of a public page (GitHub Pages, Jekyll) and of the riposte emails. It copies the structure of the Gen-AI living review: a page with newest entries on top, a daily routine, a GitHub Release per update (GitHub emails watchers), and a form to submit items. Entries are programme proposals of the RN and LFI, each with 2 to 3 ripostes in Édouard's tone, written for a vertical 30-second video.

| File | What it holds | Who edits it |
|---|---|---|
| `_includes/latest.md` | the entries, newest first | daily routine (or by hand) |
| `ROUTINE.md` | instructions the daily routine follows, entry format and style | by hand |
| `contributeurs.txt` | GitHub accounts whose submissions are processed | by hand |
| `traites.txt` | submissions already processed | routine |
| `.github/workflows/release-notes.yml` | publishes a Release with the new entries on each push | by hand |
| `.github/ISSUE_TEMPLATE/proposition.yml` | form "Proposer une proposition à analyser" | by hand |

## How it works
1. Every morning a scheduled routine reads `ROUTINE.md`: it processes submissions, checks the RN and LFI programme documents for new or changed proposals, verifies each figure at its source and writes up to 3 entries.
2. The push to `main` runs `release-notes.yml`, which publishes a GitHub Release holding only the new entries.
3. To receive them by email: open the repository on GitHub, "Watch", "Custom", tick "Releases". A GitHub account is needed. Release history: `/releases`.
4. Submissions: the issue form. Only accounts in `contributeurs.txt` are processed.

## Status (not yet deployed)
Local scaffold only. Nothing has been pushed and no GitHub repository, routine or schedule exists. To go live, three decisions are needed: (1) create the public GitHub repository and replace `ajoly35` in `index.md` and `ROUTINE.md`; (2) enable GitHub Pages on `main`; (3) create the daily routine at https://claude.ai/code/routines with the prompt "Follow ROUTINE.md in this repository", with permission to push to `main`.

## Differences from the existing `riposte-economique` repository
That repository emails through SMTP with repository secrets and covers all candidates in four steps. This one uses Releases (no mail server, no secret), covers the RN and LFI programmes, and gives each proposition three short-video ripostes.
