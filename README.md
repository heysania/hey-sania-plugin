# Hey Sania

Curated corpora on the field of impact — regenerative wealth, systems change, ocean
regeneration, bioregions, AI innovation — read by your own Claude, through the same
search the site uses.

This repository is a Claude plugin marketplace holding one plugin. Installing it does
two things at once: it connects Claude to [heysania.ai](https://heysania.ai),
and it teaches it how to read the sources — search across every set before narrowing,
cite what it found, name what the sources do not cover, and never invent an organisation.

## Install

**In claude.ai or the desktop app.** Customize → Plugins → Browse plugins → add this
repository as a marketplace, then install **Hey Sania**. Plugins are on Pro, Max, Team
and Enterprise.

**In Claude Code.**

```bash
claude plugin marketplace add heysania/hey-sania-plugin
claude plugin install hey-sania@hey-sania
```

Either way, Claude sends you to sign in at Hey Sania and approve. It is then given a
token of its own that reads exactly what you read, for an hour at a time, renewing
itself until you take it back on the site's **Add to Claude** page. Nothing to paste.

The connector can land switched off after you approve it — check
**Settings → Connectors** if Claude says it cannot see these sources. If you would
rather skip that step, [heysania.ai/connect](https://heysania.ai/connect) also has the
connector on its own: paste one address, or run `claude mcp add`, and it is live the
moment you approve it — no marketplace, no plugin, just without the skill in chat on
the web.

You need an account. The sources are curated for the organisations they were built for,
and some are open to everyone.

## What it can do

Ask it about the field and it searches every set of sources you can read, not the one
you named. It reads a few hundred feeds a day across a handful of subjects, and every
story carries a summary written for it and a link back to the publication.

It reads. It cannot publish, delete or edit anything, and the one thing it writes on
your behalf — asking the editors to look into a gap — changes nothing anyone can read.
It does not give financial, legal or tax advice, and it will route you to named
organisations and documents rather than answering thinly from the nearest source.

## What is in it

| | |
|---|---|
| `hey-sania/skills/hey-sania/SKILL.md` | How to work the sources well |
| `hey-sania/.mcp.json` | The connector — one HTTP server, OAuth at first use |

The skill is generated from the one the app serves at `/skill/SKILL.md` — not linked,
because that path is behind the sign-in — where a test holds it to the server's actual
tools: it names every one and invents none. That is why this copy is
published rather than hand-written: a skill that describes a tool the server no longer
has is worse than no skill, and a copy taken by hand goes stale the day after it is
taken. Refresh with `claude plugin marketplace update hey-sania`.

## Support

[heysania.ai/connect](https://heysania.ai/connect) is where tokens are
made and revoked, and where a connection is taken back.
