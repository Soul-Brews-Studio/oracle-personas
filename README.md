# oracle-personas

A library of named-master profiles — the **data layer** for persona-driven
Claude Code skills.

```
/oracle-facet   runs ONE persona as a lens on your work
/debate         runs 2–4 as a panel
/แปลงร่าง       adopts one persona's METHOD and builds with it
/oracle-personas  ← you are here: browse, add, validate
```

## Install

```bash
git clone https://github.com/Soul-Brews-Studio/oracle-personas ~/.claude/personas
export FACET_PROFILES=~/.claude/personas/personas
```

`/oracle-facet` also auto-discovers `~/.claude/personas`, so the export is
optional.

## What a persona is

One Markdown file per master. The schema is in [`TEMPLATE.md`](TEMPLATE.md),
and three things are non-negotiable:

- **`grounded_in:`** — where this came from. No sources, no persona.
- **The one trait** — in a single sentence. If you can't, you don't know them
  well enough yet.
- **Blind spots** — what this lens gets wrong. A persona without one is a fan
  letter, and it gives confident bad advice.

Two more that keep it honest:

- **Quotes are real and attributable, or the section says there are none.**
  A fabricated quote attributed to a real person is the one unrecoverable
  failure here.
- **`## Method` is optional.** Most artists had taste, not a loop. An invented
  method is worse than none.

## These are lenses, not people

Nothing in this library authorises writing in first person as a real person.
Named influences describe the angle taken — not endorsement, not expertise
transferred, and not the person's actual opinion. Nobody listed here has
reviewed or approved anything.

## Adding one

```bash
cp TEMPLATE.md personas/their-name.md
$EDITOR personas/their-name.md
node scripts/build.mjs        # regenerates INDEX.md + personas.json, lints schema
```

The build fails if `grounded_in` is empty, a required section is missing, or
the Quotes section is present but blank.

## Index

See [`INDEX.md`](INDEX.md) — generated, don't hand-edit.

## Licence

MIT. Reuse it, fork it, ship it.
