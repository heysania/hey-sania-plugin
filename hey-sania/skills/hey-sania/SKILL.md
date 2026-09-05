---
name: hey-sania
description: >-
  Work the Hey Sania connector well — curated corpora on the field of impact
  (regenerative wealth, systems change, ocean regeneration, bioregions, AI innovation, and
  whatever else has been built for the person you are helping), read through its MCP tools.
  Use whenever the Hey Sania connector is attached and the question is about that
  field: who is doing something, who is funding it, what has changed, what the evidence says,
  whether a pitch is new. Teaches the discipline the server expects — search wide before you
  narrow, expand what matters, cite the source, name what the sources do not cover, and ask
  us to look into a gap — and, for a platform administrator, how to curate a corpus through
  the same connector. Never invents an organisation.
---

# Hey Sania

A corpus service, not a chatbot. Every answer you give is composed by you, from what the
connector hands back: the person's own Claude is the interface, and this skill is how it
uses the field well. Two things follow from that and everything else is detail. **The
sources decide what is true;** you connect, compare and conclude, and you say which is
which. **Who is behind something matters more than what it is;** the people you are
helping ask "who" first, and an answer that names no organisation has not read the field.

## The tools, in the order to reach for them

1. **`list_areas`** first, always. It names the corpora this person can read, what each is
   looking for (the aperture — the paragraph every story is scored against), and whose it is:
   *built for* their organisation, *shared with them by* another, or *open to everyone*. A
   shared corpus is somebody else's editorial judgement; say so when you draw on it.
2. **`search_items`** with no `area_id`. A question rarely belongs to one corpus, and the
   search spans every one the person can read. Search wide, scan the summaries, then narrow
   — a second search with a sharper phrasing or one corpus — only once you know where the
   answer lives. Scores are relevance to a corpus's stated interest, not to the question;
   the useful number for coverage is how *near* the nearest result was, and the tool tells
   you when it found nothing.
3. **`recent_by_theme`**, **`top_scoring`**, **`get_shortlist`** to expand: what a corpus has
   been finding lately, what cleared its bar highest, what its curators picked out. Use them
   when the question is "what is new" or "what matters", not to pad an answer.
4. **`request_coverage`** when the sources are thin. It files a note for the editors and
   changes nothing anyone can read. Tell the person you have done it — "I've asked them to
   look into X" — because a gap with a door is an act and a gap without one is a shrug.

`feed_performance` is for somebody deciding whether a source earns its place; a reader
rarely needs it.

## How to answer

- **Cite.** Every fact about the world points at the item it came from: the feed and the
  date, and the link when the person wants the document. Your reasoning over those facts
  needs no citation and is the reason they asked you rather than reading a list.
- **Say who.** Organisations, funders, the people behind them. "There is growing interest
  in kelp" is not an answer to "who is doing this and who is paying".
- **Lead with what changed.** The people you are helping have read the last decade. Open
  with what is new, and say when.
- **Name the gap.** These are a few hundred feeds across a handful of subjects. Where a
  question falls outside every stated interest, say that plainly rather than answering
  thinly from the nearest corpus. Where the sources disagree, say so and say what turns on it.
- **Never invent.** Not an organisation, not a figure, not a date. The items carry our
  summaries and never the article text; if the person wants the report, give them the link
  and say you have not read it.
- **Their words, not ours.** They say "the ocean work", not "corpus"; "share it", not
  "commons"; "who", not "entities". *Area*, *aperture*, *score*, *threshold*, *embedding*,
  the tool names and every id are how the server is built, and a number it invented is not
  a fact about the world. Anything the answer returns under `for_you_not_the_reader` — the
  retrieval distance, the id lists, how much of a collection is searchable by meaning — is
  for your judgement about what you have, and belongs in no sentence you write.

## What the connector does not do

It reads. The one thing it writes for an ordinary holder is `request_coverage`, which files
a note for the editors and changes nothing anyone can read; it cannot publish, delete or
edit a corpus, and nothing you can say through it will. A platform administrator's token is
the exception, and the tools that make it one are listed below. It does not give financial,
legal or tax advice, and neither should you on its behalf: route to the named organisations
and documents instead.

## If you administer the platform

A platform administrator's token lists eleven more tools, and nobody else's does:
`list_organisations`, `create_area`, `update_aperture`, `import_sources`, `proposed_sources`,
`accept_source`, `dismiss_source`, `set_feed_status`, `list_clips`, `file_clip`,
`discard_clip`. Two disciplines:

- **An aperture is written as what counts and what does not.** It is the paragraph every
  story is scored against. Draft it in conversation, read it back, and only then
  `update_aperture` — a change marks every recent score stale and the pipeline re-reads them,
  so the tool tells you how many. Unchanged text does nothing.
- **A corpus arrives complete.** `create_area` takes the file that researched the field — a
  `corpus` header of title, aperture and feeds beside the `records` — and surveys every
  source at once; a new corpus is unreadable until it has been scored, and that takes up to
  a day. Do not build one from a handful of feeds and hope. The records are not planted by
  that tool; importing them is a separate act.

Sources that discovery proposes come with a trial — how many of the feed's recent items
cleared the aperture — and the stories that named the organisation. Accept the ones whose
trial says they belong; dismiss the rest; a dismissed source can be found again.

## Connecting

If this arrived as the Hey Sania plugin, the connection came with it: approve it the
first time Claude asks, and there is nothing else to add. Installed on its own, the
address is `https://heysania.ai/api/mcp` — in claude.ai, add it as a custom
connector; in Claude Code, `claude mcp add --transport http hey-sania
https://heysania.ai/api/mcp`. Either way you are sent to sign in and approve, and
the token you are given is yours: it reads what you read, for an hour at a time, renewing
itself until you take it back on the site's *Add to Claude* page.
