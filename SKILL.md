---
name: oracle-personas
description: The persona library — browse, add, and validate the named-master profiles that /oracle-facet, /debate and /แปลงร่าง read from. Use when user says "personas", "oracle-personas", "add a persona", "who is in the library", "list masters", "validate personas", or wants to create or edit a master profile. Do NOT trigger for running a persona on work (use /oracle-facet), a panel (use /debate), or adopting a method (use /แปลงร่าง).
argument-hint: "[list | show <name> | add <name> | validate]"
---

# /oracle-personas — the library

> The **noun**. `/oracle-facet` runs one, `/debate` runs several, `/แปลงร่าง`
> adopts one's method. This is where they read from.

## Usage

```
/oracle-personas                 # the index
/oracle-personas show Rams       # one profile
/oracle-personas add <name>      # research and write a new one
/oracle-personas validate        # schema + grounding lint
```

## Where it lives

Clone anywhere and point the consumers at it:

```bash
git clone https://github.com/Soul-Brews-Studio/oracle-personas ~/.claude/personas
# or, so /oracle-facet's default discovery finds it:
git clone https://github.com/Soul-Brews-Studio/oracle-personas \
  ~/.claude/skills/oracle-personas
export FACET_PROFILES=~/.claude/personas/personas
```

## list

`node scripts/build.mjs` regenerates `INDEX.md` and `personas.json`, then read
the index. Never hand-count — the generator is the source of truth.

## show

Read `personas/<slug>.md` and print it. Do not summarise from the index; the
index is derived and lossy.

## add — the part that matters

Adding a persona is research, not typing. Follow `TEMPLATE.md` and:

1. **Ground it first.** Books, talks, shipped work, documented decisions.
   WebSearch if your knowledge is thin, regional, or recent. Fill
   `grounded_in:` with what you actually used — a profile with an empty
   `grounded_in` is a rumour.
2. **The one trait is the test.** If you cannot write it in one sentence, you
   do not know them well enough yet. Stop and read more.
3. **Method section is optional and should stay that way.** Most artists had
   taste, not a loop. An invented method is worse than none.
4. **Quotes: real and attributable, or the section says so.** Mark uncertain
   wording `(paraphrase)`. A fabricated quote attributed to a real person is
   the one unrecoverable failure of this library.
5. **Blind spots are mandatory.** A persona with no blindness is a fan letter,
   and it will give confident bad advice.
6. **"Not this" guards the caricature.** Name the lazy version and why it is
   wrong.
7. Run `node scripts/build.mjs` — it fails the commit if the schema is off.

## Living people

Prefer documented positions over inference. Do not attribute opinions on
current events to anyone. If a persona would need an opinion they have never
expressed, the profile is out of scope — say so rather than inventing it.

## Rule 6

These are lenses, not simulations. Nothing here authorises writing in first
person as a real person. Every consumer of this library carries that guard;
this file states the source of it.

## Rules

1. **`grounded_in` is required.** No sources, no persona.
2. **Blind spots are required.**
3. **Real quotes or an explicit note that there are none.**
4. **Method only where a real method existed.**
5. **`INDEX.md` and `personas.json` are generated.** Never hand-edit.
6. **MIT licensed** — so it can actually be reused. Do not paste in profiles
   from repos that declare no licence.
