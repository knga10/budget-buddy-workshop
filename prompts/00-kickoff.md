# 0. Your first message

**Everyone starts here.** There are two versions depending on where your head is
at. Pick one, fill in the brackets, attach the files, send.

|  | Paste this |
|---|---|
| **I know what I want to build.** An idea card, or my own idea | **[Path A](#path-a-i-know-what-im-building)** |
| **I have no idea yet.** I want to look at the data first | **[Path B](#path-b-im-still-looking)** |

Path B ends by producing the same brief that Path A starts with, so the two
paths converge. Nobody is behind.

---

<a id="path-a-i-know-what-im-building"></a>

## Path A: I know what I'm building

Attach your data file, then paste this.

> I'm at a 2-hour workshop building a small civic web app from the 2026-27 ACT
> Budget. Here's my whole situation, so you don't have to ask.
>
> **What I'm building:** [one sentence. e.g. "a calculator that shows a Canberra
> household whether they're better or worse off next year"]
>
> **My data:** [e.g. "Table 3.3.2 of the Cost of Living Statement, 9 published
> household scenarios"], attached.
>
> **What I'm shipping:** one `index.html` plus one `data.js`, React and Babel
> from CDN with pinned versions, no build step, no backend, no login. It has to
> work on GitHub Pages and when opened as a local file, so use a `<script>` tag
> for the data, not `fetch()`. Everything stays in the browser.
>
> **How I want to work:** four steps, and I want to approve each one before you
> move on.
> 1. Describe the structure of my data. Don't extract yet.
> 2. Extract it to a CSV I can download.
> 3. Reconcile it: find the column that should equal the sum of other columns,
>    check every row, and show me a table of any that don't. If most rows fail,
>    your columns are misaligned, fix it and re-run rather than telling me it's fine.
> 4. Only then build the UI, against the data file, never against the source document.
>
> **Non-negotiable:** every figure on screen must trace back to a specific row
> and column of the source table. If you can't trace a number, don't put it on
> screen.
>
> Start with step 1.

---

<a id="path-b-im-still-looking"></a>

## Path B: I'm still looking

You have 44 files in a repo and no idea which one to open. That's a completely
normal place to be at 0:45. Here's the zero-decision version.

### Attach exactly these three files

From `data/extracted/`:

- `household-scenarios.csv` (18 rows, 9 households before and after)
- `infrastructure-program.csv` (254 rows, projects with completion dates)
- `accountability-indicators.csv` (365 rows, what agencies promised vs delivered)

**Don't attach the statements.** Don't attach the spreadsheet. These three are
already parsed, they're small, and between them they cover money, time and
promises, which is most of what's interesting in a budget.

### Then paste this

> I'm at a 2-hour workshop. In about 90 minutes I need to have shipped a small
> web app built on one slice of the 2026-27 ACT Budget. **I don't have an idea
> yet and I don't want to waste time browsing.** Help me find one, fast.
>
> I've attached three pre-extracted files from the Budget. Work only from these.
>
> **Step 1, right now:** give me the 6 most interesting things across these
> three files. For each: the finding in one plain sentence, the rows it comes
> from, and a one-line "so what" for an ordinary Canberra resident.
>
> Rank them by how much a resident would care, **not** by how big the numbers
> are. Skip anything that's just "this number is large".
>
> Two things to know about this data so you don't mislead me:
> - Rows named things like "2025-26 Budget" are baseline totals, not new
>   spending. Exclude them.
> - Rows with a name but no figures are section headings. Exclude them too.
>
> **Then stop and wait for me.** Don't build anything and don't extract anything
> yet.

### When something catches your eye

> Number [3] interests me. Two things:
>
> 1. Show me every row it's based on, so I can see it with my own eyes.
> 2. Tell me honestly: could I build a small single-page app around this in
>    45 minutes, with no backend? What would I have to fabricate or estimate to
>    make it work? If the answer is "anything", say so plainly.
>
> Then, if it survives, write me a four-line brief in this exact shape:
> WHO the one person this is for. INPUT what they pick or tell it. OUTPUT what
> they get back in one sentence. CONSTRAINT the one hard rule.

**If the answer to "what would I have to fabricate" is anything at all, pick a
different finding.** Every figure has to trace to a row.

### Then hand yourself over to the build loop

Once you have the brief, paste this and you're on the same track as Path A:

> Good, let's build that.
>
> **What I'm shipping:** one `index.html` plus one `data.js`, React and Babel
> from CDN with pinned versions, no build step, no backend, no login. It has to
> work on GitHub Pages and when opened as a local file, so use a `<script>` tag
> for the data, not `fetch()`. Everything stays in the browser.
>
> **How I want to work:** four steps, and I want to approve each one before you
> move on.
> 1. Describe the structure of the data we're using. Don't extract yet.
> 2. Get it into a clean `data.js` I can download.
> 3. Reconcile it: find the column that should equal the sum of other columns,
>    check every row, show me any that don't. If most rows fail, your columns
>    are misaligned, fix it and re-run rather than telling me it's fine.
> 4. Only then build the UI, against the data file.
>
> **Non-negotiable:** every figure on screen must trace back to a specific row
> and column of the source. If you can't trace a number, don't put it on screen.
>
> Start with step 1.

---

## Two rules for Path B

**Ten minutes, then commit.** Set a timer on your phone. Exploring is enjoyable
and it is not a deliverable. When the timer goes, you take whatever looks best
and start building.

**If nothing has grabbed you when the timer goes, take idea card 1 or 2.** They
use the smallest, cleanest data in the whole Budget and you can be building
within a minute. A shipped small thing beats an interesting unshipped thing,
every time.

Want to dig further than the six prompts above?
[`06-explore-the-data.md`](06-explore-the-data.md) has six more, including
"what's conspicuously absent", which is usually where the best ideas hide.

---

## If you're behind at 1:05

Whichever path you took, say this and keep moving:

> I'm short on time. Use the pre-extracted CSV I'm attaching instead
> (`data/extracted/household-scenarios.csv`). Skip to the UI and build it.
> Note: one household's published figures don't reconcile, by $899. Show the
> published figure and flag the gap in the UI rather than correcting it.
