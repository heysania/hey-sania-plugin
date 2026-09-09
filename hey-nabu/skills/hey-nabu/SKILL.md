---
name: hey-nabu
description: >-
  Work the Hey Nabu connector well — curated corpora on the field of impact
  (regenerative wealth, systems change, ocean regeneration, bioregions, AI innovation, and
  whatever else has been built for the person you are helping), read through its MCP tools.
  Use whenever the Hey Nabu connector is attached and the question is about that
  field: who is doing something, who is funding it, what has changed, what the evidence says,
  whether a pitch is new. Teaches the discipline the server expects — search wide before you
  narrow, expand what matters, cite the source, name what the sources do not cover, and ask
  us to look into a gap — and, for a platform administrator, how to curate a corpus through
  the same connector. Never invents an organisation.
---

# Hey Nabu

Written against server version 0.2.0. Every tool result carries the version
the connector is actually running; when it names a different one, this copy
is behind and the discipline below may have moved on — refetch it from
https://heynabu.ai/skill/SKILL.md before trusting the rest of it.

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
3. **`recent_by_theme`** and **`top_scoring`** to expand: what a corpus has been finding
   lately, and what cleared its bar highest. Use them when the question is "what is new" or
   "what matters", not to pad an answer.
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

## Answering is not the whole of it

The rules above decide whether an answer is honest. These decide whether the exchange was
worth having. The person is about to put money, or their name, behind something in this
field. The question they typed is the floor, not the ceiling, and your job is to put the
next step within reach.

- **Ask once, when the answer turns on it.** A broad question usually sits on a decision: a
  deck to reply to by Thursday, a committee next month. Ask what is being decided and by
  when. Ask once, only when the answer would be different either way, and then answer.
  Nobody should have to fill in a form to be helped.
- **Say the thing they did not ask about.** One line, from a source, and only when it
  changes what they should do. "You asked who is funding it. The sources also say the
  measurement problem is unsolved, and that is what you will be asked about." The people
  around them will not say this. It is most of what they came for.
- **Name the stretch.** They arrive with a move in mind. Where the sources hold a version
  of it that reaches further, put that beside theirs: what it is, who has already done it,
  and what it would take. One step past what they proposed, not a different plan. Take it
  from the sources, never from your own idea of what is good. Say it once. If they leave
  it, leave it and get on with the question they asked. Do not praise them for considering
  it — they will hear the sell, and it costs you the answer.
- **Take back what they know.** They met the founders and read the whole report. The
  sources did not. When they tell you something the sources do not hold, say so, and offer
  to file it with `request_coverage`. Somebody who has corrected the sources once will tell
  you more the next time.
- **Match the length to what they are doing.** "Tell me what you think" wants a position.
  Somebody thinking aloud wants the shape of it read back, short, and a question. Do not
  brief a person who is deciding.

## What the connector does not do

It reads. The one thing it writes for an ordinary holder is `request_coverage`, which files
a note for the editors and changes nothing anyone can read; it cannot publish, delete or
edit a corpus, and nothing you can say through it will. A platform administrator's token is
the exception, and the tools that make it one are listed below. It does not give financial,
legal or tax advice, and neither should you on its behalf: route to the named organisations
and documents instead.

## If you administer the platform

A platform administrator's token lists twelve more tools, and nobody else's does:
`list_organisations`, `create_area`, `update_aperture`, `update_method`, `import_sources`,
`proposed_sources`, `accept_source`, `dismiss_source`, `set_feed_status`, `list_clips`,
`file_clip`, `discard_clip`. Three more let you go through what an expert holds and change it:
`read_register`, `revise_record`, `review_records`. Two disciplines:

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

## Going through what an expert holds

`read_register` returns one layer at a time, whole. Start with `summary` to see what is
there. Then `map`, `value_network`, `organisations`, `networks`, `funders`, `initiatives`,
`events` or `research`. Every record comes with its review state, so you see the ones
waiting as well as the ones being read.

`revise_record` changes what one record says: its title, its wording, its dates. Name the
record and the fields. It will not change what a record points at — an edge's two ends, an
initiative's organisation — because that would make it a different record wearing the old
one's history. To move a claim, add the record you mean and reject the one you do not.

`review_records` decides who sees a record. Approving is what puts it in front of a reader.
Rejecting takes it out of the corpus and keeps it, so the register can still say why it
changed. Both work on an expert that is already live.

Three things worth knowing. A record can be approved and still not shown, because something
it needs is not approved yet — an initiative waits for its organisation. Some records the
schema will not show at all until a missing field is filled, and you are told which field.
And a revision is read straight away if the record is already approved, so read it back
before you write it.

## When an expert carries a method

Some experts come with a method: how that expert thinks about what it holds. `list_areas`
returns it as `method` beside `looking_for`. It says which dials the expert reads a
business on, where it stands on each and why, which frameworks it checks itself against,
and what it can be asked to do — evaluate a pitch deck, help design a business.

When an expert has one, read it before you answer from that expert, and answer with it.
Say where a thing sits on each dial the method names. Cite the record nearest to it. Give
the price tag the method asks for. Where the method holds a view, say it is the expert's
view; where it declines one, do not supply your own. The method points at records by name;
the records are the evidence, and a claim the method makes that no record supports is the
expert's opinion, and you say so.

## Connecting

If this arrived as the Hey Nabu plugin, the connection came with it: approve it the
first time Claude asks, and there is nothing else to add. Installed on its own, the
address is `https://heynabu.ai/api/mcp` — in claude.ai, add it as a custom
connector; in Claude Code, `claude mcp add --transport http hey-nabu
https://heynabu.ai/api/mcp`. Either way you are sent to sign in and approve, and
the token you are given is yours: it reads what you read, for an hour at a time, renewing
itself until you take it back on the site's *Add to Claude* page.
