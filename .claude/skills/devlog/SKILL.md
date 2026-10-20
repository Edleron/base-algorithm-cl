---
name: devlog
description: Write or extend Edleron's developer log (Geliştirici Günlüğü) for the day's work in this project, at `edleron/daily/YYYY-MM-DD.md`. Use whenever a devlog, daily log, günlük, "devlog yaz", "gün sonu", an end-of-day summary or a dated note is asked for. Carries the date rule — work done on a Saturday or Sunday is logged under the previous Friday's date, without asking or warning — plus where the file goes and how it is laid out.
---

# Devlog (Geliştirici Günlüğü)

Same system as Edleron's company repos (`orion/doc/edleron/01-daily/` in cursed-crown-frontend). The files are
collected into Edleron's second brain (hub-brain → `valar/04-habits/<gün>/`) by
`node scripts/valar-habits.mjs collect`, which only picks files named exactly `YYYY-MM-DD.md`.

## The date rule — apply it silently

- **If Edleron has not said the date and time the work started (and ended), ask for them first** — one short
  question, before writing. Do not take them from the system clock or the commits on your own.
- **A session that runs past midnight belongs to the day it started.** Started Tuesday, ran to 04:00 Wednesday →
  Tuesday's devlog.
- **Saturday or Sunday work is logged under the previous Friday** — the Friday right before that weekend
  (Saturday → one day back, Sunday → two days back), never a Friday a week earlier. First take the start day,
  then apply the weekend rule to it. Weekend work needs no times.
- Once the date is known, apply the rules silently: do not ask which date to use and do not point out that it
  differs from the real date. Compute the weekday from the date, never assume.

## Where it goes

- `edleron/daily/YYYY-MM-DD.md` (ISO date, so the folder sorts by date). Nothing else in that folder may be named like a
  date: plans, applications and notes get a different name (e.g. `plan-YYYY-MM-DD.md`), or the collector takes
  them as a day's log.
- Days without work get no file.
- **If the file already exists, add to it** (a new block under "Ne yaptım", updated tables and metrics); do not
  overwrite what is there.

## Layout (match the previous days' files — read the latest one before writing)

Turkish, technical terms in English, short sentences, first person, numbers as measured:

```markdown
# Geliştirici Günlüğü — DD.MM.YYYY

> Start time and what the day was about, in two or three lines.
> Gaps since the last entry are mentioned here ("X'ten beri ara vermiştim").
>
> **Gün sonunda:** the outcome in one or two sentences.

## Gün sonunda durum
| Ne | Hali |   ← the state at the end: branch, versions, what is done, what is waiting

## Ne yaptım (sırasıyla)
### 1. … (time range)   ← each block: what, why, how it was checked, the result; own mistakes named plainly
### 2. …

## Açık kararlar (Edleron)    ← numbered; what only Edleron can decide
## Yarın                       ← the next steps (after a Friday: "Pazartesi")
## Metrik                      ← commit counts per block, items done, checks run; "push yok" unless pushed
```

Sections with nothing in them are left out, never renamed.

## Facts and voice

- Facts come from the work itself: `git log` for the period (counts per block), `git status` / `git diff --stat`
  for uncommitted work, the conversation (decisions, things tried and abandoned, what broke), decision records.
  Nothing estimated is written as measured.
- Commits: list the important ones by hash in the tables.
- Owner's voice, plain. No praise words, no "başarıyla". Mistakes and reversals are written as they happened.
- No code blocks longer than one line; backticks for identifiers. 40 to 120 lines.

## Finish

- Show Edleron the path and a short preview.
- The devlog file goes into git with the day's work. Commit it only when Edleron asks for a commit; push only
  when Edleron says so.
