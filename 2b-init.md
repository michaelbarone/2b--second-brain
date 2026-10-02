# Second Brain Framework — Generic Template

```
QUICK START — bootstrapping a brand-new vault
  1. Copy this file (2b-init.md) into the target vault's root.
  2. Tell your agent explicitly: "Read 2b-init.md in full, then run Operation: init-vault against it."
     -- this will start the wizard to fully bootstrap the new vault/repo
  3. Answer the interview questions. init-vault writes this vault's real
     2b-instructions.md, scaffolds the folders and writes those stub files
     -- after the initial bootstrap, agent files will be created to help any agent tool find its way to the instruction file on its own.

ALREADY SET UP? Tell your agent: "Run Operation: check-for-updates"
     -- downloads the latest release, then offers update-vault

QUICK REFERENCE — operations defined in this file (full definitions below)
  Vault lifecycle
    Operation: init-vault                     run once, in a fresh vault
    Operation: check-for-updates              download a newer 2b-init.md release, then offer update-vault
    Operation: update-vault                   pull in changes from a newer 2b-init.md (+ newly required modules)
    Operation: add-use-case                   activate a module not yet active

  Core (available once a vault is initialized)
    Operation: help <module|recipe?>          module/recipe menu, or active-vault operations reference
    Operation: config <key?> <value?>         review/change vault-wide settings (e.g. citation-rigor)
    Operation: dashboard                      build/refresh Dashboard.md
    Operation: plan-day                       morning ritual — due/overdue + today's resurfaced item
    Operation: close-day                      evening ritual — log what happened
    Operation: ingest <url|file>              bring a source in: Raw -> Summary -> Wiki ripple
    Operation: check-watchlist <playlist|all> check a YouTube watchlist for new videos
    Operation: query <question>               answer from the wiki, saves real synthesis by default
    Operation: lint                           health-check the wiki
    Operation: review                         periodic review — deadlines, stagnant items, Ecosystem
    Operation: digest                         scan the web for topic news, write to Inbox (never auto-ingests)
    Operation: draft <Outputs page> <topic>   stitch cited claims into a first-pass draft
    Operation: find-open-questions <scope?>   scan ingested material for open/unclear/conflicting items
    Operation: plan-project <board?> <topic>  scope milestones/dependencies, move to In Progress
    Operation: new-board <topic>              create a new independent Projects board
    Operation: archive <topic|page>           move a finished topic into Archived/ (restorable)
    Operation: restore <archive>              bring an archive back and re-link it
    Operation: delete <archive> [files]       permanently delete an archive (own confirmation)

  Module operations (only in vaults where that module is active)
    Research            track-citation <claim> <source>
    Projections         build-projection <subject> [profile] [preset] [horizon] [increment]
                        update-projection <projection> [new details|source]
    Content Production  new-topic, prep-piece, update-sponsor, analyze-performance
    Team/Org KB         check-workflow-currency <SOP page> <new source>
    Personal CRM        log-interaction <contact> <notes>
    Competitive Intel   research-competitor <entity> <objective>
    Product Discovery   score-idea <opportunity|solution>
    Product Feasibility run-spike <question> [initiative]
    Opportunity Cost    compare-options <option set>
    Meeting Transcripts ingest-meeting <transcript file|paste>
    Due Diligence       raise-issue, resolve-issue, build-model <opportunity>
    Stand-up Comedy     develop-bit, feedback-bit, research-bit, check-prior-use,
                        build-set, log-set, review-burn, review-material
    Investment Strategy set-profile, build-policy, import-holdings, check-portfolio,
                        define-rule, add-indicator, ingest-backtest, import-trades,
                        grade-rule, review-rules, build-rulebook
    Travel Planning     plan-trip, scout, find-routes, choose, add-booking,
                        add-expense, build-itinerary, pack, check-trip,
                        trip-brief, log-trip
```

**Generator version: 4.34** — bumped on any change anywhere in this file (core or Module Library). Core sections and each Module Library entry also carry their own version line below; a vault's `2b-instructions.md` records what it was built/last-updated from in its own `## Generator versions` section, and `Operation: update-vault` uses these to know what to check without re-reading everything. **4.34 (2026-10-02): added a new standalone Module: Travel Planning** (Module version 3.0) — planning vacations and road trips, domestic or international. Shared Place pages (including eat, shop, stay and country kinds) outlive trips. Each trip gets its own folder, a card on a Travel Board (`Idea → Researching → Planning → Booked → Underway → Done`, plus Cancelled), and either a checklist or its own task board (`To Do → On Hold → In Progress → Done`), as the user chooses. Legs, stays and activities move from option to chosen to booked, with basic cost estimates for the party; the itinerary, per-day or combined, is generated from them. Dated prep tasks come from an editable prep timeline and packing lists from an editable master list. Road trips get suggested driving limits (marked as rules of thumb), planned stops and fuel estimates. International trips get a country check per traveler, by passport, age and driving, from official sources with checked dates. An optional `log-trip` is offered when a trip ends. Eleven new operations. Standard file `.obsidian/graph.json` (File version 1.1 → 1.2): `Travel/` folders. See Core 4.21 for the Help and Recipe additions. **4.33 (2026-09-30): wording and quick-start fixes.** The quick-start block gained an "Already set up?" line pointing at `Operation: check-for-updates`, and two formatting slips in it were fixed (a tab-indented line, and "finds" → "find"). Also a typo fix in core (Core 4.19 → 4.20). No behavior changed. **4.32 (2026-09-30): new `Operation: check-for-updates`**, which downloads a newer released `2b-init.md` and then offers `update-vault` (see Core 4.19). **4.31 (2026-09-30): `init-vault` now checks for version control** (see Core 4.18). **4.30 (2026-09-29): page names must be unique across a vault** (see Core 4.17). Three modules renamed fixed pages that clashed, each with a migration note for existing vaults: Content Production (Module version 3.0 → 4.0) `Content/Board.md` → `Content/Content Board.md`; Stand-up Comedy (4.0 → 5.0) `Comedy/Board.md` → `Comedy/Comedy Board.md` and `Comedy/Library.base` → `Comedy/Comedy Library.base`; Investment Strategy (4.0 → 5.0) `Investing/Library.base` → `Investing/Investing Library.base`. **4.29 (2026-09-29): added a new Research flavor, Investment Strategy** (Module version 4.0; Requires: Research; Declared citation-rigor: standard). It covers building and continually improving your own indicator-based investing rules for stocks, ETFs and crypto. Shared, versioned conditions combine into rules, rules into strategies per need, and strategies are graded per asset class from imported backtests (with a bias check) and imported trades. A two-part grade (letter plus evidence level) is gated by an editable Grading Policy. Append-only evidence ledgers and changelogs record every improvement or invalidation. Sources are trusted only as far as other evidence corroborates them. An optional, deferrable portfolio layer (Investor Profile → Portfolio Policy with allocation, per-trade risk, heat, concentration, circuit breakers and a glide path by years remaining) caps every strategy. Dated rulebooks state what changed and why. Eleven new operations. Research base (1.1 → 1.2): flavor list now names Due Diligence and Investment Strategy. Standard file `.obsidian/graph.json` (File version 1.0 → 1.1): `Investing/` folders and a `#status/invalidated` override. See Core 4.16 for the Help and Recipe additions. **4.28 (2026-09-25): archive behavior for three modules, and `Archived/` hidden in Obsidian** (per `Operation: sync-template`). Content Production (Module version 2.0 → 3.0): archiving never trims the self-node's covered-topics list, and `External Sources/` pages get the same archive rules as `Raw/`. Team / Org Knowledge Base (2.0 → 3.0): an extra preview warning before archiving a `source-of-truth` page, and `Decisions.md` is never archived or given link markers. Stand-up Comedy (3.0 → 4.0): burned bits, and the Release pages their burn records cite, can't be archived or deleted; a set's `status: archived` is separate from `Operation: archive`; Performance pages get the same archive rules as `Raw/`. Standard file `.obsidian/app.json` (File version 1.0 → 1.1): `Archived/` added to the ignore filters. **4.27 (2026-09-25): added archive and delete operations** (Core version 4.14 → 4.15). See that changelog entry. **4.26 (2026-09-24): Obsidian app settings became a standard file** (`.obsidian/app.json`, File version 1.0; Core version 4.13 → 4.14). See that changelog entry. **4.25 (2026-09-24): removed stray wikilinks** (Core version 4.12 → 4.13, wording only). See that changelog entry. **4.24 (2026-09-24): added standard files** (Core version 4.11 → 4.12). The first is a standard `.obsidian/graph.json` (File version 1.0) that colors every core and module folder by what its layer does, so graph colors are consistent across vaults with no manual setup. See that changelog entry. **4.23 (2026-09-24): added a new standalone Module: Stand-up Comedy** (Module version 3.0) — developing your own stand-up material from Inbox ideas through premises (with branching joke directions), versioned bits (one file per bit, `## Current` + version history), optional chunks, and sets built as ordered embeds with callback-ordering rules; one-enum stage scores (`killed | solid | soft | bombed`) from immutable Performance pages; recordings transcribed into `Raw/` with the original link kept; an evidence-backed Burn review (new `Comedy/Releases/` pages) before any bit is marked burned and locked as a record, with new work continuing as linked derived bits; a prior-use check against other comedians' work (paraphrased queries, "nothing found" never reported as "original"); on-request craft feedback and offered topic research (facts, shared experience, audience reach, fact-check — never joke text, never other comedians' jokes); prior-use and feedback offered together when work moves off a bit, run in the background or after the current request. Eight new operations (`develop-bit`, `feedback-bit`, `research-bit`, `check-prior-use`, `build-set`, `log-set`, `review-burn`, `review-material`), added to the quick-reference block. Core changed too (Core version 4.10 → 4.11): a Help entry for the module and a new **Comedy Writer / Performer** recipe. **4.22 (2026-09-22): `update-vault` now adds newly required modules, surfaces migration notes, and ends with a recipe check** (Core version 4.9 → 4.10 — see that changelog entry). Projections gained projection-page and preset-page templates (Module version 2.0 → 2.1); Due Diligence gained a migration note for vaults that used the pre-4.0 `build-model` (Module version 4.0 → 4.1). **4.21 (2026-09-22): Projections gained line-item presets, a vault-first gap-closing rule, and a per-projection Board card** (Module version 1.0 → 2.0) — editable `Projections/Presets/` pages (starter presets: Franchise, Product Launch) pre-load standard line items, with any the vault can't fill starting as `missing` assumptions with open issues; projections are built only from material already in the vault, gaps carry a `next-step` (`ask-user` / `search-web` / `ingest-document`), and `update-projection` with no new details offers to work the open issues (web candidates go to an Inbox shortlist and are ingested only on confirmation) before re-running; one auto-created Board card per projection with open high-impact issues, skipped when a profile routes issues elsewhere. Opportunity Cost / Options Comparison's like-for-like rule now includes `preset` (Module version 4.0 → 4.1). **4.20 (2026-09-22): added a second base module, Module: Projections** (Module version 1.0, `requires: Research`) — a shared, period-based projection model (timeline phases, cost buckets, revenue drivers, low/base/high scenarios; monthly increments over a 12-month horizon by default), with every assumption labeled by confidence (`sourced`/`user-stated`/`estimated`/`missing`), thin/missing/conflicting/high-leverage inputs surfaced as a tracked open-issues table, and `Operation: build-projection` / `Operation: update-projection` (new details answer/resolve open issues and refresh the projection, recorded in an append-only revision log). Flavors plug in through a declared `**Projection profile:**` line. Three flavors gained one and now require Projections: **Due Diligence** (Module version 3.0 → 4.0 — its financial model now builds on the shared skeleton; `build-model` kept as a shorthand; high-impact projection issues promote into `Diligence/` items), **Opportunity Cost / Options Comparison** (3.0 → 4.0 — optional like-for-like projections per option feeding the matrix and quantifying the foreclosed-cost column), and **Product Discovery / Decision-Making** (2.0 → 3.0 — launch projections checked against the opportunity's SOM). Core changed too (Core version 4.8 → 4.9): base-module requirements now resolve transitively. The quick-reference block also gained a module-operations section (previously only core operations were listed). **4.19 (2026-09-15): added `Operation: find-open-questions`** (Core version 4.7 → 4.8 — see that changelog entry for the full spec and design history). **4.18 (2026-09-15): added a new core `## Recipes` section** (Core version 4.6 → 4.7) — named, common module combinations to make bootstrap module selection more consistent across separate `init-vault` runs; see the Core-version changelog entry above for the full rationale and which operations now reference it. **4.17 (2026-09-15): Due Diligence gained spreadsheet ingestion and a sourced financial model** (Module version 2.0 → 3.0) — CSV/XLSX sources now get the same Raw treatment as any other source plus preservation of the original file in `Assets/`; a new `Operation: build-model <opportunity>` builds/updates a real, editable `.xlsx` financial model (cost assumptions, break-even quantity/revenue per the standard formula) with every populated cell traceable to its source, gracefully degrading to a markdown table when the running agent tool lacks spreadsheet-authoring capability. The first mechanic in this file to depend on a real (non-markdown) file-authoring capability — called out in a new **Tooling note** in the module's own block so that dependency isn't silently assumed. **4.16 (2026-09-15): `Projects (core)` gained a `#status/<state>` card-state tag sub-taxonomy and native Kanban tag-color highlighting** (Core version 4.5 → 4.6) — `#status/blocked`/`#status/waiting-on-answer`/`#status/answered`/`#status/at-risk`, orthogonal to board column, confirmed via the Kanban plugin's own native Tag Colors setting rather than a new plugin or CSS snippet; folded into the Dashboard's existing needs-attention widget as an additional filter. **4.15 (2026-09-15): added a new flavor Module: Due Diligence** (Module version 2.0, `requires: Research`, `standard` rigor) — ingesting and cross-referencing due-diligence source material (financial documents, business plans, meeting transcripts) into a `Diligence/` open-items register (an 8-category taxonomy, a 4-state status model, a 4-level severity scale), routing cross-document conflict detection through the existing core `## Contradiction handling` mechanic rather than a bespoke one, with high-severity items auto-raising a `Projects/Board.md` card (a deliberate departure from Meeting Transcript Ingestion's confirm-then-place default, since reaching high severity is already a deliberate sourced act, not unreviewed scraped text). See that module's own Research log for the sourcing (an M&A due-diligence checklist, a deal-desk diligence tracker). **(Correction, 2026-09-15): this header was still reading 4.13 despite the 4.14 changelog entry below already describing a completed change — a stale-number bug from the 2026-08-17 session, fixed here rather than left to compound.** **4.14 (2026-08-17): added a new core `## Contradiction handling` section** (detection classification during `Operation: ingest`, marking/tagging, and both resolution paths — supersession and scope-split) plus a generalized core Entity append-timeline convention (Core version 4.4 → 4.5), and narrowed Competitive Intelligence's own "Entity convention" bullet down to just its `last-updated-by-source`/`company:` frontmatter addition, pointing at the new core mechanic for the base behavior (Module version 3.0 → 4.0) — see that module's own Research log for the sourcing (ADR supersession, Wikidata statement ranking, a knowledge-graph-conflict survey) that grounded the design. **4.4 (2026-08-07): Product Feasibility and Opportunity Cost / Options Comparison built out from thin stubs to first-pass designs** (Module versions 1.0 → 2.0 each), per `Operation: sync-template` — see each module's own version line below. **4.5 (2026-08-07): Product Feasibility gained initiative-linked spike chaining** — an `initiative` frontmatter field on `Feasibility/` pages plus a `run-spike` behavior change that surfaces prior same-initiative spikes' context before starting a new one (Module version 2.0 → 3.0); memo assembly across multiple spikes still runs through the existing generic `Operation: draft`, not new drafting logic in `run-spike` itself. **4.6 (2026-08-07): Opportunity Cost / Options Comparison gained a Deadline hook** — a deferred comparison's `target-date` now feeds the core deadline sweep/`plan-day` synthesis, plus a boundary making a deferred comparison with no `target-date` a lint failure (Module version 2.0 → 3.0); no bespoke resurfacing mechanism, reuses the same core mechanism every other flavor's Deadline hook already relies on. **4.7 (2026-08-07): Content Production gained a lightweight key-dates check, a capacity-discipline boundary, and a structured 7-category contract-terms section on Sponsors/ pages** (Module version 1.0 → 2.0) — a fuller enterprise-style nested-calendar structure and a separate deliverable-status pipeline were both considered and declined as more machinery than this module's scale needs. **4.8 (2026-08-07): Competitive Intelligence gained `Operation: research-competitor` and a Fact/Impact/Response entry structure** (Module version 2.0 → 3.0) — a narrowed version of a full enterprise 8-step process; a proposed industry-level Porter's Five Forces page was declined here as reaching into Product Discovery/Decision-Making's decision-making scope instead of this module's tracking scope, and referred to that module's Open Questions instead. **4.9 (2026-08-07): Product Discovery / Decision-Making gained a `market-size` (SOM) field on Opportunities**, surfaced by `score-idea` as qualifying context rather than a fifth RICE factor (Module version 1.1 → 2.0) — resolves the industry-attractiveness question referred from Competitive Intelligence at the opportunity level instead of a separate industry page; a proposed switch from the Opportunity Solution Tree to the GIST framework as this module's top-level structure was considered and declined as redundant. **4.10 (2026-08-07): Personal CRM / Relationships gained a `bridges` field and a relevance-triggered follow-up convention** (Module version 1.1 → 2.0) — two independent second-signal answers to the same open question (a static bridging-position property, and a lightweight noticed-relevance capture habit), adopted together since they answer different parts of the same problem rather than duplicating each other. **4.11 (2026-08-07): Team / Org Knowledge Base cleared all four of its open questions** (Module version 1.0 → 2.0) — a human/agent content-origin tag replacing the earlier internal/external framing, a reactive `Operation: check-workflow-currency` plus a proactive SOP review cadence reusing the existing `authority` field, and the Onboarding pattern restructured into three phases with buddy/mentor named separately from manager check-ins; OKF-compatible frontmatter was deferred again explicitly, since the blocker is the standard's own immaturity, not sourcing. **4.12 (2026-08-12): Conventions gained a rule that wikilinks resolve by page name only, never a folder-qualified path, plus a dedicated `lint` check flagging any wikilink target containing `/`** (Core version 4.3 → 4.4) — reported from a deployed vault where `[[Feasibility/Page Name]]`-style links silently failed to resolve; genericized to a core rule rather than a per-module patch since any module with its own folder hits the same failure mode. **4.14 (2026-08-17): added a new standalone Module: Meeting Transcript Ingestion** (Module version 2.0) — capturing full meeting transcripts from external recording/note tools (Krisp, Granola, Google Meet/Gemini) as a new `Raw/` source-type, with participant-linking to Contacts/People, decision extraction, and a confirm-then-place mechanic for candidate action items; a manual-paste-only design for its first sync — tool-specific pull (API/MCP) and push (webhook) integrations were researched and are named in the module block but deliberately not built yet, since a push tier in particular needs its own human-review gate solved first. See that module's own Research log for the sourcing (Krisp's Webhook API, Granola's CSV export and MCP server, Google Meet's Gemini notes).

This file is not a working ruleset yet — it is a **generator**. Read the whole thing, then run `Operation: init-vault` (below) to interview the user and produce this vault's *real* `2b-instructions.md`, tailored to what they're actually building — plus `CLAUDE.md`/`AGENTS.md`/`.cursorrules`/`GEMINI.md` stub files pointing at it, so any agent tool finds its way there regardless of which filename convention it looks for. Do not treat any placeholder text (anything in `< >`) as final until `init-vault` has resolved it.

**Distributing this generator (agent-agnostic, cold start):** this file is agent-agnostic itself, but a completely naive agent tool has no way to discover it by convention alone — a fresh vault with only `2b-init.md` dropped in only "just works" for a sufficiently agentic tool that goes looking, or a user who names the file explicitly. To make cold start itself agnostic, copy `2b-init.md` into a fresh vault **together with** `CLAUDE.md`, `AGENTS.md`, `.cursorrules`, and `GEMINI.md` stub files, each containing:

```
# Stub — this is a generator, not yet initialized

This vault has not been set up yet. Read `2b-init.md` in full, then run
`Operation: init-vault` against it. That operation will replace this stub
(along with the other agent-tool stub files at this vault's root) with
one pointing at the real, tailored instructions file it produces.
```

This is a one-time authoring/packaging concern (create these alongside `2b-init.md` wherever it's distributed from) — it is *not* something `Operation: init-vault` creates, since by the time that operation runs, some agent has already found `2b-init.md` one way or another.

## Philosophy

**Core version: 4.21** — covers this section through core Boundaries and Style below, plus the `init-vault`/`check-for-updates`/`update-vault`/`add-use-case` operations themselves. Bumped whenever any of those change; the Module Library entries below version independently of this. **4.21 (2026-10-02): Help gained a Travel Planning entry, and `## Recipes` gained a Travel Planner recipe** (Travel Planning core; Opportunity Cost / Options Comparison and Personal CRM optional). Both accompany the new module added in Generator 4.34; no operation behavior changed. **4.20 (2026-09-30): wording only.** Fixed a typo in `init-vault`'s Interview ("oboarding" → "onboarding"); no behavior changed. **4.19 (2026-09-30): new `Operation: check-for-updates`.** It reads the latest release tag from the public repo (`michaelbarone/2b--second-brain`), compares it with the vault's `2b-init.md` version part by part (4.10 is newer than 4.9), and, if a newer release exists, shows its changelog entries and asks before downloading. It checks the downloaded file's version against the tag, replaces only `2b-init.md`, then offers `update-vault` (or `init-vault` in a vault not yet initialized). It also catches a downloaded but never-applied `2b-init.md` by comparing against `## Generator versions`. Added to the quick reference, to `help`'s always-listed operations, and to a new core boundary; `update-vault`'s intro now points at it for getting a fresher copy. **4.18 (2026-09-30): `init-vault` gained step 5, Recommend version control** (Report is now step 6). It checks whether the vault is under git. If not, it recommends setting it up so every agent change is reviewable and undoable, and offers to run `git init`, write a `.gitignore` for per-device Obsidian state, and make a first commit, only on the user's yes. Connecting a remote stays the user's step. Declining is fine, and Report now says whether the vault is under version control. **4.17 (2026-09-29): new convention, page names are unique across the vault.** Found in a vault built from this generator: Content Production's `Content/Board.md` and the core `Projects/Board.md` shared the page name `Board`. Since links resolve by name and folder paths in links are ruled out, `[[Board]]` could point at either. Every fixed page a module scaffolds now carries its module's name; before creating any page, check the vault for the name or an alias; aliases never repeat another page's name or alias; `_Template.md` files are the only exception. `lint` gained a duplicate-page-name check. The module-independence rule and the Module Library intro now cover name collisions as well as path collisions, and the Projects Independence example names the renamed `Content/Content Board.md`. **4.16 (2026-09-29): Help gained an Investment Strategy entry, and `## Recipes` gained an Investor / Trader Strategy Development recipe** (Investment Strategy core; Due Diligence, Competitive Intelligence and Opportunity Cost / Options Comparison optional). Both accompany the new flavor added in Generator 4.29; no operation behavior changed. **4.15 (2026-09-25): new `Operation: archive`, `Operation: restore` (alias `unarchive`) and `Operation: delete`**, for clearing finished topics out of a vault. Archive moves every page created for a topic, `Raw/` files included, into `Archived/<slug>-<date>/`, which Obsidian excludes from search and the graph. It runs after a preview and confirmation, marks links on the pages that stay (`*(archived)*`), removes the topic's Index lines, board cards and Bibliography entries, and writes a restore index. Restore reverses it and re-runs ingest's linking and contradiction check. Delete permanently removes an archive, only when asked and with its own confirmation. Marked links become `Page (deleted <date>)`, and the user decides each claim left without a source. Also: `Archived/` in `## Core vault map`; `ingest` never links into it and avoids reusing archived page names; `lint` skips it; the `Raw/` boundary gains a move/delete exception for these operations only, with content never changed; and the Module Library intro documents a new optional `**Archive behavior:**` line. **4.14 (2026-09-24): `## Obsidian app settings (core)` folded into `## Standard files (core)`** as `### Standard file: .obsidian/app.json` (File version 1.0). It uses a new `keys` apply mode: only the listed keys are set, list values are merged, and a **Supersedes** line names old entries to remove. The three ignore filters are now anchored to exact files. The broad patterns `/Index/`, `/Log/` and `/_Template/`, which could also hide unrelated notes such as `Login Flow.md`, are superseded. New entries hide `2b-init.md` and the agent stub files. New keys: attachments go to `Assets/`, new notes to `Inbox/`, and wikilinks use shortest names and update automatically on rename. `update-vault` no longer re-applies app settings silently on every run. They go through standard-file step 7 (ask, show the change, confirm), which replaces the old silent step 7 and the separate step 7a. A vault with no `standard-file app.json` line recorded is offered the standard on its next update. **4.13 (2026-09-24): removed three stray wikilinks** that would have rendered as real links to pages that may not exist. The Help section's Product Feasibility entry named Product Discovery / Decision-Making as a link; it's now plain text. The contradiction-handling card title and supersession note used `[[Old]]` / `[[New]]`; they're now placeholder syntax in inline code. Wording only; no behavior changed. This file is a seed and contains no links. `[[...]]` appears only as syntax examples in code. **4.12 (2026-09-24): new `## Standard files (core)` section.** It holds ready-made files placed into a vault's own folders, each with its own File version and an Apply line naming what it owns. The first is `.obsidian/graph.json`, which owns the graph view's color groups and covers every core and module folder. Colors are grouped by what each layer does, with status overrides such as `#status/contradiction-open` placed first. `init-vault`'s Scaffold step writes standard files where none exist. `update-vault`'s new step 7a asks whether to set each changed standard file as the vault's default, shows the change, and confirms before overwriting, with adopt / replace / skip choices. The outcome is recorded in `## Generator versions` (new `standard-file` lines) so a declined version isn't asked again. `## Graph view setup` now points at the standard file instead of describing manual setup. There's a new core boundary against overwriting `.obsidian/` or other targeted files without confirmation. **4.11 (2026-09-24): Help gained a Stand-up Comedy entry, and `## Recipes` gained a Comedy Writer / Performer recipe** (Stand-up Comedy core; Content Production and Personal CRM optional) — both accompany the new standalone module added in Generator 4.23; no operation behavior changed. **4.10 (2026-09-22): `Operation: update-vault` no longer only refreshes modules a vault already has.** Found when Due Diligence, Opportunity Cost / Options Comparison, and Product Discovery / Decision-Making gained a new required base (Projections): an updated module could otherwise land referencing a base the vault never installed. Three additions: (1) **newly required modules** — if an updated module's `**Requires:**` now names a module not active in the vault, it's added (transitively, confirmed, using `add-use-case`'s per-module logic); (2) **migration notes** — a new optional `**Migration note:**` line in a Module Library block tells `update-vault` what existing content an upgrade affects; it's surfaced and the user decides how to handle it, deliberately not automated or exhaustive; (3) **recipe check** — before offering `add-use-case`, the now-active modules are compared against `## Recipes`, and any recipe that matches or nearly matches has its missing members suggested — user-driven, nothing added automatically. **4.9 (2026-09-22): base-module requirements now resolve transitively** — the new Projections base module itself requires Research, so a flavor requiring Projections pulls in both. `init-vault`'s Interview/Assemble and `Operation: add-use-case` now walk `**Requires:**` chains to the end (each auto-included base still confirmed with the user, never silent); the Module Library intro now names two base modules and documents the `**Projection profile:**` line alongside `**Dashboard contribution:**`; the Help section gained a Projections entry and `## Recipes` notes that required bases (Research, and Projections where a flavor declares it) are implied. **4.8 (2026-09-15): added a new core `Operation: find-open-questions [scope] [focus]`** — a manually-invoked, vault-internal scan of already-ingested material for open questions, ambiguity, and conflicts, broader than `## Contradiction handling`'s literal-conflict-only, ingest-time-only scope. Checks `Wiki/Arguments/` (plus in-scope `#status/contradiction-open` items) before raising anything new so repeat runs don't duplicate, and reports what's still open from before. Took a simple `scope` (explicit pages/tag/date-cutoff, combinable) and `focus` (a short steering instruction) as its only parameters. Originated from a narrower Due-Diligence-specific "review pass" need (see that module's own Research log) and was generalized to a plain core operation once `Wiki/Arguments/`'s own existing definition — *"the thinking garden... cultivate this folder continuously as sources are ingested"* — turned out to already describe exactly this use; Due Diligence remains a beneficiary, not a dependency. A separate named-reusable-prompt-file architecture (`Prompts/`, a Prompt Library, a `run-prompt` operation) was designed and then explicitly deferred in favor of this simpler, directly-hardcoded operation — same treatment as every other core operation in this file; revisit the fuller architecture only if a second, genuinely distinct complex task actually needs it. **4.7 (2026-09-15): added a new `## Recipes (common module combinations)` core section** — ~8 named, versioned module combinations for common real-world needs (Academic Research, Team/Org KB + Meetings, Content Creator Operations, Competitive/Market Watch, Product Strategy & Roadmap Decisions, Investment/Deal Due Diligence, Personal CRM/Relationship-First, General Knowledge Base), each with core members and optional add-ons. Motivation: without a fixed reference point, module selection from a free-text purpose description is a judgment call re-derived from scratch on every `init-vault` run, with no guarantee five separate bootstraps given a similar stated purpose land on the same module set — recipes don't make this perfectly deterministic (matching against them is still a judgment call), but narrow it from "compose freely across 11 modules" to "pick the closest of ~8 named options, then confirm/adjust," which is meaningfully more consistent. `init-vault`'s Interview step 2 now supports naming a recipe directly for a quick start, or comparing free text against every recipe for a match before falling back to the from-scratch walkthrough; `Operation: help` surfaces `## Recipes` alongside the module menu and supports `Operation: help <recipe name>`; `Operation: add-use-case` step 2 now checks whether an already-active module belongs to a recipe whose other core members aren't yet active, and suggests those (never auto-adds). A recipe is always a confirmed starting point, never silently applied — same discipline as picking modules individually. **4.6 (2026-09-15): `## Projects (core)` gained a `#status/<state>` card-state tag sub-taxonomy** (`#status/blocked`, `#status/waiting-on-answer`, `#status/answered`, `#status/at-risk`) plus native Kanban-plugin tag-color highlighting, orthogonal to board column — requested to let a card show it's actually stuck (e.g. pending an answer) without moving it out of its real workflow column. Confirmed via research rather than assumed: the Kanban plugin already supports mapping a hashtag to a custom background/text color, no new plugin or CSS snippet needed. Folded into the Dashboard's existing needs-attention widget as an additional filter. The new Due Diligence flavor (see Module Library) is the first real consumer — its auto-raised high-severity items carry these tags — but the mechanic itself is core, not flavor-specific. **4.5 (2026-08-14): added `## Contradiction handling`** (a new core section between `## Vault config` and `## Dashboard`) plus a generalized Entity append-timeline convention in `## Conventions (core)`, a new `#status/contradiction-open` tag-taxonomy value, a contradiction-check sub-step in `Operation: ingest` step 4, and a Boundaries addition gating silent resolution — see the Generator-version changelog entry above for the module-level knock-on (Competitive Intelligence's Entity convention narrowed to point at this instead of restating it). **4.0 (2026-07-31): graduated Project/Work Planning from the Module Library into core** — every vault now gets `Projects/` (Kanban board, `Operation: plan-project`/`new-board`, the needs-attention Dashboard widget, board-confirmation/WIP-limit Boundaries) unconditionally, replacing the retired `TODO.md` as the core follow-up-tracking mechanism. **4.1 (2026-07-31): `plan-day`/`close-day` now record their own last-run date/time** in a new `Routines/Daily Ritual.md` page (mirroring the existing `Routines/Watchlists.md` last-run-tracking pattern), so a Dashboard widget can show ritual currency — bookkeeping about the ritual itself, not a relaxation of `plan-day`'s read-only-over-vault-content guarantee. **4.2 (2026-08-04): added core `.obsidian/app.json` defaults** (`showLineNumber`, `userIgnoreFilters`, `showUnsupportedFiles` — see `## Obsidian app settings` below), merged into that file (never overwriting unrelated keys) by `init-vault`'s Scaffold step and re-applied idempotently by `update-vault`. **4.3 (2026-08-04): added a human-readable quick-start/quick-reference block** at the very top of the file (bootstrap instructions naming this file explicitly, since the agent-tool stub files don't exist yet on a genuinely fresh vault, plus a one-line-per-operation index) — navigation aid only, no behavior change. **4.4 (2026-08-12): Conventions gained a wikilinks-resolve-by-name-not-path rule, and `Operation: lint`'s checklist gained a dedicated check for `/`-containing wikilink targets** — see Generator version 4.12 changelog entry above for the full rationale.

This vault follows Karpathy's LLM Wiki pattern extended with a functional-layer model: the user curates sources and asks questions; Claude does everything else — summarizing, cross-referencing, keeping the wiki internally consistent, and bookkeeping. Claude is not a passive librarian. Depending on which modules are active (see below), Claude may also track strategy, plan work, or manage a production pipeline — always receipt-backed, never inventing facts.

This pattern assumes a vault of hundreds, not millions, of pages. It works because Claude can hold the whole index and follow links directly — at genuinely enterprise scale (millions of documents), a traditional RAG/embedding pipeline becomes the better tool. If a vault is approaching that scale, that's a signal to reconsider the approach, not a reason to keep force-fitting it here.

`< VAULT PURPOSE — one or two sentences on what this specific vault is for, filled in by init-vault >`

## Help — choosing and using modules

Run `Operation: help` any time for this section, filtered to whatever's actually active in the current vault. Before `init-vault` has run, this doubles as the module menu — read it to decide what to turn on. Modules are composable; most real vaults pick 1-2. **See `## Recipes` below for named, common combinations** — a faster starting point than picking modules one at a time from scratch, especially for a purpose that matches one closely. **`Projects/` (work planning, Kanban board) is core, not a module choice — see `## Projects (core)` below** — every vault gets it regardless of which of the following are also selected.

- **General Wiki** — use when the goal is a broad, growing reference with no production pipeline attached. Value comes from capture discipline: the wiki only compounds if sources actually get ingested and cross-linked, not left sitting in `Inbox/`. Pitfall: an `Inbox/` that never empties.
- **Content Production** — use for any recurring-output pipeline (video, newsletter, podcast) with external creators or sponsors to track. Value comes from keeping the self-node's covered-topics list current, so continuity checks on new ideas mean something. Pitfall: letting sponsor deliverable stages drift from reality — money and relationships ride on that data being right.
- **Team / Org Knowledge Base** — use when multiple people rely on the vault as shared institutional memory. Value comes from logging the *why* behind a decision, not just the outcome — that's what a reader needs in a year. Pitfall: a Decisions log that's really just a changelog with no rationale.
- **Personal CRM / Relationships** — use when the vault's primary job is relationships and follow-through, not topics. Value comes from logging interactions promptly so cadence tracking stays honest. Pitfall: only opening a contact's page once something's already overdue.
- **Research (base) + flavors** — pick a flavor when the vault's job needs source-backed claims; Research itself is never picked directly, it comes along automatically with whichever flavor(s) below are chosen. Value comes from getting the citation-rigor tier right for what's actually at stake — see Citation-rigor dial above. Pitfall: picking `strict` by default "to be safe" when the real content is closer to `standard` — over-strict rigor just makes claims tedious to write without adding real evidentiary value.
  - **Academic Paper** — use when the output has to survive a citation audit (a paper, thesis, or grounded research deliverable). Declares `strict` rigor. Value comes from atomic-claim discipline: resist writing prose summaries, force every claim onto its own sentence with a dual link (Source Note + pinpoint in-link). Pitfall: skipping the pinpoint in-link "to save time" — that rigor is the entire point of this flavor.
  - **Competitive Intelligence** — use when tracking how entities (competitors, products, markets) change over time. Declares `standard` rigor. Value comes from append-don't-overwrite timeline discipline, so you can see the arc of a competitor's moves, not just their current state. Pitfall: overwriting old facts on an entity page, which destroys the "how did we get here" record that's the whole point of this flavor.
  - **Product Discovery / Decision-Making** — use when the job is deciding what to build or pursue, not tracking what already exists. Declares `standard` rigor. Value comes from populating opportunities with real evidence (switch interviews, usage data) rather than assumptions before scoring them. Pitfall: scoring an idea (RICE/ICE) before the opportunity it serves has any real evidence behind it — the score becomes a confident-sounding guess.
  - **Product Feasibility** — use when the question is *can we build it*, not whether it's worth building (Product Discovery / Decision-Making) or how it compares to the alternatives (Opportunity Cost / Options Comparison, below). Declares `standard` rigor. Value comes from time-boxing the investigation — a spike with a fixed hour budget forces an actual verdict, or an explicit "invest more time" decision, rather than open-ended exploration. Pitfall: running a spike without a narrow, answerable question — an unscoped "is this feasible" investigation just becomes unstructured research with a deadline attached.
  - **Opportunity Cost / Options Comparison** — use when comparing mutually exclusive options against what pursuing each one forecloses, rather than scoring any one of them independently. Declares `standard` rigor. Value comes from the explicit foreclosed-cost column — naming what's given up by each option *not* chosen, not just scoring what's chosen. Pitfall: running the full comparison on a decision that didn't actually need to be made yet — an explicit defer gate exists specifically to catch that before real effort goes into scoring options that could instead be kept open.
  - **Due Diligence** — use when investigating whether to pursue, invest in, or acquire a business or opportunity — verifying claims across financial documents, business plans, and meeting transcripts before a go/no-go decision. Declares `standard` rigor. Value comes from a severity-ranked, owned open-items register that survives past the meeting where a question was raised, not a pile of ingested documents nobody cross-checked. Pitfall: treating ingestion as the finish line — a financial statement sitting next to a business plan that quotes different numbers, with nothing flagging the conflict, isn't meaningfully more useful than the same files sitting in a deal folder.
  - **Investment Strategy** — use for building and continually improving your own investing rules: indicator-based entry, exit, stop and sizing rules for stocks, ETFs and crypto, grouped into strategies per need, graded per asset class from imported backtests and your own trades, optionally inside a portfolio policy set from your goals, risk and years to invest. Declares `standard` rigor. Value comes from the loop: every rule traces back to the research that suggested it and forward to the backtests and trades that support or weaken it, every source is trusted only as far as other evidence confirms it, and each rulebook states what changed since the last one and why. Pitfall: treating a rule as proven because it sounds convincing or looked good on one backtest — grades always show their evidence level, and nothing is promoted on in-sample results or a small sample.
- **Projections (base)** — never picked directly; comes along automatically with Due Diligence, Opportunity Cost / Options Comparison, or Product Discovery / Decision-Making, each of which declares a projection profile. Gives a period-by-period timeline/cost/revenue projection (month-by-month over 12 months by default) that gets revised as new details arrive. Value comes from the projection being honest about its weak spots: every assumption is labeled by how well it's supported, and anything thin, missing, conflicting, or high-leverage is tracked as an open issue that each update is checked against. Pitfall: a clean-looking 12-month grid built mostly on guesses reads as more solid than it is — which is why the confidence tally is always shown next to the outputs.
- **Meeting Transcript Ingestion** — use when meetings are a recurring input worth capturing as raw source material, not just a paraphrased summary. Standalone module, no Research dependency. Value comes from treating the transcript as an immutable Raw source like any article/video, so decisions and action items extracted from it stay traceable back to what was actually said. Pitfall: ingesting a transcript wholesale without extracting anything — a wall of text nobody re-reads isn't meaningfully more useful than the recording tool's own archive.
- **Stand-up Comedy** — use when developing your own stand-up material: ideas grown into premises, branching joke directions, versioned bits, and sets ordered around callbacks, with stage scores feeding back into the bits. Standalone module. Value comes from the links between pieces — which bits plant callbacks for which, what parked branches could still become, how each bit has actually done on stage — plus a prior-use check against other comedians' work and an evidence-backed review before any bit is marked burned (publicly released, and locked as a record). Pitfall: letting suggestions blur into your own voice — Claude's feedback, research and alternatives always sit in marked callouts and are never written into your joke text.
- **Travel Planning** — use when planning vacations and road trips, domestic or international: destinations, ways to get between places, stays and activities with basic cost estimates for your actual party (adults, and children by age), dated prep, packing, a country check for international trips, and an itinerary sized to the trip. Standalone module. Value comes from keeping each fact in one place: bookings and chosen items are the source of truth, the itinerary is generated from them, and Place pages carry what you learned into the next trip. Pitfall: treating researched prices, hours or country rules as settled. Every one carries its source and the date it was checked, and a country rule is never stated from memory.

**Running multiple vaults is a supported pattern, not a workaround.** Rather than combining every module into one vault, it's equally valid to run several separate, purpose-specific vaults (e.g. a personal second brain and a content-archive vault) and point an agent at whichever one's context is needed for the task at hand, since each vault's own `2b-instructions.md` (plus its `CLAUDE.md`/`AGENTS.md`/etc. stubs) explains how to read it. A looser variant works too: several named knowledge bases as sibling subfolders under one shared root, each with its own `2b-instructions.md`, rather than fully separate top-level vaults.

## Recipes (common module combinations)

**Why this section exists:** picking modules one at a time from a free-text description of the vault's purpose is a judgment call made fresh every time — the same stated purpose, given to `init-vault` on five separate occasions, is not guaranteed to land on exactly the same module set each time, since nothing anchors the recommendation to a fixed reference point. A **Recipe** is that fixed reference point: a named, versioned module combination for a common real-world need, defined once here rather than re-derived from scratch on every bootstrap. Recipes make module selection **more consistent, not perfectly deterministic** — matching a stated purpose against a recipe is still a judgment call, just a much narrower one (pick the closest of ~8 named options, then confirm/adjust) than freely composing from 11 individual modules.

**How recipes get used (see `Operation: init-vault`'s Interview step 2 and `Operation: add-use-case` step 2 for exactly where this plugs in):**

1. **Quick-start:** the user may name a recipe directly ("set this up for investment due diligence") instead of describing their purpose in their own words. Offer the named recipe's module set for confirmation.
2. **Free-text comparison:** if the user instead describes their purpose in long-form free text (the existing Interview flow), compare that description against every recipe below for a match or partial match, and lead with the closest one as a starting point — e.g. *"this sounds closest to the Investment / Deal Due Diligence recipe, which also normally includes Meeting Transcript Ingestion — want that too?"* — rather than deriving a module list independently each time. If nothing below is a reasonable match, fall back to walking the Help section module-by-module as before; forcing a poor-fit recipe is worse than admitting none fits.
3. **Never silent:** a recipe is always a *starting point*, shown to the user for confirmation/editing before `Assemble` runs — exactly the same confirm-before-apply discipline every individual module pick already gets. Adding, dropping, or swapping a module from a recipe's default set is expected and fully supported, not a deviation to talk the user out of.

Each recipe names its modules as **core members** (what the recipe is actually built around) and **optional add-ons** (common, but skip them if they don't fit) — a required flavor's own base module(s) — Research, plus Projections for Due Diligence, Opportunity Cost / Options Comparison, and Product Discovery / Decision-Making — are implied wherever a flavor is named, per the usual base+flavor rule, and aren't listed separately below.

- **General Knowledge Base** — *use when the purpose is broad/exploratory, with no specific pipeline or decision shape yet.* Core: General Wiki. This is the existing no-module default, named here so it's a visible option rather than only a fallback buried in the Interview's wording.
- **Academic Research** — *use when producing a paper, thesis, or any deliverable that has to survive a citation audit.* Core: Academic Paper (pulls in Research). About as close to a single-module pick as a recipe gets, but common enough to name.
- **Team / Org Knowledge Base + Meetings** — *use when standing up shared institutional memory for a team that runs a lot of recorded meetings.* Core: Team / Org Knowledge Base + Meeting Transcript Ingestion. Optional: Personal CRM, if the team also wants per-person relationship tracking distinct from the plain `People/` roster Team/Org KB already gives. Why together: a Decisions log gets far more useful when transcripts feed it directly instead of being manually summarized after the fact.
- **Content Creator Operations** — *use when running a recurring content pipeline (video, newsletter, podcast) with sponsors or competitors to track.* Core: Content Production + Competitive Intelligence (pulls in Research). Optional: Personal CRM, for sponsor/creator-relationship follow-through specifically.
- **Competitive / Market Watch** — *use when the job is purely tracking how competitors, products, or markets move over time — not deciding what to build in response.* Core: Competitive Intelligence (pulls in Research), alone. Kept separate from Product Strategy & Roadmap Decisions below precisely because tracking and deciding are different jobs — see that flavor's own "Distinction from sibling flavors."
- **Product Strategy & Roadmap Decisions** — *use when the question is what to build, whether it's buildable, and how it compares to the alternatives — the full "should we build this" chain.* Core: Product Discovery / Decision-Making + Product Feasibility + Opportunity Cost / Options Comparison (pulls in Research). Optional: Competitive Intelligence, if market positioning also matters. Why together: these three flavors are explicitly designed to chain on one real decision while staying separate (see each one's own "Distinction from sibling flavors" callout) — a strategy-focused vault very often wants two or three of them from day one, not just one in isolation.
- **Investment / Deal Due Diligence** — *use when investigating a new business opportunity, investment, or acquisition — verifying financial documents, business plans, and meetings before a go/no-go.* Core: Due Diligence (pulls in Research) + Meeting Transcript Ingestion. Optional: Product Feasibility and/or Opportunity Cost / Options Comparison, once the underlying facts are verified and the question shifts to buildability or comparing multiple live deals — not needed on day one; Personal CRM, if tracking many counterparties/investors by name matters as much as tracking the deal itself.
- **Personal CRM / Relationship-First** — *use when the vault's primary job is people and follow-through, not topics.* Core: Personal CRM, alone. Optional: Meeting Transcript Ingestion, if a lot of relationship-building happens over recorded calls. Kept distinct from the optional Personal-CRM add-ons above — here it's the primary layer, not a bolt-on to another module's own purpose.
- **Comedy Writer / Performer** — *use when developing and performing your own stand-up material.* Core: Stand-up Comedy, alone. Optional: Content Production, if you also publish clips (it handles the publishing pipeline; Stand-up Comedy's Burn review decides what a clip spends); Personal CRM, for bookers, venues, and other comics as relationships rather than plain Entity pages.
- **Investor / Trader Strategy Development** — *use when building, testing and refining your own investing rules and strategies (stocks, ETFs, crypto) from research, backtests and your own trade history.* Core: Investment Strategy (pulls in Research), alone. Optional: Due Diligence, for fundamentals research on individual holdings; Competitive Intelligence, for company or sector timelines; Opportunity Cost / Options Comparison, for one-off allocation decisions between strategies. Best run as its own vault, since it holds personal trade and account history.
- **Travel Planner** — *use when planning vacations, road trips or international travel.* Core: Travel Planning, alone. Optional: Opportunity Cost / Options Comparison, for big one-off decisions such as which destination, or flying vs. driving (it pulls in Research and Projections, so it's only worth adding if those decisions come up often); Personal CRM, for travel companions or hosts as relationships. Best run as its own vault, since it holds booking references and travel-document dates.

**Adding a recipe:** treat this the same as adding a Module Library entry — a genuine, common real-world need, not a one-off. Bump this section's own version-tracking the same way any other core-section change does (see the Generator-version changelog).

## Core vault map

These layers exist in **every** vault regardless of which modules are active. Folders are functional layers reflecting how data is processed, not topics — keep the structure flat.

- `Raw/` — immutable original sources. Never edit a file here after creation. A web-clipper capture lands here the same way a manually fetched URL does.
- `Inbox/` — quick captures, digests, and dropped-in data waiting to be processed.
- `Assets/` — binary attachments: screenshots, images, exported PDF excerpts, and other non-markdown evidence (e.g. a screenshot of a figure or graph from a source). Keeps `Raw/`, `Wiki/`, and `Outputs/` markdown-only — pages embed from here (`![[Assets/figure-3.png]]`) on the relevant Raw/External source page rather than storing binaries inline, so the visual anchor surfaces when hovering the source link later.
- `Wiki/` — the compounding knowledge layer. Claude owns this layer.
  - `Wiki/Index.md` — catalog of every maintained page across all layers, read first on any query. Beyond a flat page list, include: relationship mappings between related pages, thematic concept clusters (pages bundled by topic, not just folder), evidence trails for load-bearing claims (which source backs what), and navigation paths for different reading needs (e.g. "new to this vault, start here"). Mermaid diagrams are a useful but optional way to visualize connections — only worth the upkeep once a vault has enough pages that a diagram stays legible. Keep this current through the same automated workflows that maintain everything else — a stale relationship map is worse than none.
  - `Wiki/Log.md` — append-only operation log.
  - `Wiki/Entities/` — people, organizations, products, companies, or other named actors.
  - `Wiki/Concepts/` — ideas, frameworks, and recurring themes. Claims here interpret but never speculate — every claim traces back to a Summary or Source. Speculation belongs in `Wiki/Arguments/` instead.
  - `Wiki/Summaries/` — one summary page per ingested source.
  - `Wiki/Arguments/` — the thinking garden: open questions, hypotheses, drafts, and speculative connections across Concepts and Entities. This is the one Wiki subfolder explicitly exempt from "never invent facts" — it exists so speculation has somewhere to live instead of leaking into Concepts, Entities, or Outputs. An idea graduates out of Arguments once it's disciplined and receipt-backed enough to become an Outputs page. Cultivate this folder continuously as sources are ingested (the "farmer" model) rather than searching for connections only once a deadline hits (the "hunter" model) — by the time a draft is needed, the ideas should already be grown.
- `Outputs/` — the output layer: receipt-backed conclusions, playbooks, or deliverables squeezed from the wiki. Every claim here cites the summary or data that backs it. `< OUTPUTS FOLDER NAME — init-vault may rename this to something more domain-specific, e.g. "Playbooks/", "Findings/", "Deliverables/"; update this map if renamed >`
- `Ecosystem.md` — dashboard of every active tool, subscription, API, or integration connected to this system, with purpose, cost, renewal date, and status. Used for budget and basic security review.
- `Routines/` — automated and recurring jobs: one page per routine, tracking schedule, status (`not-automated` / `active` / `broken`), last successful run, and errors. `Routines/Watchlists.md` is one such routine, purpose-built for watched YouTube playlists — see `Operation: check-watchlist`.
- `Projects/` (core, mandatory) — tracking and executing real work via one or more independent Kanban boards. See the `## Projects (core)` section below for the full folder/board/operations spec. Follow-up items and future extensions for the framework itself — a digest link, an ad-hoc source shortlist, a single one-off action — get a card on a board's Idea column the same way any other tracked work does; there is no separate lighter-weight tracker.
- `Dashboard.md` (root, optional) — see the Dashboard section below. Not part of the mandatory scaffold; built on request via `Operation: dashboard`.
- `Archived/` — finished topics moved out of the live vault by `Operation: archive`, one folder per archive (`Archived/<slug>-<YYYY-MM-DD>/`), each with the files in their original folder paths plus a restore index. Created by the first archive, not by the scaffold. Obsidian excludes it from search and the graph (see the standard `.obsidian/app.json`). Every operation except `restore` and `delete` treats it as outside the vault: nothing in it is read, linked to, or checked. The Tasks and Dataview plugins index the whole vault regardless of Obsidian's excluded files, so their queries may still show archived pages.

Module blocks (below) each layer additional folders on top of this core. A vault may run zero, one, or several modules at once.

## Conventions (core)

- Use wikilinks everywhere. Every person, organization, product, or concept with a page gets a wikilink on first mention.
- Wikilinks resolve by page name (or alias), never by folder path — write `[[Page Name]]`, not `[[Folder/Page Name]]`, even for a page that lives inside a dedicated module folder (`Opportunities/`, `Options/`, `Feasibility/`, `Content/`, etc.). Obsidian matches `[[...]]` against the vault's whole file/alias index regardless of where the target file sits; a folder-qualified target only resolves if that exact string happens to be the page's own title, so a path-prefixed link doesn't error, it just silently fails — the kind of mistake that can go unnoticed across dozens of cross-references until a lint pass catches it. Use a piped link (`[[Page Name|Folder: Page Name]]`) if the folder context is worth surfacing to the reader, never a path in the link target itself.
- **Page names are unique across the vault.** Links resolve by name, so two pages with the same filename in different folders make `[[Name]]` ambiguous: Obsidian silently picks one, and the rule above leaves no path to reach the other. This covers `.base` and `.canvas` files as well as notes. So:
  - Every fixed page a module scaffolds carries its module's name in the filename (`Content/Content Board.md`, not `Content/Board.md`). The core default board, `Projects/Board.md`, is the only page named `Board`.
  - Before creating any page, check the vault for an existing page or alias with that name, including in `Archived/`. If it's taken, choose a more specific name rather than reusing it.
  - An alias is never another page's name or alias.
  - The one exception is scaffolded `_Template.md` files. They're never linked to, and the standard app settings hide them from search.
- Every note starts with YAML frontmatter: `type`, `created`, `updated`, `tags` (see Tag taxonomy below), plus whatever fields the active module(s) add.
- Use absolute dates (`2026-07-13`), never relative ones ("yesterday", "last week").
- Claims in Wiki pages cite the relevant summary page. Claims in Outputs pages cite summaries or raw data.
- Entity and Concept pages use plain names (`OpenAI.md`), not prefixed.
- When a new source updates a fact about an existing Entity, append it to a dated timeline section on that Entity's page rather than overwriting the old value — the superseded fact stays visible with a plain update note, not deleted. See `## Contradiction handling` for what happens when the update actually conflicts with, rather than simply extends, an existing fact.
- Summary pages are named `S - <Title>.md`.
- Raw source pages are named `R - <Title>.md`.
- Never invent facts. If something isn't supported by a source, mark it `unverified`.
- Give every page an `aliases:` frontmatter field with natural shorthand names, so links read naturally inside a sentence without renaming the page itself.
- Any frontmatter field that names an Entity (`author`, `creator`, `company`, `client`, `journal`, etc.) should be a **wikilink value** (`author: [[Name]]`), not a plain string. This turns that field into a backlink hub: opening the Entity page shows every page pointing at it, automatically, with no manually maintained "papers by this author" list.
- When citing a Raw or External source, cite the most specific location it supports, not just the page: an Obsidian block reference (`^block-id`) for text, a timestamp for audio/video, a page/highlight reference for PDFs (the PDF++ plugin supports this natively). A bare link to the whole source page is a fallback, not the default — this is the same discipline the Content Production module already calls "beats," just generalized to any source type.
- Use embeds (`![[Note]]`) rather than copy-paste when stitching Concepts/Arguments content into a draft — the embed stays live if the source page is later corrected.
- Use piped links (`[[Note|anchor text]]`) to keep anchor text clean — especially for pinpoint links to a block ID or a long title — so the reader never sees a raw block ID or a cryptic filename inline.
- Use callouts (`> [!info]-`) as structured, collapsed-by-default containers for asides that would otherwise clutter a page: why a source matters personally, an AI-generated summary kept visually distinct from original analysis, etc. Collapse by default (the trailing `-`) to keep the page scannable.
- Any file written to `Inbox/` that's awaiting a user decision — a digest, an ad-hoc source shortlist, anything not yet ingested — gets a card added to `Projects/Board.md`'s Idea column (or the appropriate topic board's, if more than one is active) the same time it's created. `Inbox/` is easy to forget about once it's not the newest thing on screen; the Board is where follow-up visibility actually lives.
- Before writing wiki prose, follow an anti-AI writing style: no puffery, no undue emphasis, no promotional phrasing, no hedge-padding — the tells documented on Wikipedia's own "AI writing style" guidance page apply here too. Structural rigor (atomic claims, citations) doesn't excuse robotic prose.

## Tag taxonomy

Frontmatter (`type:`, `tags:`) plus wikilinks are enough to make the wiki *readable*. They are not enough to make Obsidian's **graph view** and tag pane useful for filtering and clustering — for that, every page also carries namespaced tags, applied consistently so the graph can be sliced by more than folder location.

Required on every page (core, all modules):

- `#type/<kind>` — matches the page's frontmatter `type` field. Core kinds: `#type/source`, `#type/summary`, `#type/entity`, `#type/concept`, `#type/argument`, `#type/output`, `#type/project`, `#type/milestone`, `#type/directory` (the last three from `Projects/`, core and mandatory — see `## Projects (core)`). Each module adds its own kinds (see module blocks) — always `#type/<kind>`, never a second taxonomy.
- `#status/<state>` — coarse lifecycle state for graph filtering: `#status/idea`, `#status/active`, `#status/done`, `#status/stale`, `#status/unverified`, `#status/contradiction-open` (a page carrying a flagged, unresolved contradiction — see `## Contradiction handling`; reverts to `#status/active` once resolved). This is deliberately coarser than any module's own `status:` frontmatter field (e.g. a Content Production page might have `status: sponsor-approval` in frontmatter *and* `#status/active` as its tag) — the tag is for graph slicing, the frontmatter field is for precise pipeline state.

Optional but encouraged:

- `#topic/<slug>` — free-form topic tag for graph clustering, applied to Concepts, Entities, and Summaries. Multiple per page is normal. This is what lets the graph view reveal topic clusters and topic velocity across otherwise-unrelated pages.

Rules:

- Tags are lowercase, kebab-case within the slug (`#topic/prompt-caching`, not `#topic/PromptCaching`).
- Don't invent a second namespace for something a module tag already covers.
- `lint` (below) checks every page for a `#type/*` and `#status/*` tag and flags pages missing either.

## Graph view setup

Graph View color groups come preconfigured: the standard `.obsidian/graph.json` (see `## Standard files (core)` below) colors every core and module folder by what its layer does — evidence in teal, built knowledge in blue→violet, speculation in orange, finished output in green, work in yellow, unprocessed captures in red — plus status overrides (e.g. `#status/contradiction-open`) that win over folder color. No manual setup is needed. This makes "what did I read" vs. "what do I think" visible at a glance, and makes topic clusters (via `#topic/*`) walkable: following the graph between two unrelated topics through a shared intermediary node is how new Arguments-worthy connections tend to surface.

## Dynamic views (Bases / Dataview)

`Wiki/Index.md` is the hand-maintained table of contents — good for "what pages exist," bad for "show me everything tagged `#status/active`" or "sort every source by year." For anything better expressed as a live filtered list than a manually updated one, set up a property-driven view instead, using Obsidian's built-in Bases feature (or the Dataview community plugin on older Obsidian versions — note whichever is in use in `Ecosystem.md`):

- Filter by folder or `type` (e.g. everything where `folder is Raw`).
- Sort/filter by any frontmatter property (`year`, `rating`, `status`, `target-date`).
- Worth setting up in nearly every vault regardless of active module: a reading/backlog list, an "active" list, and a chronological archive.

These views self-maintain as long as frontmatter stays accurate — they are not something Claude regenerates by hand, only something Claude keeps the underlying properties correct for.

## Projects (core)

Every vault tracks execution of real work — not just accumulated knowledge — via one or more independent Kanban boards. **Easy mode by default, expandable when needed:** a fresh vault gets exactly one board (`Projects/Board.md`) and never has to think about which board a task belongs on. Running `Operation: new-board <topic>` to add a second, purpose-specific board is a deliberate opt-in, not something pushed toward: it buys real separation but adds a small ongoing cost from that point on, since every task/project creation then needs its board confirmed. Stay single-board until mixing everything together actually becomes the friction.

- **Folders — one or more independent boards, each with its own nested task folder:** `Projects/Board.md` is the default board; its task pages (frontmatter: `type: project`, `status`, `target-date`) live in `Projects/Board-Tasks/`, not flat in `Projects/` (a permanent naming exception — the default board's file stays `Board.md`, never `Board-Tasks.md`, only its task folder carries the `-Tasks` suffix). Additional topic boards follow `Projects/Board-<Topic>.md` (the board file) with its own `Projects/Board-<Topic>/*.md` (that board's task pages, Title Case with spaces, e.g. `Board-Client Work.md` / `Board-Client Work/`). Every board is fully independent — no shared task pool between boards, and no automatic mechanism to move a task from one board to another (a manual file move, done only when actually needed).
- **New pages:** `Projects/Board.md` (and each `Projects/Board-<Topic>.md`) — Kanban board (Obsidian Kanban plugin), columns customizable per vault but typically `Idea → Planned → In Progress → Blocked → Review → Done`, cloned automatically for every new board; `Projects/Directory.md` — a **singleton** manifest (exactly one per vault, not a `_Template.md`-style page stamped out per instance) mapping every active board to its folder and purpose (`Board | Folder | Description | Status` table), scaffolded once with the default board's row and thereafter auto-maintained by `Operation: new-board` rather than hand-edited, distinct from `Wiki/Index.md`'s page-level catalog since this is board-level (one row per board).
- **Multi-lens views:** the fixed Kanban board isn't the only view of this data — set up additional Bases/Dataview views over the same `Projects/` pages (recursive across every board's task folder — Dataview's folder source already includes subfolders, no query change needed) for other decisions: a timeline/deadline view, an Eisenhower-style importance-vs-urgency view, a per-week plan. Same underlying project data, different lens depending on what question is being asked. These are supplementary views, not a replacement for any board file.
- **Two-tier task hierarchy:** work is tracked at two distinct granularities — macro tasks (a project/work package) live as `Projects/Board-Tasks/*.md` (or a topic board's own folder) pages and cards on that board; micro tasks (individual checklist items within a project page, e.g. several unrelated open questions bundled under one card) aren't given their own board cards, they're aggregated dynamically via a Tasks-plugin/Dataview query instead.
- **Tags:** `#type/project`, `#type/milestone`, `#type/directory` (for `Projects/Directory.md`).
- **Card-state tags, orthogonal to column:** any board card may carry one or more `#status/<state>` tags independent of which column it's in — `#status/blocked` (something external is stopping progress), `#status/waiting-on-answer` (paused pending a response), `#status/answered` (a response has landed but the card isn't fully closed out yet), `#status/at-risk` (still moving but flagged as endangered). Column tracks *where* a card is in the workflow; these tags track *why* it's stuck, if it is — a card can sit in "In Progress" while also carrying `#status/blocked`, without losing its progress context by being moved to the "Blocked" column. **Highlighting:** the Kanban plugin natively maps a hashtag to a custom background/text color, applied live to any card carrying it — no new plugin or CSS snippet needed. This is a one-time manual setup step for the user, not something `init-vault`'s Scaffold step applies automatically: Claude can state a suggested color mapping (blocked = red, waiting-on-answer = amber, answered = green, at-risk = orange) for the user to enter in the Kanban plugin's own settings UI, same "Claude can check plugin state but not configure plugin-internal settings" limitation already documented for community plugins generally (see Recommended plugins below) — the tags themselves work as plain wikilink tags regardless of whether colors are ever configured; only the visual highlighting depends on this manual step.
- **Dated/recurring Milestones (Tasks plugin):** individual Milestone checklist items on a task page may carry a Tasks-plugin-format due date and/or recurrence directly on the line (e.g. `- [ ] Ship v1 📅 2026-08-15 🔁 every week`), not just the whole-project `target-date` — this is what makes "upcoming due dates" and recurring work items queryable at the granularity that actually matters. Without the Tasks plugin, dated Milestones degrade to plain undated checklist items — the rest of `Projects/`, Board and all, still works fine.
- **Deadline hook:** project milestone due dates feed both `Operation: review`'s deadline sweep and `Operation: plan-day`'s morning synthesis — the same underlying Tasks-plugin query (due today/overdue across every board's task pages), each operation applying it for its own purpose (periodic sweep vs. daily plan). Indexes vault-wide regardless of file location, so this needs no per-board query changes as boards are added. Degrades gracefully to just the staleness half of the Dashboard's needs-attention widget (below) if the Tasks plugin isn't installed.
- **Independence:** every board is kept separate both from any other core/module file (e.g. Content Production's `Content/Content Board.md`, if that module is also active) and from every *other* board within `Projects/` itself — no shared task pool, no path collisions, no merging. Stacking modules, or stacking multiple boards within `Projects/`, never merges or overwrites another board's file.

**Operations:** see `Operation: plan-project` and `Operation: new-board` under Core operations below. **Boundaries:** see the board-confirmation and WIP-limit entries under Boundaries (core) below.

## Recommended plugins

Core (every vault, regardless of active modules):

- **Bases** — built into current Obsidian versions (a core plugin toggled on, not installed) — the primary mechanism for the dynamic views above.
- **Dataview** — community plugin fallback for Obsidian versions that predate Bases, or for anyone who prefers its query syntax. Not needed alongside Bases unless the user wants both.
- **Kanban** — renders `Projects/Board.md` (and any additional topic board) as an actual Kanban board; degrades gracefully to a plain checklist without it.
- **Tasks** — required for dated/recurring Milestone checklist items on `Projects/` task pages (see `## Projects (core)`); without it, Milestones degrade to plain undated checklist items, and the rest of `Projects/` still works fine.
- **Tasks Calendar Wrapper** — calendar view of Tasks-plugin due dates across every board; confirmed to read Tasks plugin's native emoji date format, unlike Full Calendar, which does not.

Module-specific plugins are listed in each module's own block in the Module Library below (e.g. Kanban for board-based modules, PDF++ and a web clipper for the Research base module). `Operation: init-vault` step 4 consolidates core + whichever modules were selected into one list.

**What Claude can and can't check:** a vault's `.obsidian/community-plugins.json` lists enabled community plugins by ID, and `.obsidian/plugins/<id>/` shows what's installed (even if disabled); `.obsidian/core-plugins.json` shows which built-in core plugins (like `bases`) are toggled on. Claude can read these directly and report what's already present versus missing — genuinely useful, not a guess. What Claude **cannot** do is install or enable a community plugin itself: that requires the user acting inside Obsidian's own UI (Settings → Community plugins → Browse → search by name → Install → Enable). Browser-extension-based tools (e.g. Obsidian Web Clipper, which runs in Chrome/Firefox, not inside the vault) never show up in `.obsidian/` at all — Claude can recommend them but can't verify whether they're installed.

## Standard files (core)

Ready-made files placed into a vault's own folders, so every vault built from this generator looks and behaves the same with no manual configuration. Each `### Standard file:` block below gives its target path, a `**File version:**` line, an `**Apply:**` line, and the exact file content. The Apply line says what the standard owns in an existing file: `whole-file`, one named key (e.g. `color-groups`), or `keys` (only the keys the standard lists, merged into the file). Obsidian app settings (`.obsidian/app.json`) are one of these standard files. A standard file may include entries for folders a given vault doesn't have, e.g. graph colors for modules that aren't active. Those entries match nothing and are harmless.

**How a standard file is applied:**

- **Target doesn't exist yet** (a genuinely fresh vault): `init-vault`'s Scaffold step writes it as given.
- **Target already exists** (any `update-vault` run, or `init-vault` in a vault Obsidian already opened): **never overwrite silently.** For each standard file whose File version differs from the one recorded in `## Generator versions`, or that has none recorded:
  1. **Ask whether to set the standard as this vault's default**, showing what differs: entries the standard would add, change or remove, and any of the vault's own entries that aren't in the standard.
  2. **Offer three choices.** (a) **Adopt the owned part**: only what `**Apply:**` names is replaced, and everything else in the file is kept. For `color-groups`, the vault's own display and force settings stay; any custom groups not in the standard are listed, and the user decides per group whether to keep it, with kept groups placed ahead of the standard ones so they still take effect. For `keys`, only the listed keys are set and every other key is untouched. A listed key that already has a different value is shown and changed only on confirmation, since it's likely a deliberate choice. A list value (e.g. `userIgnoreFilters`) is merged: the standard's entries are added, the vault's own entries are kept, and only entries named on the block's **Supersedes** line are removed. (b) **Replace the whole file** (not offered for `keys`, since the file also holds settings the standard doesn't own). (c) **Skip.**
  3. **Confirm before writing**, then record the outcome in `## Generator versions` (e.g. `- standard-file graph.json: 1.0 (adopted)`, `(replaced)` or `(declined)`). A declined version isn't offered again; a newer File version is.
- **If Obsidian is open:** Obsidian holds some settings in memory and can write its own copy back over the new file. Ask the user to close any open view that uses the file (for `graph.json`, the graph view) before the write, and to reopen it after.

### Standard file: .obsidian/app.json

**File version: 1.1**

**Apply:** keys

**Supersedes:** `/Index/`, `/Log/`, `/_Template/` (the ignore filters from the earlier core app settings)

Obsidian app settings that put core conventions into Obsidian's own behavior. Line numbers are on and non-markdown files stay visible. Attachments land in `Assets/` and new notes in `Inbox/`. New links are wikilinks by page name, updated automatically when a page is renamed. The ignore filters keep machine-maintained and meta files, and archived topics (`Archived/`, see `Operation: archive`), out of search, graph view and unlinked mentions. Each filter is anchored to an exact file, because an entry wrapped in slashes is a pattern that can match anywhere in a path.

```json
{
  "showLineNumber": true,
  "showUnsupportedFiles": true,
  "attachmentFolderPath": "Assets",
  "newFileLocation": "folder",
  "newFileFolderPath": "Inbox",
  "useMarkdownLinks": false,
  "newLinkFormat": "shortest",
  "alwaysUpdateLinks": true,
  "userIgnoreFilters": [
    "Wiki/Index.md",
    "Wiki/Log.md",
    "/_Template\\.md$/",
    "2b-init.md",
    "CLAUDE.md",
    "AGENTS.md",
    "GEMINI.md",
    "Archived/"
  ]
}
```

### Standard file: .obsidian/graph.json

**File version: 1.2**

**Apply:** color-groups

Color groups for Obsidian's graph view, covering every core and Module Library folder. Obsidian uses the first group that matches a note, so the order is: status overrides, then specific subfolders, then broad folders. Paths are quoted with a trailing slash (`path:"Raw/"`) so a folder name can't match part of a filename. Display and force settings are defaults for a vault with no `graph.json` yet. View state Obsidian rewrites itself (`scale`, `close`, `search`) is left out.

```json
{
  "collapse-filter": true,
  "search": "",
  "showTags": false,
  "showAttachments": false,
  "hideUnresolved": false,
  "showOrphans": true,
  "collapse-color-groups": false,
  "colorGroups": [
    { "query": "tag:#status/contradiction-open", "color": { "a": 1, "rgb": 16711935 } },
    { "query": "tag:#status/burned", "color": { "a": 1, "rgb": 4674921 } },
    { "query": "tag:#status/invalidated", "color": { "a": 1, "rgb": 4674921 } },
    { "query": "path:\"Inbox/\"", "color": { "a": 1, "rgb": 15680580 } },
    { "query": "path:\"External Sources/\"", "color": { "a": 1, "rgb": 6220500 } },
    { "query": "path:\"Raw/\" OR path:\"Sources/\"", "color": { "a": 1, "rgb": 1357990 } },
    { "query": "path:\"Wiki/Summaries/\"", "color": { "a": 1, "rgb": 8246268 } },
    { "query": "path:\"Wiki/Concepts/\"", "color": { "a": 1, "rgb": 3900150 } },
    { "query": "path:\"Wiki/Entities/\"", "color": { "a": 1, "rgb": 9133302 } },
    { "query": "path:\"Wiki/Arguments/\"", "color": { "a": 1, "rgb": 16347926 } },
    { "query": "path:\"Outputs/\" OR path:\"Findings/\" OR path:\"Playbooks/\" OR path:\"Deliverables/\" OR path:\"Recommendations/\"", "color": { "a": 1, "rgb": 2278750 } },
    { "query": "path:\"Projects/\"", "color": { "a": 1, "rgb": 15381256 } },
    { "query": "path:\"Routines/\"", "color": { "a": 1, "rgb": 10576391 } },
    { "query": "path:\"Contacts/\" OR path:\"People/\" OR path:\"Interactions/\" OR path:\"Decisions.md\"", "color": { "a": 1, "rgb": 16628340 } },
    { "query": "path:\"Content/\" OR path:\"Sponsors/\" OR path:\"Armory/\"", "color": { "a": 1, "rgb": 15485081 } },
    { "query": "path:\"Opportunities/\"", "color": { "a": 1, "rgb": 10741301 } },
    { "query": "path:\"Options/\"", "color": { "a": 1, "rgb": 14285213 } },
    { "query": "path:\"Feasibility/\"", "color": { "a": 1, "rgb": 6660877 } },
    { "query": "path:\"Projections/\"", "color": { "a": 1, "rgb": 5078031 } },
    { "query": "path:\"Diligence/\"", "color": { "a": 1, "rgb": 12456508 } },
    { "query": "path:\"Comedy/Premises/\"", "color": { "a": 1, "rgb": 6809849 } },
    { "query": "path:\"Comedy/Bits/\"", "color": { "a": 1, "rgb": 440020 } },
    { "query": "path:\"Comedy/Chunks/\"", "color": { "a": 1, "rgb": 947344 } },
    { "query": "path:\"Comedy/Sets/\"", "color": { "a": 1, "rgb": 6514417 } },
    { "query": "path:\"Comedy/Performances/\"", "color": { "a": 1, "rgb": 10859772 } },
    { "query": "path:\"Comedy/Releases/\"", "color": { "a": 1, "rgb": 4405450 } },
    { "query": "path:\"Investing/Portfolio/\"", "color": { "a": 1, "rgb": 8788367 } },
    { "query": "path:\"Investing/Indicators/\"", "color": { "a": 1, "rgb": 15772668 } },
    { "query": "path:\"Investing/Conditions/\"", "color": { "a": 1, "rgb": 15235577 } },
    { "query": "path:\"Investing/Strategies/\"", "color": { "a": 1, "rgb": 14239471 } },
    { "query": "path:\"Investing/Rules/\"", "color": { "a": 1, "rgb": 12592851 } },
    { "query": "path:\"Investing/Backtests/\"", "color": { "a": 1, "rgb": 10624175 } },
    { "query": "path:\"Investing/Trades/\"", "color": { "a": 1, "rgb": 7346805 } },
    { "query": "path:\"Travel/Places/\"", "color": { "a": 1, "rgb": 16622767 } },
    { "query": "path:\"Travel/Trips/\"", "color": { "a": 1, "rgb": 14753096 } },
    { "query": "path:\"Travel/\"", "color": { "a": 1, "rgb": 10424889 } },
    { "query": "path:\"Use Cases/\"", "color": { "a": 1, "rgb": 16478597 } },
    { "query": "path:\"Standard Files/\"", "color": { "a": 1, "rgb": 9741240 } }
  ],
  "collapse-display": true,
  "showArrow": false,
  "textFadeMultiplier": 0,
  "nodeSizeMultiplier": 1,
  "lineSizeMultiplier": 1,
  "collapse-forces": true,
  "centerStrength": 0.52,
  "repelStrength": 10,
  "linkStrength": 1,
  "linkDistance": 250
}
```

## Citation-rigor dial

Not every module needs the same citation discipline — a competitor-timeline entry and a thesis claim don't carry the same evidentiary bar. Rather than each research-oriented module hard-coding its own citation mechanic, the Research base module (see Module Library) and every flavor that requires it each declare a **citation-rigor tier**, resolved once per vault into a single active setting:

- **`strict`** — atomic-claim + dual-link discipline: one claim per sentence, each carrying both a Source Note link and a pinpoint in-link (block reference, timestamp, or PDF++ page/highlight). Lint-enforced — a claim with only one of the two links is a lint failure, not a style note.
- **`standard`** — a citation is required on every claim, but no mandatory pinpoint in-link. A bare link to the source page is sufficient.
- **`light`** — citation recommended, not lint-enforced.

**Resolution: per-vault, strictest-active-flavor-wins.** When multiple flavors requiring Research are active at once, the vault's single resolved `citation-rigor` setting is the strictest tier declared by any of them — never "whichever was added last," and never silently loosened when a looser flavor is added later. This is computed automatically at `init-vault` time (from the flavors selected in the Interview) and recomputed — shown as a proposed change, never silently applied — whenever `Operation: add-use-case` activates a new flavor.

The resolved value lives in the vault's `## Vault config` section (below) and is read by `lint` (to decide whether the strict-tier checks apply), `draft` (to decide how heavily an output's claims need sourcing), and any flavor's own Boundaries that reference "the active rigor tier."

## Vault config

A small, structured section in every initialized vault's `2b-instructions.md`, holding resolved cross-module settings — distinct from `## Generator versions` (which tracks what the vault was built *from*, not what it's configured to *do*):

```
## Vault config
- citation-rigor: <resolved tier>
```

`init-vault`'s Assemble step writes this section for the first time, computed from the selected modules (only present at all if a Research-requiring flavor was selected). `Operation: config` (below) is the only supported way to review or change it afterward — never hand-edit this section directly, so `Wiki/Log.md` always has a record of who changed what and why. Future vault-level settings beyond citation-rigor belong in this same section as new lines, not a second config mechanism.

## Contradiction handling

Two independently-sourced claims sometimes genuinely conflict — not a specificity difference, but mutually exclusive statements about the same fact. This section defines how that gets detected, marked, and resolved, so a contradiction is surfaced explicitly rather than silently smoothed over or left for a reader to stumble on unannounced. It extends, rather than replaces, the core Boundary "deprecate and link forward instead of deleting" (below) for the specific case of two sourced claims in tension, not just one page going stale.

**Detection (runs as part of `Operation: ingest` step 4 — ripple through touched Entities/Concepts):** when a new source's claim lands on a page that already has a claim about the same fact, classify it before writing anything:
- No prior claim on this point → append normally, nothing else applies.
- Same claim, corroborating → add provenance only (a second citation), no new marking.
- More specific than the existing claim, not actually contradictory (a **granularity** difference — e.g. "Q3 2026" vs. "2026") → propose refining the existing claim in place, resolved live in conversation with the user during the ingest itself. No flag, no task.
- Mutually exclusive with the existing claim (a **contradictory** conflict — e.g. two different dates for the same event) → classify by stakes. A **substantial** contradiction (the existing claim is cited by a Use Case's "How it works," a Recommendation, or is otherwise load-bearing) is always flagged automatically — no need to ask before flagging it, only before resolving it. A **minor** contradiction (a peripheral/detail-level claim) is surfaced live during the ingest conversation instead and resolved with the user in the moment; it only escalates to the full flagging below if the user asks for that.

**Marking a flagged contradiction:**
- Under `strict` citation-rigor (atomic claim + dual link per sentence), the old claim's sentence gets `> [!warning] Contradiction — see [[S - <New Source>]]` directly beneath it; the new claim's sentence gets a matching back-link to the old one.
- Under `standard`/`light` rigor, where claims aren't reliably anchored at sentence granularity, the same callout attaches at the top of the whole Concept/Entity page instead — a coarser anchor, same mechanic.
- Both sides' Summary/Raw pages get a one-line cross-reference too, so the contradiction is visible from the source level, not only the derived-claim level.
- The page(s) carrying the callout get `#status/contradiction-open` (see Tag taxonomy).
- A card lands on the relevant `Projects/` board's Idea column, with its own task page — `Review contradiction: [[<old page>]] vs [[<new page>]]` — same as any other follow-up item, per the core rule that every follow-up gets a card.

**Resolving a flagged contradiction** (worked out on the task page, never silently):
- **New source of truth:** the old claim's callout becomes a `superseded by [[<new page>]]` note. The old claim is kept in place, never deleted or edited away — same discipline as `Raw/` immutability and the Entity-timeline convention above.
- **Both stand, different contexts:** each claim (old and new) gets a `**Scope:**` line added in place, stating when/where it applies. The warning callouts are removed once the scope lines are in place — the scoping *is* the resolution.
- Either way, the actual reasoning goes on the task page itself, not just the outcome — the same discipline `Decisions.md` (Team/Org Knowledge Base) already applies to its own append-only corrections.
- **On resolution, sweep for stale citations:** search the vault for other pages linking to the affected Concept/Entity page (`Use Cases/`, `Recommendations/`, `Outputs/`, `Projects/` especially) and list any hits on the task page as "may need review" — surfaced, never auto-edited. This is a one-time check run at resolution time, not a standing query.

## Dashboard

`Dashboard.md` is an **optional** core page — not part of every vault's mandatory scaffold, but any vault can have one, built and refreshed by `Operation: dashboard` (below) from two widget sources:

- **Core widgets** — exist regardless of which modules are active: total `Wiki/Concepts/` count, recent `Wiki/Log.md` activity, **Resurfaced items** (below), and **needs attention** — upcoming-due/overdue Milestones, stale projects, and cards carrying a `#status/blocked` or `#status/waiting-on-answer` tag (see `## Projects (core)`'s card-state tags), across every `Projects/` board, all carrying a Board column so a row's board is visible without opening the page when more than one board is active. Defined once here, not per module.
- **Module-specific widgets** — each module/flavor in the Module Library *may* declare a `**Dashboard contribution:**` line in its block (parallel to `**Output template:**`, equally optional) describing what of its own assets is worth surfacing and how. Not every module needs one — a module with nothing dashboard-worthy simply omits the line, same as a module with no extra Boundaries omits that line. Mirrored the same way in the corresponding `Use Cases/*.md` file's "How it works" section for any vault that maintains module designs as separate source files and syncs them into a Module Library this way.

**Rendering:** widgets are Bases/Dataview query embeds wherever the underlying data supports live filtering (counts, "due soon," recent activity) — consistent with the existing Dynamic views convention, so the dashboard self-maintains as long as frontmatter/checklist metadata stays accurate rather than needing manual regeneration. A widget that genuinely can't be expressed as a live query (rare) falls back to something `Operation: dashboard` recomputes on request.

**Resurfaced items (core widget):** a small, deterministic daily rotation surfacing old, easy-to-forget material — specifically `Wiki/Arguments/` pages with no recent update (speculative ideas that went cold) and `Inbox/` items awaiting a decision that never got made. Deterministic by design (seeded by the day's date, e.g. via a DataviewJS selection keyed on `dayOfYear % candidateCount`) so it rotates on its own without a scheduler and shows the same picks all day rather than reshuffling on every reload. Starts minimal — these two sources only, not every core folder — and is meant to expand only once it earns its keep, not speculatively. This is the core-level analogue of a module's own `**Dashboard contribution:**` line, just not tied to any one module since both source folders exist in every vault regardless of active modules.

**Not a replacement for `Wiki/Index.md`** — Index is the hand-maintained catalog of every page; Dashboard is a live, narrower "what needs attention right now" view assembled from active modules' own declared contributions.

## Core operations

These run in every vault regardless of active modules. Modules may append extra steps to any of these (documented in the module's block) or add entirely new operations of their own.

### Operation: help \<optional: module name\>

1. If run before `init-vault` (no tailored `2b-instructions.md` exists yet), show the full "Help — choosing and using modules" section above as the module menu, plus `## Recipes` as the faster, named-combination starting point. `Operation: help <recipe name>` shows just that recipe's module set and rationale, same lookup pattern as step 3 below for an individual module.
2. If run in an initialized vault, show only the active module(s)' guidance from that section plus a quick reference of the operations currently available (core + active modules). That quick reference always includes `Operation: check-for-updates` (download a newer `2b-init.md` release), `Operation: update-vault` (check for and pull in changes from a newer `2b-init.md`), `Operation: add-use-case` (activate a module not yet in this vault), `Operation: dashboard` (build/refresh `Dashboard.md`), `Operation: plan-day`/`Operation: close-day` (daily ritual bookends), `Operation: plan-project`/`Operation: new-board` (`Projects/` is core — see `## Projects (core)`), and `Operation: archive`/`Operation: restore`/`Operation: delete`, regardless of which modules are active; it includes `Operation: config` too whenever a `## Vault config` section exists.
3. If a specific module name is given, show just that module's entry plus its full block from the Module Library (folders, operations, boundaries) regardless of whether it's currently active — useful for evaluating whether to add it later.
4. **Tooling reminder:** if no browser-automation tool driving a real, authenticated browser (e.g. a Chrome-extension-based tool) is currently available, mention plainly that installing/enabling one makes video-source ingestion meaningfully more reliable than a sandboxed browser tool alone — see `Operation: ingest`'s video-URL fallback for why. Surface this once per session at most (e.g. the first time `help` runs, or the first time a video ingest is attempted), not on every single ingest.

### Operation: config \<optional: key\> \<optional: new value\>

Reviews or updates the vault's `## Vault config` section (see Vault config above). Only present/relevant in a vault where that section exists (i.e. at least one Research-requiring flavor is active).

1. **No arguments:** display every current setting (e.g. `citation-rigor`), the tier/value in effect, and which active module(s) it was resolved from (e.g. "standard — max of Competitive Intelligence (standard) and Product Discovery/Decision-Making (standard)").
2. **`<key> <value>`:** validate the value against that key's allowed set (`citation-rigor` must be `strict`/`standard`/`light`). If the requested value is *looser* than what the active flavors would currently resolve to, warn plainly that this lets a stricter flavor's claims go under-enforced — but still apply it once the user confirms; never silently block a deliberate override.
3. Update `## Vault config` with the new value and append the change (old value, new value, reason if given) to `Wiki/Log.md`.
4. `Operation: add-use-case` calls into this same logic when a newly activated flavor would change the resolved value — proposing the recomputed tier as a normal confirm-before-apply step, the same as any other change that operation makes, rather than a separate silent recalculation. If the current value was a manual override (not what the active flavors would compute), say so explicitly and ask whether to keep the override or recompute.

### Operation: dashboard

Builds or refreshes `Dashboard.md` (see Dashboard above). Safe to run any time — assembling is idempotent, always reflecting current state rather than accumulating stale content.

1. If `Dashboard.md` doesn't exist yet, ask before creating it (same as any new top-level page) — this operation never runs unprompted.
2. Gather the core widgets (total `Wiki/Concepts/` count, recent `Wiki/Log.md` activity, Resurfaced items, needs attention) — always included.
3. For each currently active module/flavor, check its Module Library block for a `**Dashboard contribution:**` line. Skip modules that don't declare one — that's expected, not an error.
4. Render each included widget as a Bases/Dataview query embed where the module's contribution spec supports it (the default); fall back to computed static content only where a widget genuinely can't be expressed as a live query.
5. Include a short orienting-context excerpt (echoing this vault's own Purpose/tone) and, if a terminal-style plugin is installed (check `.obsidian/community-plugins.json` the same way plugin-presence is checked elsewhere), a one-line note on how to open it alongside this page — Claude cannot install the plugin itself, only detect and point to it.
6. Write/overwrite `Dashboard.md` with the assembled result. Append to `Wiki/Log.md`.

### Operation: plan-day

A morning ritual: synthesize what's already live elsewhere into one short, readable plan — never a new data source of its own, never a board/status change.

1. Gather anything due today or overdue — same mechanism as `review`'s deadline sweep: `Projects/`'s Deadline hook (core, always present) plus any other active module's own declared one.
2. Surface today's Resurfaced items (see Dashboard above), if `Dashboard.md` exists.
3. Present the combined result as a short ordered list. Does not move any card, check any box, or write anything back to vault content — read-only synthesis with respect to Projects/Wiki data.
4. Record this run's date/time in `Routines/Daily Ritual.md`'s `plan-day-last-run` field (create the page, seeded with both fields empty, on first-ever run of either this operation or `close-day`). This is bookkeeping about the ritual itself, not vault content — it doesn't relax step 3's read-only guarantee.

### Operation: close-day

An evening ritual, paired with `plan-day`: log what happened, let anything unfinished simply remain visible for tomorrow rather than requiring an explicit "carry it over" step.

1. Ask what got done today, or read it from Tasks-plugin done-dates (`✅ YYYY-MM-DD`) if that plugin and dated checklist items are in use — never infer completion silently.
2. Append a one-line summary to `Wiki/Log.md`.
3. Anything still open or overdue needs no explicit rollover — the same live queries `plan-day` and the Dashboard's needs-attention widget use will simply keep showing it tomorrow. Never mark anything done without the user confirming it actually happened, per core Boundaries.
4. Record this run's date/time in `Routines/Daily Ritual.md`'s `close-day-last-run` field (same file `plan-day` uses; create it if this is the first-ever run of either operation).

### Operation: ingest \<url or file\>

1. If a URL, fetch it and save the full text to `Raw/R - <Title>.md` with a `source-url` field. If a module defines a source subtype (e.g. Content Production's external creator videos), use that module's file location and naming instead.
   - **Video URLs specifically:** a plain fetch only returns page metadata (title, channel, description snippet) — captions are loaded by JavaScript, not present in the static page a simple fetch sees. Try, in order:
     - (a) A metadata-only fetch (e.g. the platform's oEmbed endpoint) to confirm title/creator before anything else.
     - (b) If a browser-automation tool is available, open the video and attempt to reveal its transcript/caption panel. **Known failure mode, confirmed on YouTube:** some platforms silently defeat automated transcript retrieval even when captions genuinely exist — the panel opens, a tab highlights, a direct fetch of the caption endpoint can even return HTTP 200, but the actual payload comes back empty. This is a different failure than captions being disabled, and it has a fix: dispatch a genuine trusted click (a real mouse/keyboard automation action) rather than a scripted DOM `.click()` — the platform can tell the difference (`event.isTrusted`) and silently defeats the latter while allowing the former. Prefer clicking via an accessibility-tree element reference over raw pixel coordinates where possible, since coordinate positions can drift between page states and a blind click risks landing on the wrong element (including navigating away entirely). If a sandboxed/limited browser-automation tool keeps failing even with a trusted click, and a tool that drives the user's own real, authenticated browser is available (e.g. a Chrome-extension-based tool, sometimes called "Claude in Chrome" or similar), try that next — a genuine logged-in session can succeed where a fully sandboxed one won't. **If no such real-browser tool is available at all, say so plainly and note that installing/enabling one would make video ingestion meaningfully more reliable going forward** — don't silently settle for oEmbed-plus-paste every time without mentioning the option exists.
     - (c) If both fail, ask the user to paste the transcript directly. Never fabricate transcript content to fill the gap.
2. If already in `Raw/` or `Inbox/`, start there.
   - For an unusually rich or ambiguous source, it's fine to ask the user what to emphasize, how granular to be, or what the ingest is really for before processing — the same judgment call `init-vault`'s interview makes once per vault, just applied per-source when a source actually warrants it. Not required for routine ingests.
3. Write `Wiki/Summaries/S - <Title>.md` with key claims, numbers, quotes, and why this matters to the vault's purpose.
4. Ripple the source through every Entity and Concept page it touches. A good source usually updates 5-15 pages.
   - **Contradiction check:** for each touched page, compare the new claim against what's already there before writing — see `## Contradiction handling` for the full classification (corroborating / granularity refinement / contradictory) and what to do for each case.
5. Create missing Entity and Concept pages as needed. Apply any module-specific source-handling convention here.
   - **Archived pages:** never link to a page in `Archived/`. If a new page's name would match an archived page's, give the new page a unique name (e.g. add a date), so a later `Operation: restore` doesn't collide.
6. Add backlinks and citations to the summary page. Tag it per the taxonomy above.
7. If the source affects an in-progress Output, Project, or piece of Content (whichever modules are active), note it on the relevant page or propose a new one. Do not move any board/pipeline card without asking.
8. Update `Wiki/Index.md`.
9. Append to `Wiki/Log.md` with date, operation, source title, and pages touched.

### Operation: check-watchlist \<playlist name | "all"\>

Watches YouTube playlists for new videos and ingests them automatically. This is the one place `ingest` runs without asking first — being added to `Routines/Watchlists.md` **is** the user's upfront authorization for that specific playlist, which is a narrower and more deliberate act than the blanket web content `digest` touches and never auto-ingests.

1. Read `Routines/Watchlists.md`; operate on the named playlist, or every `status: active` row if "all".
2. For each playlist, get its current video list: prefer browser automation to open the playlist page and read off video titles/links — this is a different, generally easier ask than reading a single video's transcript panel (no hidden panel to open, just a rendered list), but still isn't guaranteed in every environment. If it fails, log the failure in that row's Notes, leave `status` as-is, and move on to other playlists rather than blocking the whole run.
3. For each video found, determine if it's new by matching **video ID** (not raw URL string — `youtu.be/X`, `youtube.com/watch?v=X`, and a URL with extra query params all refer to the same video) against every `Raw/` page's `source-url`. Skip anything already present.
4. For each new video, run `Operation: ingest` — with one change to its video-URL fallback order, since a scheduled run has no one to ask: if oEmbed metadata succeeds but transcript retrieval fails (browser automation unavailable or unreliable, captions disabled), **do not wait for a paste.** Save the `Raw/`/`Summary` pages from metadata alone, set `status: needs-transcript` in their frontmatter, and add a card linking the page to `Projects/Board.md`'s Idea column so it surfaces for the user to paste the transcript later. Nothing is silently lost or silently skipped. (This unattended fallback applies only to scheduled/unattended runs — if the user triggers `check-watchlist` interactively in a live session, the normal `ingest` fallback, including asking them to paste, still applies.)
5. Update the playlist's row in `Routines/Watchlists.md`: `last-checked` date and a one-line run summary (e.g. "3 new, 1 needs-transcript").
6. Append to `Wiki/Log.md`.

**Without a live scheduled task:** cadence still matters even with no real automation behind it — enforce it as a session-start reminder instead. The first time in a session that Claude does substantive work in this vault, check every `active` playlist's `last-checked` against its `cadence`. If today is past the next-due date, say so plainly before getting into whatever else was asked, and offer to run `check-watchlist` right then. This is a standing instruction Claude follows because it's read here, not a technical hook — but it means a watchlist never silently goes stale just because no one remembered to check it.

`Routines/Watchlists.md` format — one consolidated file, not one page per playlist (a deliberate exception to `Routines/`'s usual one-page-per-routine convention, made because a table of watched playlists is easier to scan and maintain as a single list):

```
---
type: routine
tags: [routine, watchlist]
status: active
---

# Watchlists

| Playlist | URL | Cadence | Status | Last checked | Notes |
|---|---|---|---|---|---|
| <name> | <playlist URL> | daily / weekly / etc. | active / paused | <date> | |
```

If Content Production is active, videos ingested from a watchlist use that module's `External Sources/` naming (`EXT - <Creator> - <Title>.md`) instead of plain `Raw/`, per `ingest` step 1's existing module-subtype rule.

### Operation: query \<question\>

1. Read `Wiki/Index.md` first.
2. Open only the relevant pages.
3. Answer from the wiki with citations.
4. Clearly separate what the wiki knows from what Claude adds from general knowledge.
5. If the synthesis is genuinely valuable — not a quick lookup, an actual synthesis across multiple pages — save it as a new `Wiki/Concepts/` page by default, and say plainly that it was saved. Skip saving only if the user says not to, or if it's a thin one-off answer not worth keeping. Defaulting to save-and-tell exists specifically so a good answer can't quietly disappear once the chat ends — "offer and wait" was tried and lost real answers.
6. Append the query to `Wiki/Log.md`.

### Operation: lint

Health-check the wiki:

- Contradictions and stale claims.
- Orphan pages (no inbound links).
- Broken backlinks and orphaned references — a page can have working inbound links elsewhere and still contain an outbound link to something that no longer exists.
- Wikilink targets containing a `/` — almost always the folder-path mistake described in Conventions above, not a legitimate page name. Flag every instance directly; it's a distinct, mechanically-detectable pattern worth its own fast check rather than relying on the general broken-link scan to happen to catch it.
- Duplicate page names: two notes, `.base` or `.canvas` files with the same filename in different folders, or an alias matching another page's name or alias. Skip `_Template.md` files. Report each with the links it makes ambiguous. Renaming is confirmed with the user, never automatic, and updates every link in the same pass.
- Raw-file ingestion coverage: a source saved into `Raw/` but never actually worked into the wiki (caught by cross-checking `Raw/` against `Wiki/Log.md`'s ingest entries).
- Stale articles: no update in 90+ days and no longer clearly relevant — flag for review, don't auto-archive. Archiving is done deliberately, with confirmation, through `Operation: archive`.
- Archived content: skip everything inside `Archived/`. Links on live pages marked `*(archived)*` or converted to `(deleted …)` text aren't broken links, and neither are links in append-only pages such as `Wiki/Log.md`. Flag any live page whose name matches an archived page's.
- Entities or concepts mentioned 3+ times with no page.
- Pages missing a `#type/*` or `#status/*` tag.
- Summaries missing from `Wiki/Index.md`.
- Outputs claims lacking citations.
- Entity-referencing frontmatter fields (`author`, `creator`, `company`, etc.) stored as plain text instead of wikilinks.
- Concepts or Entities pages containing speculative language that belongs in `Wiki/Arguments/` instead.
- Module-specific checks appended by each active module (e.g. board-card-vs-status-field consistency, sponsor deadlines vs. attention dashboard).

Report findings. Fix mechanical issues directly. Ask before rewriting major pages. Suggest new article/source candidates the audit surfaces, rather than only reporting problems.

**Automating this:** rather than re-running `lint` manually each time, it's worth packaging it as an installable Claude Skill plus a scheduled task (see `Routines/`) so it runs unattended on a cadence (e.g. monthly) and reports back automatically.

### Operation: review

Generic replacement for a periodic (daily/weekly/ad hoc) review — cadence is whatever the user runs it at.

1. Deadline sweep: pull in `Projects/`'s Deadline hook (core, always present — see `## Projects (core)`) plus any other active module's own `**Deadline hook:**` line (e.g. Personal CRM's) — that's the actual mechanism, not "any module-tracked due date" left to infer. Anything due within 7 days gets flagged at the top of the response and listed in `Inbox/Attention.md` (overwritten each sweep — it's a dashboard, not a log). Ecosystem renewals are core, not module-specific, and are always included regardless.
2. Summarize activity since the last review: pages created/updated, module-specific pipeline movement.
3. Check for stagnant items: Outputs/projects/routines with no update in 30+ days, flagged.
4. Review `Ecosystem.md`: upcoming renewals, cost changes, unused tools or credentials to revoke.
5. Check `Routines/` for broken or stale routines.
6. If the review period produced a clear new finding worth acting on, update the relevant `Outputs/` page, citing receipts.
7. Append to `Wiki/Log.md`.

### Operation: digest

1. Search the web for the most significant news in `< DIGEST TOPICS — filled in by init-vault from the interview >` from the last 24 hours (or since the last digest, whichever is longer).
2. Write `Inbox/Digest <DATE>.md` with 5-8 items, each with a one-line summary and likely wikilinks.
3. Flag items with high topic velocity (multiple independent sources covering the same thing in a short window) as candidates worth a closer look.
4. Add a card linking the new digest file to `Projects/Board.md`'s Idea column (see core Conventions) so it's visible in the follow-up tracker, not just discoverable by browsing `Inbox/`.
5. Run the deadline sweep (step 1 of `review`) as part of this operation.
6. Do not auto-ingest. The user chooses what enters the wiki.

### Operation: draft \<Outputs page\> \<topic(s)\>

The "harvest" step — stitching cultivated Arguments/Concepts claims into a first-pass deliverable, the way atomic claims act as jigsaw pieces for a manuscript.

1. Gather the atomic claims already captured across the relevant `Wiki/Concepts/` and `Wiki/Arguments/` pages for the given topic(s).
2. **If the target Outputs page falls under a flavor module that declares an `**Output template:**`** (see Module Library — e.g. Academic Paper's paper/thesis skeleton, Competitive Intelligence's comparison-matrix skeleton, Product Discovery/Decision-Making's decision-memo skeleton), fill that specific template's shape rather than a generic page. Otherwise stitch into a plain first-draft page.
3. Stitch the gathered claims into the draft using embeds (`![[Note]]`) or inline text, preserving every claim's existing citation — nothing gets re-derived or re-stated without its link.
4. Flag gaps explicitly: any point the draft needs that isn't yet backed by a Concepts claim is listed as "needs a source," never invented to fill the gap.
5. This produces a first pass for the user to edit, not a final deliverable — it does not get treated as approved or published on its own.

### Operation: find-open-questions [scope] [focus]

A manually-invoked, vault-internal scan of already-ingested material for open questions, ambiguity, and conflicting information — broader than core `## Contradiction handling` (literal same-fact conflicts only, automatic at ingest time) and distinct from `Operation: digest` (external/web-facing; this stays vault-internal). Checks existing `Wiki/Arguments/` (and any in-scope `#status/contradiction-open` items) before raising anything new, so repeat runs don't create duplicates, and reports what's still open from before alongside anything newly found. Every finding cites its source — `Wiki/Arguments/` is where the questions themselves get to be speculative, but their existence must trace back to something actually present (or absent) in the scoped material, never manufactured.

**`scope`** (optional) — explicit page/file name(s), an existing tag, and/or a date cutoff (combinable). Kept simple by design — no hub-page/backlink-following scope. If omitted, propose a default (recently-touched Raw/Wiki activity) and confirm before proceeding — never silently scan the whole vault.

**`focus`** (optional) — a short steering instruction narrowing what kind of questions to look for on this run (e.g. "legal concerns and company liability" on one pass, "day-to-day operations and the first 90 days" on the next, over the same material). Without one, look broadly. Worth re-running with a different `focus` over the same material, and worth noting explicitly when a since-answered question suggests a new one.

1. Resolve `scope`; confirm before defaulting to "recent activity."
2. Build a working list of already-open items from `Wiki/Arguments/` (plus in-scope `#status/contradiction-open` items) — split still-open vs. already-resolved.
3. Read the scoped material for unanswered questions, underspecified claims, and informal inconsistencies (not formal contradictions) — `focus` prioritizes, doesn't exclude; note anything else genuinely notable as out-of-focus.
4. Dedup every candidate against the working list — link/extend an existing `Wiki/Arguments/` page rather than duplicating; genuinely new findings get their own page with a dual-link citation to the source it came from.
5. Report the full result (new / extended / reconfirmed-still-open / out-of-focus-but-notable) before finishing — nothing written silently.
6. Append a dated entry to `Wiki/Log.md` recording what was scoped, what was found/extended/reconfirmed, and any `focus` used — this *is* the "tracked as a dated task" record; no separate task-tracking page type needed.

### Operation: plan-project \<board\> \<topic or Projects page\>

Search the wiki for related prior work, define milestones and dependencies, seed a cheat-sheet of verified facts to work from, move the project to "In Progress" on the named board. `<board>` is only required to disambiguate when more than one board is active — with only one board active, omit it (see the board-confirmation Boundary below for what happens when it's omitted anyway). If `<board>` names a board that doesn't exist yet, this operation never creates one silently — confirm with the user whether to run `Operation: new-board` first or use an existing board instead.

### Operation: new-board \<topic\>

Creates `Projects/Board-<topic>.md` (cloned frontmatter/columns from the default board), the matching `Projects/Board-<topic>/` folder, and writes that board's row to `Projects/Directory.md` (creating the manifest itself, with the default board's row, if it doesn't exist yet). **Reserved name:** `<topic>` cannot be `Tasks` — that would produce `Board-Tasks.md` and reuse the default board's own `Board-Tasks/` folder, a genuine path collision, not just an awkward name. Reject it and ask for a different topic name.

### Operation: archive \<topic | page\>

Clears a finished topic out of the live vault, to cut clutter and keep old research out of the agent's context. Every page created for the topic moves into `Archived/<slug>-<YYYY-MM-DD>/` (see `## Core vault map`). Nothing is deleted: `Operation: restore` brings the topic back, and `Operation: delete` removes it for good. A single page works the same way, as a topic of one. `<slug>` is the topic name in kebab-case.

1. **Find the members.** A page belongs to the topic if it was created for it. Propose members from links first, `created` dates second, and `Wiki/Log.md` as a last resort. System and common pages are never members, even though they link to the topic: `Wiki/Index.md`, `Wiki/Log.md`, board files, `Projects/Directory.md`, `Bibliography.md`, `Dashboard.md`, `Ecosystem.md`, and any page other topics use. A page created for this topic but since linked from a live page outside it is shared and stays. Only links from live pages count, so once every topic using a shared page has been archived, the last archive includes it. An active module's `**Archive behavior:**` line may exclude pages or add rules.
2. **Preview, then confirm.** Show:
   - the members, grouped by folder, with `Raw/` files called out
   - the shared pages that stay, and how many links on each will be marked
   - the `Wiki/Index.md` lines, board cards and `Bibliography.md` entries to be removed
   - warnings about open work, such as an open contradiction, a board card in progress, or a module's own open items. These are for context: the user decides whether to go ahead.
   - how to undo it (`Operation: restore`)

   Nothing moves until the user confirms. The user may add or drop members before confirming.
3. **Move the members** into `Archived/<slug>-<date>/`, each keeping its original folder path inside it (e.g. `Archived/<slug>-<date>/Wiki/Concepts/<page>.md`). Files are moved, never edited. `Raw/` files move unchanged.
4. **Mark links on retained pages:** each link to a member becomes `[[Page]] *(archived)*`. Append-only pages (`Wiki/Log.md`, and any a module declares) are left as they are.
5. **Remove live references:** the members' `Wiki/Index.md` lines, the topic's board card lines, and its `Bibliography.md` entries. A card's task page moves with the other members; the card itself is a line of text in the board file, so it's cut from there.
6. **Write the restore index**, `Archived/<slug>-<date>/Archive Index - <slug>-<date>.md`: the reason for archiving, each member's original path, the removed Index lines, Bibliography entries and board cards (text and column), and the pages that got `*(archived)*` markers.
7. Append to `Wiki/Log.md`: the topic, date, reason, and number of pages. Once the archive is deleted, this is the only trace left.

### Operation: restore \<archive\>

Also `Operation: unarchive`. Reverses `Operation: archive` for one archive folder.

1. **Preview, then confirm:** what moves back, which markers are removed, and which Index lines, board cards and Bibliography entries return. If a live page now has the same name as an archived one, stop and ask how to resolve it (rename one of them, or leave that file archived).
2. Move each file back to its original path. Remove the `*(archived)*` markers. Put back the Index lines, Bibliography entries and board cards (in their recorded columns) from the restore index. Remove the emptied archive folder and its restore index.
3. **Re-link automatically:** re-run `Operation: ingest`'s linking steps (4–6) for the restored pages against the current wiki, including the contradiction check. This adds the links that pages created since the archive would have gotten, and flags newer sources that conflict with the restored claims.
4. Append to `Wiki/Log.md`.

### Operation: delete \<archive\> [files]

Permanently removes an archive, or only the named files inside it. Works only inside `Archived/`: nothing in the live vault is deleted by this operation. Runs only when the user asks for it, never offered as part of `archive`.

1. **Preview:** every file to be removed; every marked link that will be converted; and every claim on a live page whose only citation is a file being deleted. State plainly that without version control (e.g. git) or a sync service's file history, deleted files can't be recovered.
2. **Explicit confirmation**, separate from any earlier archive confirmation.
3. **Claims left without a source:** the user decides each one (keep, remove, or reword). Anything left undecided is marked `unverified (deleted YYYY-MM-DD)`.
4. Delete the files. Convert each marked link to plain text: `Page (deleted YYYY-MM-DD)`. Deleting a whole archive removes its folder and restore index; deleting only some files updates the restore index.
5. Append to `Wiki/Log.md`.

## Boundaries (core)

- Never modify `Raw/` files after creation. **The one exception is the archive operations:** `Operation: archive` may move a `Raw/` file into `Archived/` and `Operation: restore` may move it back, always with confirmation. A `Raw/` file's content is never changed, and it's deleted only from inside `Archived/` by `Operation: delete`, never directly from `Raw/`. Every other `Raw/` rule still applies.
- Never delete a wiki page without asking. Permanent deletion of archived content happens only through `Operation: delete`, with its own explicit confirmation.
- Deprecate and link forward instead of deleting.
- When two independently-sourced claims genuinely conflict (not just differ in specificity), never silently prefer one — flag it explicitly and resolve it through `## Contradiction handling`, never inline without a record.
- Never invent facts — except in `Wiki/Arguments/`, the one deliberate exception. Keep speculation contained there rather than letting it leak into Concepts, Entities, or Outputs.
- Mark anything unverified when it lacks a source.
- Never move a pipeline/board card to a real-world-confirmed state (Published, Filmed, Approved, Closed, etc.) without the user confirming it happened.
- **Board confirmation on task creation:** whenever a task or project page is created, of any size, and more than one `Projects/` board is active, the board must be confirmed before the file is written — if the requester names it explicitly, proceed without asking again; if they don't, resolve a best-guess board via `Projects/Directory.md` (matching the task's topic against each board's Description) and explicitly confirm that guess with the user rather than silently placing it. With only one board active, no prompt is needed.
- **WIP-limit discipline:** favor finishing in-progress work over starting new work on any `Projects/` board — an overloaded "In Progress" column is a signal to stop pulling in new items, not push through. "An invisible task is an unmanaged task" only helps if the visible board stays honest about how much is actually being worked on at once.
- Each active module may add its own boundaries (documented in its block below) — these are additive, never a relaxation of the core list.
- Never overwrite an existing file in a vault's `.obsidian/` folder, or any other file a standard file targets, without showing the change and getting the user's confirmation.
- `Operation: check-for-updates` replaces only the vault's `2b-init.md`, only after the user confirms, and never applies the new version itself. That's `update-vault`'s job.
- This file's own version lines (Generator version, Core version, each Module version, each standard File version) are only ever bumped as part of an actual edit to the section they cover, never standalone and never skipped when that section changes.
- `## Vault config` (citation-rigor and any future vault-level setting) is only ever changed through `Operation: config`, never hand-edited directly, and never silently recomputed by `add-use-case` without showing the proposed change first — same discipline as any other section a core operation writes to.

## Style

`< TONE — filled in by init-vault, e.g. "direct and lightly strategic," "neutral and encyclopedic," "warm and conversational." Default if unspecified: direct and practical. >`

Receipt-backed corrections: when new data contradicts something the user previously claimed, a wiki page, or an established rule, say so plainly and cite the receipts. Do not soften or bury contradictions to be agreeable.

**Suggested workspace layout (optional, human-side):** a split view with the source (PDF/video/article) open on one side and Concepts/Arguments notes stacked on the other makes it easy to cycle through claims while reading. This is a tip for the user's Obsidian window layout, not something Claude configures.

---

## Operation: init-vault

Run this once, in a fresh vault that has this file and nothing else load-bearing yet (an Obsidian default `Welcome.md` is fine to ignore or delete).

### 1. Interview

Ask the user, in plain language — do not dump this as a raw checklist:

1. **Purpose** — what is this vault for? (Free text. This fills the `< VAULT PURPOSE >` placeholder above.)
2. **Modules** — `Projects/` (work planning) is core and needs no selection. Two entry paths, either is fine:
   - **The user names a recipe directly** ("set this up for X") — see `## Recipes` above. Offer that recipe's module set (core members + any optional add-ons) for confirmation.
   - **The user describes their purpose in free text instead** (the answer to question 1 above, or more detail given here) — compare it against every named Recipe for a match or partial match, and lead with the closest one as a starting point rather than composing a module list from scratch each time; this is what keeps module recommendations consistent across separate `init-vault` runs given a similar stated purpose. If nothing in `## Recipes` is a reasonable match, fall back to walking the "Help — choosing and using modules" section module-by-module and building the list from there — forcing a poor-fit recipe is worse than admitting none fits. Recommend "General Wiki alone" (also named as a Recipe) if the purpose sounds broad/exploratory rather than tied to one of the other named shapes.
   - **Either way, the resulting module list is always shown to the user for confirmation/editing before Assemble runs** — a recipe (or a from-scratch list) is a starting point, never an unconfirmed final answer. Adding, dropping, or swapping a module from a recipe's default set is expected, not a deviation to talk the user out of.
   - **Base + flavor modules:** Research and Projections are **base modules** — never selected on their own, only pulled in automatically when a **flavor** that needs them is picked (see each flavor's `**Requires:**` line in the Module Library — every Research-requiring flavor needs Research; Due Diligence, Opportunity Cost/Options Comparison, and Product Discovery/Decision-Making also need Projections). Resolve requirements **transitively**: Projections itself requires Research, so follow each `**Requires:**` chain to the end. If the user picks a flavor, confirm every required base is being added too rather than silently including it — a user should see "Due Diligence (needs Research, which does X, and Projections, which does Y) — include all three?" not just end up with bases active unexplained.
   - **Explain the citation-rigor dial** briefly when any Research-requiring flavor is picked: each flavor declares its own tier (`strict`/`standard`/`light`, see Citation-rigor dial above), and if more than one such flavor is selected, the vault runs at the *strictest* of them — say plainly what that resolves to for this vault's specific selection before moving on, so the user isn't surprised by it later. This is a real point of onboarding complexity worth spelling out, not a footnote.
   - **Explain shared vs. per-flavor storage:** all Research-requiring flavors share one `Sources/`/`Bibliography.md` pool; each flavor's own deliverables live in their own path under `Outputs/` (e.g. `Outputs/Academic Paper/`, `Outputs/Competitive Intelligence/`) so stacking flavors never blends their outputs together.
3. **Naming** — does `Outputs/` need a more specific name for this vault (e.g. "Playbooks", "Findings", "Deliverables", "Recommendations")? Any other core folder the user wants renamed?
4. **Tone** — how should Claude sound when maintaining this vault? (Fills the Style placeholder.)
5. **Digest topics** — only if the user wants the `digest` operation: what subject(s) should it scan for?

### 2. Assemble

Using the user's answers:

1. Take the Core sections of this file (Philosophy through Boundaries and Style) and resolve every `< placeholder >`.
2. For each selected module, copy its entire block from the Module Library below into the new file: append its folders to the Vault Map, its frontmatter fields and tags to the taxonomy, its operations after the Core Operations, its boundaries after the Core Boundaries. If a selected module declares a `**Requires:**` base module (see Module Library), include that base module's own block too, even if the user didn't name it explicitly in the Interview — a flavor is never assembled without its required base. Resolve transitively (a base may itself require another base, e.g. Projections requires Research) and include each base block exactly once, however many selected modules require it.
2a. If any included module declares a citation-rigor tier, resolve the vault's single `citation-rigor` setting as the strictest tier among them (see Citation-rigor dial above) and write the `## Vault config` section into the new file with that resolved value. Skip this step entirely if no included module declares a tier.
3. Modules stay independent even when several are active together — a vault can stack any combination without one module's board, log, or tracker merging into or overwriting another's. The core `Projects/Board.md` and Content Production's `Content/Content Board.md` are deliberately separate files, with different names, for exactly this reason. If a genuine collision is ever found between two modules (the same file path, or the same page name in different folders, claimed by both), that's a defect in the Module Library itself — flag it rather than silently merging or picking one.
4. Write the assembled result as `2b-instructions.md` in the target vault root. **This file (`2b-init.md`) is not deleted or replaced** — it stays in the vault root as the versioned reference copy `Operation: update-vault` and `Operation: add-use-case` read against later, coexisting side by side with the tailored ruleset it produced from that point on. Add one line to the new `2b-instructions.md`'s Vault map or Conventions noting that `2b-init.md` is present for that purpose only and is never the active ruleset.
5. Add a `## Generator versions` section near the top of the new `2b-instructions.md`, stamped from this file's current version lines:
   ```
   ## Generator versions
   - 2b-init.md file version at last sync: <this file's current Generator version>
   - core: <this file's current Core version>
   - <module-slug>: <that module's current Module version>
   - <one line per selected module>
   - standard-file <file name>: <its current File version> (<written | adopted | replaced | declined>)
   - <one line per standard file>
   ```
   Module slugs are the kebab-case of the module name (e.g. `academic-paper`, `project-work-planning`) — a consistent naming rule, not tied to any particular tag convention.
6. Write (or overwrite) the agent-tool stub files at the vault root — `CLAUDE.md`, `AGENTS.md`, `.cursorrules`, `GEMINI.md` by default; ask the user if any other tool's convention filename should be added. `AGENTS.md` already covers OpenAI's Codex/ChatGPT agentic tooling — it adopted the same open convention, so no separate file is needed for it. Each stub is short and directive:

   ```
   # Stub — see `2b-instructions.md`

   This vault's actual operating ruleset lives in `2b-instructions.md`.
   Read that file in full before doing anything else here. This file
   exists only so agent tools that look for this filename by convention
   find something.
   ```

   **This step is idempotent and independently rerunnable** — safe to run on its own, any time, without redoing the Interview or the rest of Assemble: if `2b-instructions.md` is later renamed or moved, or this stub template's wording is improved in a future version of `2b-init.md`, rerunning just this step refreshes every stub file to match. Plaintext stubs are used deliberately over symlinks for portability — symlinks need Developer Mode/admin rights on Windows and often don't survive a zip-download or archive-extraction round trip.

### 3. Scaffold

Create the folders and starter files the assembled file now describes:

- `Wiki/Index.md`, `Wiki/Log.md` (both seeded with the section headers matching the active modules)
- `Ecosystem.md`
- `Projects/Board.md` (empty Kanban board, default columns) and `Projects/Directory.md` (seeded with the default board's own row)
- Every core and module folder referenced in the assembled Vault Map
- `_Template.md` stub pages for each page type now in play (Entity, Concept, Argument, Summary, Project — always in play, since `Projects/` is core — and any module-specific type: Contact, Sponsor, Source-with-credibility, etc.), each pre-filled with the right frontmatter fields (including `aliases:`) and a reminder to add `#type/*` and `#status/*` tags.
- The agent-tool stub files from Assemble step 6 above, if not already written.
- Every standard file (see `## Standard files (core)` above; currently `.obsidian/app.json` and `.obsidian/graph.json`): written as given where the target doesn't exist yet. Where it does exist, ask and confirm as that section describes, never overwriting silently.

### 4. Recommend plugins

1. Build one consolidated plugin list: the core recommendations above (Bases/Dataview/Kanban/Tasks/Tasks Calendar Wrapper) plus the "Recommended plugins" line from each selected module's block.
2. Check what's actually there: if `.obsidian/community-plugins.json`, `.obsidian/plugins/`, and `.obsidian/core-plugins.json` already exist (they usually won't in a genuinely fresh vault, but may if the user opened Obsidian before running this operation), read them and mark each recommended plugin present/enabled, present/disabled, or missing.
3. Report the consolidated list either way, with a one-line purpose per plugin and, for anything missing, the manual install path: Settings → Community plugins → Browse → search by name → Install → Enable. Note plainly that Claude cannot install or enable a plugin itself — that step is the user's, inside Obsidian.
4. Browser-extension tools (e.g. a web clipper) never appear in `.obsidian/` — recommend them, but don't claim to have verified their presence.
5. Missing plugins are never blocking: every module works in degraded form without them (a Kanban board can be a plain checklist; Bases/Dataview-less filtering just means manually maintained lists a while longer).

### 5. Recommend version control

1. Check whether the vault is already under git: a `.git` folder in the vault root, or `git rev-parse --is-inside-work-tree` succeeding there (the vault may sit inside a larger repo). If git itself isn't installed, say so and treat the vault as having no repo.
2. **If a repo exists,** say so in one line and move on.
3. **If not, recommend setting one up**, with the reason in plain terms: every change the agent makes to the vault becomes a reviewable, undoable history. Without it, an unwanted edit can only be undone from a sync service's file history, if there is one, and deleted files can't be recovered (see `Operation: delete`). Then:
   - Offer to set it up now. On a yes: run `git init` in the vault root, write a `.gitignore` if none exists (below), and make a first commit of the freshly scaffolded vault. Never do this without the user's yes.
   - If they'd rather do it themselves, give the same steps as commands: `git init`, create the `.gitignore`, `git add -A`, `git commit -m "Initial vault scaffold"`.
   - Connecting a remote (GitHub, GitLab, etc.) and pushing is always the user's step. Mention it as optional, and note that the Obsidian Git community plugin can commit and push on a schedule from inside Obsidian.
4. Suggested `.gitignore` — per-device Obsidian state that changes constantly and shouldn't be versioned:
   ```
   .obsidian/workspace.json
   .obsidian/workspace-mobile.json
   .trash/
   ```
   If a `.gitignore` already exists, suggest only the lines it's missing and add them on confirmation.
5. Not blocking: declining is fine, and every operation works without git.

### 6. Report

Summarize what was created and where, including that `2b-init.md` itself remains in the vault root as a reference copy for future `Operation: update-vault`/`Operation: add-use-case` runs, not something to delete, and whether the vault is under version control. Do not touch anything outside the target vault path.

---

## Operation: check-for-updates

Run this any time to see whether a newer `2b-init.md` has been released, download it into the vault root, and then offer `Operation: update-vault`. Releases are published at `https://github.com/michaelbarone/2b--second-brain/releases`, each tagged `v<Generator version>` (e.g. `v4.32`) with `2b-init.md` attached. This operation only ever replaces `2b-init.md`. Applying its changes to `2b-instructions.md` is `update-vault`'s job.

1. **Local versions.** Read the Generator version line of the `2b-init.md` in the vault root, and, if the vault is initialized, the file version recorded in `2b-instructions.md`'s `## Generator versions`. If there's no `2b-init.md` in the vault root, say so and treat the local version as none.
2. **Latest release.** Get the latest release's tag from `https://api.github.com/repos/michaelbarone/2b--second-brain/releases/latest` (the `tag_name` field) with whatever the agent has: a web-fetch tool, `gh release view -R michaelbarone/2b--second-brain`, or `curl`. The repo is public, so no login is needed. If it can't be reached, say so, give the releases link for a manual download, and stop.
3. **Compare** the release tag (without its `v`) against the local `2b-init.md` version, as MAJOR.MINOR numbers compared part by part, not as decimals: 4.10 is newer than 4.9.
   - **Same or older:** report "up to date" with both versions. If the local `2b-init.md` is newer than the version recorded in `## Generator versions`, it was downloaded but never applied, so offer `update-vault` (step 6). Otherwise stop.
   - **Newer:** continue.
4. **Ask before downloading.** Show the local and latest versions and the release link. Download the release's `2b-init.md` (`https://github.com/michaelbarone/2b--second-brain/releases/download/<tag>/2b-init.md`) to a temporary location, not the vault, and list the Generator-version changelog entries newer than the local version, so the user sees what changed. Ask whether to replace the vault's `2b-init.md` with it. On no, stop; nothing in the vault has changed.
5. **Replace.** On yes, check that the downloaded file's Generator version line matches the release tag. If it doesn't, or the file is empty or isn't this generator, stop without replacing anything. Otherwise overwrite `2b-init.md` in the vault root and nothing else. If the vault is under git, the old copy stays recoverable from history. If it isn't, say the old copy is being replaced for good before overwriting.
6. **Offer `update-vault`.** Ask whether to run `Operation: update-vault` now to apply the new version to this vault. On yes, continue directly into it. On no, remind the user that the new `2b-init.md` isn't in effect until `update-vault` runs. In a vault not yet initialized, offer `Operation: init-vault` instead.
7. Append to `Wiki/Log.md` (if it exists): the versions compared, and whether the file was replaced.

---

## Operation: update-vault

Run this any time to pull changes from a newer `2b-init.md` into an already-initialized vault's `2b-instructions.md`. Requires a vault that has already run `init-vault` (so a `## Generator versions` section exists) and a `2b-init.md` present in the vault root — if the copy in the vault is stale, get a fresher one first with `Operation: check-for-updates`, which downloads the latest release and then offers this operation (or the user drops a fresher one in over it by hand).

1. Read `2b-instructions.md`'s `## Generator versions` section. If it's missing (the vault predates this section, or its `2b-instructions.md` was hand-authored rather than produced by `init-vault`), stop and tell the user this operation only applies to a vault actually built by `init-vault`.
2. Compare the recorded file version against `2b-init.md`'s current Generator version at the top of this file. **If they match, report "up to date" and stop here** — this is the cheap gate that avoids scanning anything else when nothing changed.
3. If they differ, compare recorded vs. current version for core, and for each module recorded as active in `## Generator versions` (never-activated modules are out of scope here — see `Operation: add-use-case` — except when an updated module newly requires one, step 5a). Skip, explicitly (list what was skipped, don't just go silent on it), any section whose version is unchanged.
4. For each section whose version changed: diff the vault's current block/content against what's now in `2b-init.md` (core sections, or the relevant Module Library entry), and present the change and why. **Always show this diff and require confirmation before applying it, even if the section shows signs of local hand-editing that no longer matches what `init-vault` originally generated** — never silently overwrite.
5. On confirmation, apply each approved section's new content and update that section's recorded version in `## Generator versions` to match.
5a. **Newly required modules:** if an updated module's `**Requires:**` line now names a module that isn't active in this vault (e.g. Due Diligence 4.0 now requires Projections), add it — resolved transitively, and confirmed with the user the same way `init-vault` confirms a required base, never silently — using `Operation: add-use-case` step 3's per-module logic (Assemble + Scaffold against the existing vault) and adding its line to `## Generator versions`. An updated module is never left referencing a base the vault doesn't have. If the user declines, say plainly which parts of the updated module won't work without it.
5b. **Migration notes:** if an updated module's block carries a `**Migration note:**` line for the version range being crossed, show it and ask the user how to handle the existing content it describes — apply what they choose, one decision at a time. Don't try to convert everything automatically or cover every edge case; when something is unclear, ask.
6. Once every changed section is resolved, update the recorded file version in `## Generator versions` to match `2b-init.md`'s current Generator version.
7. **Standard files** (including `.obsidian/app.json`, which older versions re-applied silently on every run): for each standard file whose File version differs from the one recorded in `## Generator versions`, or that has none recorded, ask whether the user wants to set it as this vault's default. Show what would change and confirm before overwriting anything, using the adopt / replace / skip choices in `## Standard files (core)`. Record the outcome in `## Generator versions`. A version the user already declined isn't offered again.
8. Append a summary to `Wiki/Log.md`.
9. **Recipe check, then prompt:** compare the now-active modules against `## Recipes`. For any recipe the vault matches or nearly matches, list its core members and add-ons that aren't active yet as suggestions (e.g. *"you're running Due Diligence — the Investment / Deal Due Diligence recipe also includes Meeting Transcript Ingestion"*). User-driven only: nothing is added unless the user picks it, and "none" is a fine answer. Then ask whether they want to add any of those, or look at other modules; on yes, continue directly into `Operation: add-use-case` with their picks.

## Operation: add-use-case

Run this any time — after `update-vault`'s prompt, or standalone — to activate one or more Module Library modules that aren't yet part of this vault.

1. Read `2b-instructions.md`'s `## Generator versions` section to see which modules are already active; list every Module Library entry in `2b-init.md` that isn't.
2. Walk the user through the "Help — choosing and using modules" entries for just those unbuilt modules (same plain-language approach as `init-vault`'s Interview step 2, including the base+flavor/rigor/shared-storage explanations that step now gives) and ask which to add. **Recipe check first:** if any already-active module is a core member of a `## Recipes` entry whose other core members aren't yet active, surface that as a suggestion before the general walkthrough — e.g. a vault with Due Diligence active but not Meeting Transcript Ingestion is a likely candidate for that recipe's other core member. A suggestion only, never auto-added. None being wanted right now is a valid answer — stop cleanly.
3. For each module picked: if it declares a `**Requires:**` base module not already active in this vault, add that base module too — resolved transitively, same as `init-vault`'s Assemble step 2 (e.g. adding Due Diligence to a vault with neither base active adds Research and Projections) — confirm this with the user the same way `init-vault` does, never silently. Then run the same per-module logic as `init-vault`'s Assemble step 2 (append its folders to the Vault map, its frontmatter/tags to the taxonomy, its operations after Core operations, its boundaries after core Boundaries) and Scaffold step 3 (create its folders and starter files) against the *existing* vault rather than a fresh one. Apply the same path-collision guard from Assemble step 3 — flag rather than silently merge or overwrite if a new module's file path collides with an already-active one.
3a. If any newly added module declares a citation-rigor tier, recompute the vault's resolved `citation-rigor` the same way Assemble step 2a does, across every now-active tier-declaring module (old and new). If this changes the vault's current value, route it through `Operation: config`'s confirm-before-apply step rather than writing `## Vault config` directly — same as any other value change to that section. If no `## Vault config` section exists yet (this is the vault's first Research-requiring flavor), create it.
4. Add a new line to `## Generator versions` for each newly active module, stamped with its current Module version from `2b-init.md`.
5. Re-run `init-vault` step 4 (Recommend plugins) against the now-updated module list, since the new module(s) may bring their own recommendations.
6. Report what was added and where.
7. Append to `Wiki/Log.md`.

---

## Module library

Reference material for `init-vault`. Each module is self-contained; folder and prefix names are chosen so no two modules collide, and every fixed page a module scaffolds has a name no other module or core page uses (see Conventions: page names are unique across the vault), so any combination can be stacked without one module's files overwriting or merging into another's.

**Base modules vs. flavor modules:** most modules stand alone. A few instead form a **base + flavor** group: a base module (currently Research and Projections) owns shared mechanics with no fixed citation rigor or output shape of its own, and **flavor** modules stack on top of it, each contributing an opinionated output template, a declared `citation-rigor` tier, and any flavor-specific conventions. A flavor's block carries two extra lines a standalone module doesn't:

- **`**Requires:**`** — the base module(s) it depends on. Never selected without its base — `init-vault`'s Interview and `Operation: add-use-case` both auto-include (with confirmation) any required base a chosen flavor needs. A base module may itself carry a `**Requires:**` line (Projections requires Research); requirements resolve transitively.
- **`**Declared citation-rigor:**`** — its own tier (`strict`/`standard`/`light`); see Citation-rigor dial above for what each tier means and how multiple active flavors' tiers resolve into one vault-wide setting.

**Any module (base, flavor, or standalone) may also carry a `**Dashboard contribution:**` line** — see Dashboard above. Fully optional and independent of the base/flavor distinction; most modules currently have none.

**Any module may carry an `**Archive behavior:**` line** — what `Operation: archive`, `restore` or `delete` must do differently for this module's content: pages that can't be archived, extra preview warnings, lists that must keep archived entries, or append-only pages that never get link markers. Consider it whenever a module is added or changed. A module with nothing special omits it.

**Any module may carry a `**Migration note:**` line** — which existing content an upgrade to this version affects (e.g. files produced by an older version of an operation) and how to carry it forward. `Operation: update-vault` step 5b shows it and asks the user; it's guidance for a conversation, not an automated conversion.

**A flavor that requires Projections carries a `**Projection profile:**` line** — what it adds to the Projections base's shared skeleton: where `build-projection` gathers assumptions from, extra line items or default phases, where open issues are routed, extra summary metrics, and where the workbook is written. Anything a profile doesn't specify falls back to the base's `generic` behavior.

### Module: General Wiki

**Module version: 1.0**

**Use case:** broad, general-purpose knowledge base — a "Wikipedia clone." No pipeline, just capture → summarize → cross-link → index.

- **Adds:** nothing beyond core. This is the floor every other module builds on.
- **Modeled on:** "Using Claude Code to Setup a Second Brain aka LLM Wiki" (Wes Roth / Natural 20, natural20.com) — the literal ancestor text this template descends from; also matches the "general use wikipedia clone" framing this module was originally scoped around.

### Module: Research

**Module version: 1.2**

**Base module — never selected on its own; pulled in automatically by any flavor that requires it (Academic Paper, Competitive Intelligence, Product Discovery / Decision-Making, Product Feasibility, Opportunity Cost / Options Comparison, Due Diligence, Investment Strategy).**

**Use case:** the shared sourcing/citation substrate for any flavor that needs to track where its claims come from — gather sources, rate/tag them, keep them citable. Owns no fixed citation-rigor level or output shape of its own; that's each flavor's own contribution (see Citation-rigor dial above).

- **Folders:** `Sources/` (if finer-grained than `Raw/` credibility tracking is wanted — otherwise credibility lives directly on `Raw/` source pages via frontmatter).
- **Frontmatter additions:** `credibility` (primary / secondary / tertiary, peer-reviewed y/n), `rating`, `intent` (why this source was pulled in — e.g. "background" vs. "for manuscript X"), `year`, `cited-by` (back-reference list, usually auto-derivable from links but explicit for citation-heavy vaults).
- **Tags:** `#type/citation` if `Sources/` is split out as its own kind.
- **New pages:** `Bibliography.md` — running reference list, shared across every active flavor (not duplicated per flavor), auto-updated whenever a source is ingested.
- **Operations:**
  - `Operation: track-citation <claim> <source>` — record which source backs which specific claim, for later audit of citation density on any Outputs page.
- **Dashboard contribution:** a simple counts widget — total ingested sources (`Raw/` + `Sources/` if split out), broken down by `credibility` tier if that frontmatter is populated consistently; `Bibliography.md` entry count. A Bases/Dataview count query, not anything requiring a new plugin.
- **Recommended plugins:** PDF++ (deep-link into PDF highlights/selections), a web clipper (importing external articles into `Raw/`), Bases/Dataview (reading lists sorted by `rating`/`intent`/`year`).

### Module: Projections

**Module version: 2.1**

**Requires:** Research

**Base module — never selected on its own; pulled in automatically by any flavor that declares a `**Projection profile:**` line (currently Due Diligence, Opportunity Cost / Options Comparison, Product Discovery / Decision-Making).** Requires Research itself, since every assumption cites where it came from.

**Use case:** a shared, period-based projection model — timeline phases, costs, and revenue laid out increment-by-increment over a set horizon — with its uncertainties surfaced as tracked issues and every update recorded as a revision. Covers the economic/viability question no flavor otherwise owns (Product Feasibility scopes Economic feasibility out; Opportunity Cost / Options Comparison compares options without modeling their numbers).

- **Folders:** `Projections/` — one page per projection, the source of truth for its parameters, assumptions, issues, and revision history. Frontmatter: `type: projection`, `subject` (wikilink to the page being projected), `profile` (`generic` or the declaring flavor's profile name), `preset` (optional), `period-start`, `increment` (`week` / `month` / `quarter` / `year` — **default `month`**), `horizon` (a duration — **default `12 months`**), `scenarios` (default `[low, base, high]`), `revision` (starts at 1), `status` (`draft` / `open-issues` / `current` / `superseded`), `open-issues`, `high-impact-issues`, `last-updated`, `workbook`, `board-card`. `Projections/Presets/` holds line-item presets (below).
- **Period convention:** one column per increment across the horizon (default 12 monthly columns). `period-start` defaults to the first day of the next full increment. A horizon that doesn't divide evenly gets a final partial column, flagged as partial. Horizon and increment can be changed later via `update-projection`, recorded as a revision.
- **Projection skeleton (shared by every profile):** timeline phases mapped onto increments (default `setup/pre-launch → ramp → steady state`), driving which costs and revenue apply when; cost buckets — one-time/startup (placed in the increment they occur), fixed recurring, variable per unit; revenue drivers — units × price, with a per-phase ramp; per-increment outputs — revenue, total costs, net, cumulative net; summary outputs per scenario — break-even point (units: fixed costs ÷ (price per unit − variable cost per unit)), break-even increment (first increment where cumulative net turns positive, or "not within horizon"), peak cash need (deepest cumulative negative), horizon-end cumulative net. Every assumption has a `base` value and optional `low`/`high`; one with no range carries `base` into all three scenarios and is marked "no range."
- **Presets (a second axis beside profiles):** a profile says *which flavor's context* (where assumptions come from, where issues and output go); a preset says *what kind of business or deal* — its standard line items, whichever flavor invokes it. Each preset is an editable `Projections/Presets/<Name>.md` page (`type: projection-preset`, `default-phases`, optional `default-horizon`) listing line items — ID, cost bucket or revenue driver, unit, description, where the figure typically comes from. `build-projection ... [preset]` pre-loads every line item; any the vault can't fill starts as a `missing` assumption with its own open issue. Copied in at build time — later preset edits affect only new projections. **Starter presets** scaffolded with this module (editable; add more by copying one):
  - **Franchise** — one-time: initial franchise fee, build-out/leasehold improvements, opening equipment and inventory, working-capital reserve, training/travel; fixed recurring: rent/occupancy, base labor, technology/software fees, insurance; variable: royalty (% of revenue), marketing/ad-fund contribution (% of revenue), cost of goods; revenue driver: revenue per unit per increment with a ramp to maturity; parameters: franchise term and renewal/transfer fees (checked against the horizon). Figures typically come from the franchisor's disclosure document and existing franchisees — ingesting the disclosure document as a Raw source turns them from `missing` into `sourced`.
  - **Product Launch** — one-time: development/build cost, launch marketing, tooling/setup; fixed recurring: staff, hosting/infrastructure, tools; variable: cost of goods or service per unit, customer acquisition cost; revenue drivers: price per unit, units or customers per increment with a launch ramp, churn/repeat rate where it applies.
- **Assumption confidence labels:** `sourced` (cites a vault page), `user-stated` (given directly by the user, dated), `estimated` (benchmark/comparable/derived — its basis stated next to it), `missing` (no supportable value; affected output lines marked incomplete, never filled with a guess).
- **Open issues:** each projection page carries an issues table with stable IDs (`P-001`, …), raised automatically by both operations and manually on request. Fields: `id`, `question` (what would need to be known to firm this up), `kind`, `affects`, `impact` (`high` / `medium` / `low` — estimated effect on the summary outputs), `status` (`open` / `answered` / `resolved` — an answer can exist while the concern stays live), `next-step` (`ask-user` / `search-web` / `ingest-document`), `answer` + citation. Kinds: `missing` (no supportable value); `weak` (thin support — estimated/user-stated with no document behind it, a single low-credibility source, or a stale one); `conflict` (two sources disagree — routed through core `## Contradiction handling`, the issue linking to that record); `sensitivity` (flexing the assumption low → high moves the break-even increment by more than one increment, or in/out of the horizon — raised even when `sourced`, so the numbers the projection hinges on get confirmed deliberately).
- **Vault-first, then close the gaps:** a projection is built only from material already in the vault (Raw sources, Summaries, Concepts, Entities, pages linked to `subject`, what the user has said) — never from a web search mid-build. Anything unsupported becomes an open issue with a `next-step`; closing gaps (asking the user, a web search, ingesting a document) happens afterwards, then the projection is re-run with `update-projection`.
- **Operations:**
  - `Operation: build-projection <subject> [profile] [preset] [horizon] [increment] [period-start]` — (1) resolve parameters, applying defaults and stating them back; if no `preset` is named and one plausibly fits, suggest it rather than silently applying it; (2) gather assumptions from existing vault material linked to `subject` (the profile says where; `generic` searches pages linking to `subject` and Raw sources tagged for it), pre-loading the preset's line items if chosen; (3) lay out the skeleton and label every assumption's confidence; (4) raise issues for every `missing`/`weak`/`conflict` assumption and run the sensitivity check; (5) compute the period grid and summary outputs per scenario; (6) write the `Projections/` page (revision 1) and the workbook; (7) report the summary outputs, the confidence tally, and open issues ranked by impact — framed as the specific questions whose answers would most change the projection.
  - `Operation: update-projection <projection> [new details or source]` — (0) if no new details are given, offer to work the open issues, highest impact first: `ask-user` issues are asked directly; `search-web` issues get a web search whose candidates go to an `Inbox/` shortlist (a checklist item on the projection's issues card, not a separate card) and are ingested only once the user confirms — never auto-ingested, same as core `digest`; `ingest-document` issues name the document to ask for; then continue with whatever came in; (1) take in the new information: a substantive new document goes through core `Operation: ingest` (or a module's meeting-ingest operation) first so its figures are citable; brief facts stated by the user are recorded as `user-stated` with today's date; (2) check every open issue against it and mark each `answered`, `resolved`, or still `open`, citing the source for any answer; (3) revise affected assumptions — the new value becomes current, the prior value stays in that assumption's history (core append-don't-overwrite), and a value conflicting with an existing `sourced` one goes through Contradiction handling rather than silently replacing it; (4) re-scan for issues the new information raises; (5) recompute the grid, summary, and workbook; (6) append a revision-log entry and bump `revision`/`last-updated`/`status`; (7) report issues closed, issues opened, and before → after deltas on the summary outputs.
- **Board hand-off (one card per projection):** when a projection has any open `impact: high` issue, `build-projection`/`update-projection` automatically creates one `Projects/Board.md` card — "Resolve open issues: <projection>" — in Planned, tagged `#status/waiting-on-answer`, with the open high-impact issues (and each one's `next-step`) as a checklist on its page, per the core two-tier hierarchy. `update-projection` keeps the checklist in sync; when none remain it removes the tag and asks whether to move the card to Done (never moved unconfirmed). **Skipped when the profile routes high-impact issues elsewhere** (Due Diligence), so no issue gets two cards. Board confirmation applies as usual when more than one board is active.
- **Revision log:** every `update-projection` run appends a dated entry — revision number, what came in (linked), assumptions changed (old → new, with confidence-label changes), issues closed/opened, summary-output deltas. Prior revisions are never rewritten; a projection replaced wholesale is marked `status: superseded` with a link forward.
- **Projection profile (extension point):** a flavor requiring this base declares a `**Projection profile:**` line specifying any of: where assumptions are gathered from, extra line items or default phases, issue routing, extra summary metrics, workbook location. Unspecified parts fall back to `generic`.
- **Output:** the `Projections/` page (summary, parameters, assumptions table, period grid, open/resolved issues, revision log) plus a real, editable `.xlsx` workbook with live formulas — assumptions sheet (each cell's source note naming its citation and confidence label), period-grid sheet, summary sheet per scenario. Written to `Outputs/Projections/` under `generic`, or the declaring flavor's own Outputs path if its profile says so.
- **Page templates:** scaffolded with this module as `Projections/_Template.md` (projection page) and `Projections/Presets/_Template.md` (preset page); the two starter presets are written in the preset format from the line items listed under Presets above. `build-projection` fills the projection template; tables stay plain markdown so they render without any plugin.
  - **Projection page:**
    ```
    ---
    type: projection
    subject:
    profile: generic
    preset:
    period-start:
    increment: month
    horizon: 12 months
    scenarios: [low, base, high]
    revision: 1
    status: draft
    open-issues: 0
    high-impact-issues: 0
    last-updated:
    workbook:
    board-card:
    aliases: []
    tags: [type/projection, status/draft]
    ---

    # Projection — <subject>

    ## Summary
    | Scenario | Break-even point | Break-even increment | Peak cash need | Horizon-end cumulative net |
    |---|---|---|---|---|
    Confidence: <n> of <m> assumptions sourced · <k> high-impact issues open

    ## Parameters
    Period start, increment, horizon, scenarios, profile, preset — as in frontmatter, plus any stated reason for non-defaults.

    ## Timeline phases
    | Phase | Start increment | End increment | Notes |
    |---|---|---|---|

    ## Assumptions
    | ID | Line item | Bucket | Phase | Low | Base | High | Unit | Confidence | Source / basis |
    |---|---|---|---|---|---|---|---|---|---|

    ## Period grid (base scenario)
    | Line | Inc 1 | Inc 2 | … | Inc N |
    |---|---|---|---|---|

    ## Open issues
    | ID | Question | Kind | Affects | Impact | Next step | Status |
    |---|---|---|---|---|---|---|

    ## Resolved issues
    | ID | Question | Status | Answer | Citation |
    |---|---|---|---|---|

    ## Revision log
    - r1 — <date> — built from <sources>; <n> issues raised.
    ```
  - **Preset page:**
    ```
    ---
    type: projection-preset
    default-phases: [setup, ramp, steady state]
    default-horizon: 12 months
    aliases: []
    tags: [type/projection-preset]
    ---

    # Preset — <Name>

    Use for: <kind of business or deal>

    ## Line items
    | ID | Line item | Bucket | Unit | Description | Typical source |
    |---|---|---|---|---|---|
    (Bucket: one-time / fixed / variable / revenue / parameter)

    ## Notes
    Where figures usually come from, and anything to check against the horizon.
    ```
- **Tags:** `#type/projection`, `#type/projection-preset`.
- **Boundaries addition:** never write a number without a basis — an `estimated` value states its basis, a value with no basis is `missing`, never guessed; every assumption not labeled `sourced` has a matching open issue (lint failure otherwise, not a style note); an issue is only marked `answered`/`resolved` with a cited answer; `update-projection` never silently overwrites — prior values and revisions stay visible, and every run appends a revision-log entry; the summary always shows the confidence tally (e.g. "9 of 14 assumptions sourced, 3 high-impact issues open") next to the outputs; `build-projection` never performs web searches — anything found on the web is used only after it's ingested (on confirmation) and cited; a projection's issues card and its high-impact issues never diverge.
- **Dashboard contribution:** a projections widget — each `Projections/` page with `status`, `revision`, `last-updated`, and `high-impact-issues`, sorted by high-impact issues descending. A Bases/Dataview query, no new plugin needed.
- **Tooling note:** the workbook depends on the agent tool having a spreadsheet-authoring capability. Without it, the projection page's markdown period grid is the full output; nothing else in this module needs that capability.
- **Recommended plugins:** Bases/Dataview (filter projections by `status`, `profile`, `preset`, `subject`, or open-issue counts); Kanban (already core, for the issues card).

### Module: Academic Paper

**Module version: 2.0**

**Requires:** Research

**Declared citation-rigor:** strict

**Use case:** an output that has to survive a citation audit — a paper, thesis, or grounded research deliverable. Extracted from the former "Research / Academic" module and narrowed to just this flavor's own discipline, now that shared sourcing mechanics live in the Research base module above.

- **Claim discipline — the defining rigor of this flavor:** Concepts pages are held to an atomic-sentence standard — one claim per sentence, and every sentence carries **two links**: one to the Source Note (network connectivity) and one pinpoint "in-link" straight to the exact highlight/location in the original material (PDF++ page/selection link, a block reference, or equivalent) so the claim can be double-checked in one click. This is the module's strict reading of the core "deep citation" convention, and the concrete behavior behind its `strict` citation-rigor declaration.
- **Summary format addition:** literature-review style — summaries note methodology and limitations, not just findings.
- **Output template:** paper/thesis-shaped skeleton (abstract, sections, references) that `Operation: draft` fills when targeting this flavor's Outputs path.
- **Boundaries addition:** an Outputs claim with no citation is treated as a lint failure, not just a style note; a Concepts claim with only one link (Source Note but no pinpoint in-link, or vice versa) is flagged the same way.
- **Independence:** deliverables live under their own `Outputs/Academic Paper/` path (naming may be adjusted per vault, same as the core `Outputs/` rename option), kept separate from any other active flavor's outputs.

### Module: Content Production

**Module version: 4.0**

**Use case:** a recurring content pipeline — video, writing, podcast, or other periodic output, potentially with external creators to track and sponsors to manage. (Generalized from a working YouTube-channel vault.)

- **Folders:**
  - `Content/` — one page per piece of content (frontmatter: `type: content`, `status`, `target-date`, `sponsor` if any).
  - `Sponsors/` — one page per sponsor: contacts, deliverables, required assets, due dates, approval status, and a structured **contract terms** section covering seven named categories (deliverables, deadlines/revisions, payment terms, content ownership/usage rights, exclusivity, confidentiality, termination grounds).
  - `Armory/` — tools and technical builds supporting production (not content ideas themselves — link the two if a build becomes the subject of a piece).
  - `External Sources/` — immutable pages for other creators'/competitors' content, one per item, named `EXT - <Creator> - <Title>.md`. Treated like `Raw/` (never edited after creation).
- **New pages:** `Content/Content Board.md` — Kanban board, columns `Idea → On Deck → Research → Scripting/Drafting → Produced → Packaging → Published`. Named `Content Board`, not `Board`, so it never clashes with the core `Projects/Board.md` (see core Conventions: page names are unique across the vault).
- **Migration note (from 3.x):** the board used to be `Content/Board.md`, which has the same page name as the core `Projects/Board.md`, so a plain `[[Board]]` link could point at either. Rename it to `Content/Content Board.md`. Renaming inside Obsidian updates links automatically; otherwise update them in the same pass. Check each existing `[[Board]]` link and point it at the board it actually meant, asking the user where that isn't clear. If the vault already worked around the clash with an alias such as `Content Board`, keep it, since it now matches the filename.
- **Tags:** `#type/content`, `#type/sponsor`, `#type/creator`.
- **Entity convention:** the vault's own producer gets a self-node Entity page linking every piece of content, covered topics, and performance metrics. Other creators/competitors get their own Entity pages, linked from their items in `External Sources/`.
- **Concepts convention:** track topic velocity (multiple sources hitting the same topic in a short window) and format velocity (which formats the algorithm/market currently favors) on creator/topic pages, marked unverified unless backed by concrete metrics.
- **Operations:**
  - `Operation: new-topic <topic>` — continuity check against the self-node's covered-topics list, create an Idea card, assess whether the wiki has enough supporting sources (flag `under-resourced` if not), offer a sourcing shortlist rather than auto-ingesting, and check the idea against upcoming key dates (holidays, industry events, campaigns).
  - `Operation: prep-piece <topic or Content page>` — continuity check, suggested packaging/hooks, topic velocity read, a cheat sheet of verified facts, a key-dates check, move the piece to Research/Scripting.
  - `Operation: update-sponsor <sponsor>` — update requirements/due dates/assets/approval status, sync linked Content pages and the board, run the deadline sweep.
  - `Operation: analyze-performance` — ingest performance data, compare against past output and comparable output from other creators, update the relevant Outputs playbook with receipt-backed rules.
- **Boundaries addition:** never mark a sponsor deliverable approved without the user's confirmation; never move a card to Produced or Published without the user confirming it happened in reality; never let the Idea/On Deck columns grow past what production capacity can realistically absorb — an overloaded early-stage column gets flagged as a signal to stop pulling in new ideas, not silently accumulated.
- **Note:** a "beat" is this module's application of the core deep-citation convention — the pinpoint location is a timestamp instead of a PDF highlight or block reference. Any lint check for missing pinpoint citations applies to beats too.
- **Independence:** `Content/Content Board.md` is this module's own file, kept separate from the core `Projects/Board.md` and from any other active module's board. Stacking modules never merges or overwrites either — each use case keeps its own file, always.
- **Archive behavior:** `Operation: archive` never trims the self-node's covered-topics list. An archived topic's entry stays, with its link marked `*(archived)*`, and becomes plain text with a `(deleted <date>)` note if the archive is later deleted, so `new-topic` and `prep-piece` continuity checks still see that the topic was covered. `External Sources/` pages follow the same archive rules as `Raw/`: moved and deleted only through the archive operations, never edited.
- **Recommended plugins:** Kanban (for `Content/Content Board.md`), Bases/Dataview (filter Content by status/target-date), a web clipper (importing `External Sources/` items).

### Module: Team / Org Knowledge Base

**Module version: 3.0**

**Use case:** internal documentation, onboarding, and institutional decision history for a team or organization.

- **Folders:** `People/` — one page per team member/role (distinct from `Wiki/Entities/`, which stays for external companies/products/people).
- **New pages:** `Decisions.md` — append-only decision log: what was decided, when, by whom, and why (the rationale, not just the outcome).
- **Document authority tiers:** every page in this module carries an `authority` field ranking it: `source-of-truth` (leadership-approved, effectively read-only — e.g. `Decisions.md` entries), `core` (technical/foundational, stable), `working` (sprint notes, meeting notes, subject to revision), or `archive` (outdated, retained not deleted). When two documents conflict, the higher tier wins by default — Claude flags the conflict explicitly rather than silently picking one, but the tier gives a starting precedence rule multi-person teams need and a single-curator vault doesn't.
- **Tags:** `#type/person`, `#type/decision`.
- **Onboarding pattern:** a page per role/team, split into three phases — **learning/integration** (standing context, links into the relevant Concepts and People pages rather than duplicating information), **contribution/collaboration**, and **autonomy/growth**. Buddy/mentor support is named as a distinct mechanism from manager check-ins.
- **Content-origin convention:** any note copied from an AI conversation gets a `contains-AI` tag; a folder-routing automation (e.g. Auto Note Mover) files tagged notes into a dedicated subfolder, separating human-authored from agent-generated content by mechanism rather than by habit alone.
- **SOP review cadence:** a `core`-tier page gets reviewed annually by default; `source-of-truth` pages less often; `working` pages have no formal cadence; `archive` pages are never reviewed. Each review bumps a lightweight version — minor edits increment the decimal (v1.1), structural changes increment the whole number (v2.0) — noted directly on the page.
- **Ecosystem tie-in:** tooling/process inventory that's org-wide (not personal) lives in the core `Ecosystem.md`, tagged by owning team if useful.
- **Operations:**
  - `Operation: check-workflow-currency <SOP page> <new source>` — compares newly-ingested material against the named SOP page and reports exactly what needs to change.
- **Boundaries addition:** decisions are never edited after logging — corrections get a new dated entry that supersedes the old one, linked forward.
- **Archive behavior:** archiving a page with `authority: source-of-truth` gets an extra warning in the `Operation: archive` preview, naming the page and its tier, before the user confirms. `Decisions.md` is append-only: it's never archived and never given link markers, so its links to archived or deleted pages stay as they are, like `Wiki/Log.md`'s.
- **Recommended plugins:** Bases/Dataview (query `Decisions.md` and `People/` by `authority`, owning team, or status), Auto Note Mover (routes `contains-AI`-tagged notes automatically), a web clipper (importing externally-sourced material into `Raw/`).

### Module: Personal CRM / Relationships

**Module version: 2.0**

**Use case:** tracking people and the relationship/interaction history with them — this makes the people layer primary rather than supporting.

- **Folders:** `Contacts/` — one page per person (frontmatter: `type: contact`, `relationship`, `last-contact`, `cadence`, `strength`, `bridges` [optional — which of the user's own other social/professional clusters this contact connects to]).
- **Relationship strength:** a qualitative `strength` field (cold / warm / hot / close) tracks connection health over time, distinct from and complementary to the plain `cadence` field — `cadence` says how often to check in, `strength` says how the relationship is actually doing.
- **Bridging convention:** `bridges` is a second, independent prioritization axis alongside `strength` — a manually-set field, not a computed network score. A contact connecting two otherwise-separate parts of the user's own network can be worth prioritizing even at low `strength`, since bridging position (not tie warmth) predicts access to genuinely new information.
- **Relevance-triggered follow-up convention:** alongside cadence-based reminders, a follow-up prompt gets added to a contact's existing follow-up list whenever something specifically relevant to them comes up — a lightweight capture habit, not a computed schedule.
- **Tags:** `#type/contact`.
- **Per-contact structure (default):** an interaction log (dated, append-only) and a follow-up list on each contact page.
- **Alternative for high-volume or multi-person tracking:** if a vault's interaction volume is heavy, or interactions frequently involve multiple contacts at once (e.g. group meetings), switch to a separate `Interactions/` folder — one atomic note per interaction event (frontmatter: `date`, `people` as wikilinks to every contact involved, `method`, `summary`, `follow-up`) instead of an inline log section. This trades simplicity (one file per contact, works with zero tooling) for queryability (Bases/Dataview can filter across all interactions directly, and one interaction can link multiple contacts instead of being duplicated or arbitrarily owned by one). Needs an extra sync step to keep each contact's `last-contact` updated from the newest linked Interaction note. Pick one variant per vault at setup time — don't mix.
- **Operations:**
  - `Operation: log-interaction <contact> <notes>` — append a dated entry to the contact's interaction log (default variant) or create a new `Interactions/` note linking the relevant contacts (alternative variant), update `last-contact`, and surface any follow-up the user flags.
- **Deadline hook:** contacts overdue against their stated `cadence` surface in both the core `review` operation's deadline sweep and `Operation: plan-day`'s morning synthesis, alongside due dates.
- **Boundaries addition:** interaction log entries are never edited after the fact, only appended to — same append-only rationale as `Wiki/Log.md`.
- **Recommended plugins:** Templater (quick-capture interaction logging via command palette, per source), Bases/Dataview (follow-up/cadence dashboard: overdue contacts, upcoming birthdays).

### Module: Competitive Intelligence

**Module version: 4.0**

**Requires:** Research

**Declared citation-rigor:** standard

**Use case:** tracking how entities (competitors, products, markets) change over time. Narrowed from the former "Product / Competitive Intelligence" module back to its original scope — discovery, ideation, and prioritization work now belongs to the separate Product Discovery / Decision-Making flavor below instead.

- **Frontmatter additions on Entities:** `last-updated-by-source` (which summary most recently touched this entity's facts) so the entity page reads as a living, versioned record rather than a static one; `company: [[CompanyName]]` (and similar) as a wikilink value per the core property-links convention, so the company page becomes an auto-aggregating hub of every product/comparison that names it.
- **Entity convention:** uses the core append-don't-overwrite Entity-timeline convention (`## Conventions (core)`) for how facts update over time, and `## Contradiction handling` for what happens when an update actually conflicts rather than extends. This flavor's own addition is the `last-updated-by-source`/`company:` frontmatter above, which turns that timeline into a queryable, auto-aggregating record rather than just a chronological note.
- **New pages:** feature-comparison matrix pages (one per comparison the user wants to track, e.g. "Product A vs Product B") living in this flavor's own Outputs path.
- **Tags:** `#type/comparison`.
- **Concepts convention:** a market-move timeline tracks significant competitor moves chronologically, each entry citing its source summary. Each entry (and each comparison-matrix row) carries a **Fact / Impact / Response** structure — Fact (what happened), Impact (what it means for the vault's own position), Response (what to do about it, if anything).
- **Operations:**
  - `Operation: research-competitor <entity> <objective>` — states the objective first, sweeps public/secondary sources broadly, then flags which claims need primary/human verification rather than treating everything as equally in need of expensive verification. Runs on demand, not a fixed schedule — a set of named trigger signals (contract expirations, new technology installs, product removals, hiring shifts, funding events, review-trend shifts, a competitor mention surfacing elsewhere) are cues worth running it early rather than waiting for the next scheduled pass.
- **Output template:** comparison-matrix / market-move-timeline skeleton that `Operation: draft` fills when targeting this flavor's Outputs path.
- **Boundaries addition:** never state a competitive claim without a citation (this flavor's own reading of its `standard` citation-rigor declaration — no mandatory pinpoint in-link, but a citation is never optional); explicitly mark speculation about competitor intent as `unverified`.
- **Independence:** deliverables live under their own `Outputs/Competitive Intelligence/` path, kept separate from any other active flavor's outputs.
- **Recommended plugins:** Bases/Dataview (build the feature-comparison matrices and filter Entities by `last-updated-by-source` or `company`), a web clipper (importing competitor pages/announcements into `Raw/`).

### Module: Product Discovery / Decision-Making

**Module version: 3.0**

**Requires:** Research, Projections

**Declared citation-rigor:** standard

**Use case:** deciding what to build or pursue — opportunity mapping, needs identification, and evidence-informed prioritization. Split out from the former "Product / Competitive Intelligence" module's accumulated discovery/ideation material, which was solving a different problem than tracking competitor timelines (that stays with the Competitive Intelligence flavor above).

- **Folders:** `Opportunities/` — one page per outcome being pursued, structured as an Opportunity Solution Tree (outcome → opportunity → solution → assumption-test), with a `market-size` field (a rough SOM — Serviceable Obtainable Market — estimate, not TAM) populated during mapping, before scoring.
- **New pages:** decision-memo pages living in this flavor's own Outputs path.
- **Tags:** `#type/opportunity`, `#type/decision-memo`.
- **Discovery convention:** operates continuously, as a parallel always-on track rather than a one-time exercise — opportunities get added and reprioritized as evidence accumulates, not just when a decision deadline hits.
- **Needs-identification convention:** populate opportunities with real switching evidence (why a customer chose, switched to, or switched away from something) rather than assumptions.
- **Operations:**
  - `Operation: score-idea <opportunity or solution>` — score using RICE (reach × impact × confidence ÷ effort) when reach data exists, or ICE (impact × confidence ÷ effort) as a simpler fallback when it doesn't. Records the score and its inputs on the relevant page, cites the evidence behind each input, and surfaces the opportunity's `market-size` (SOM) estimate alongside the score as qualifying context — not multiplied into the RICE/ICE formula itself.
- **Projection profile (`launch`):** `Operation: build-projection <opportunity or solution> launch` projects a product launch, `subject` being the `Opportunities/` page. Default phases become `setup → launch → ramp → steady state`. **SOM cap:** projected unit volume in any increment is checked against the opportunity's `market-size` (SOM); exceeding it raises a `weak` issue rather than being silently clipped, and a missing `market-size` raises a `missing` issue. `score-idea`'s Effort input may cite the projection's setup-phase cost and duration (with its `revision`). Once a decision memo recommends pursuing, the projection's phases are offered as seed milestones to core `Operation: plan-project` — offered, never auto-created. Workbooks are written under `Outputs/Product Discovery/`.
- **Output template:** decision-memo skeleton (opportunity, evidence, options considered, recommendation, score) that `Operation: draft` fills when targeting this flavor's Outputs path.
- **Boundaries addition:** never state a prioritization score without recording the evidence behind its inputs; a scored opportunity with no supporting evidence is treated as a lint failure, not just a style note.
- **Independence:** deliverables live under their own `Outputs/Product Discovery/` path, kept separate from any other active flavor's outputs.
- **Dashboard contribution:** a counts widget — opportunities currently under assessment (`Opportunities/` page count, ideally split by stage: unscored / scored / decided), plus most recent `score-idea` results. A Bases/Dataview query, no new plugin needed.
- **Recommended plugins:** Bases/Dataview (filter/sort opportunities and decision memos by score, status, or evidence count).

### Module: Product Feasibility

**Module version: 3.0**

**Requires:** Research

**Declared citation-rigor:** standard

**Use case:** assessing whether a proposed product or initiative is actually buildable — narrowed to Technical and Operational feasibility (Scheduling as a secondary check), assessed via time-boxed, initiative-linked spikes, as distinct from whether it's worth building (Product Discovery / Decision-Making) or how it compares to the alternatives (Opportunity Cost / Options Comparison).

- **Folders:** `Feasibility/` — one page per spike/investigation (frontmatter: `type: feasibility-spike`, `initiative` [optional wikilink to the Project/Opportunity page this spike serves], `question`, `dimension` [technical / operational / scheduling], `status`, `time-boxed-hours`, `verdict`).
- **New pages:** feasibility-memo pages living in this flavor's own Outputs path.
- **Tags:** `#type/feasibility-spike`, `#type/feasibility-memo`.
- **Dimension convention:** a narrowed TELOS — **Technical** (available technology, team skills, integration — including PIECES's Control and Information categories as sub-checks: security/oversight requirements, data quality/availability) and **Operational** (can existing organizational systems/processes support it — including PIECES's Efficiency and Service categories as sub-checks: workflow fit, stakeholder impact) as the assessed core, **Scheduling** as a secondary check. Economic and Legal feasibility stay explicitly out of scope (Economic belongs to Opportunity Cost / Options Comparison's territory; Legal isn't covered by any current flavor). PIECES folds in as sub-checks within TELOS's existing dimensions rather than as its own parallel framework.
- **Operations:**
  - `Operation: run-spike <question> [initiative]` — a time-boxed investigation scoped to one narrow, answerable question against one dimension. The question should specify whether it's PoC-level ("can this be built at all") or Prototype-level ("how would it work"). If `initiative` names a page with prior spikes already linked to it, surfaces those spikes' questions and verdicts as context before starting the new investigation, rather than starting blind. Creates a `Feasibility/` page recording the question, dimension, initiative link (if any), time box, and outcome: a verdict (feasible / not feasible / feasible with caveats) or an explicit "invest more time" decision — never a silent non-answer.
- **Initiative linking convention:** spikes stay independent by default — running one doesn't create or update anything beyond its own page. Tagging multiple spikes for the same initiative with a shared `initiative` link is what makes them chainable: each new spike gets prior spikes' context per the behavior above, and `Operation: draft`, when targeting a feasibility memo for that initiative, gathers every `Feasibility/` page sharing that link into one memo — the same generic gather-and-flag-gaps mechanism `draft` already uses for every other flavor, now able to group by `initiative` as well as by topic tag.
- **Output template:** feasibility-memo skeleton (question, dimensions assessed, linked spike results per dimension, overall verdict, named risks) that `Operation: draft` fills when targeting this flavor's Outputs path.
- **Boundaries addition:** never declare a dimension feasible without at least one completed spike backing it — a verdict with no linked `Feasibility/` page is treated as a lint failure, not just a style note; a spike that hits its time box without a clear verdict must record "invest more time" explicitly.
- **Independence:** deliverables live under their own `Outputs/Product Feasibility/` path, kept separate from any other active flavor's outputs.
- **Dashboard contribution:** a counts widget — open vs. resolved spikes (`Feasibility/` page count by `status`), most recent verdicts. A Bases/Dataview query, no new plugin needed.
- **Recommended plugins:** Bases/Dataview (filter spikes by dimension, status, verdict, or `initiative`).

### Module: Opportunity Cost / Options Comparison

**Module version: 4.1**

**Requires:** Research, Projections

**Declared citation-rigor:** standard

**Use case:** comparing mutually exclusive options against what pursuing each one forecloses, via a musts/wants filter, weighted matrix, and foreclosed-cost analysis, gated by an explicit defer-or-decide check — distinct from Product Discovery / Decision-Making's single-opportunity scoring, this flavor is about the tradeoff between options rather than whether any one of them clears a bar on its own.

- **Folders:** `Options/` — one page per comparison decision (frontmatter: `type: options-comparison`, `status`, `musts`, `criteria`, `weights`, `defer-gate-result`, `target-date` [required when `defer-gate-result: defer` — when to revisit the decision]).
- **New pages:** options-comparison memo pages living in this flavor's own Outputs path.
- **Tags:** `#type/options-comparison`.
- **Comparison sequence convention:**
  1. **Defer gate** — before scoring anything, ask explicitly whether this decision must be made now, irrevocably, or can be deferred/partially committed/scaled into. If deferring is viable and cheaper than committing now, the recommendation is to defer and the rest of the sequence doesn't run.
  2. **Musts/wants filter** (Kepner-Tregoe) — any option failing a hard "must" is eliminated outright, before scoring begins.
  3. **Weighted matrix** (Pugh method) — surviving options scored against weighted criteria relative to a reference baseline.
  4. **Foreclosed-cost column** — for each non-chosen option, the explicit and implicit cost of not picking it, recorded alongside the matrix.
  5. **Regret check** — a **required** final step: record an explicit answer to "which option will I regret least" on the winning option, mirroring Kepner-Tregoe's own risk-analysis stage. The comparison is not complete without it.
- **Operations:**
  - `Operation: compare-options <option set>` — runs the full sequence above (defer gate → musts/wants filter → weighted matrix → foreclosed-cost column → regret check) and records it on an `Options/` page.
- **Projection profile (`options`):** after the musts/wants filter, `compare-options` offers — not forces, since not every comparison is financial — to run `Operation: build-projection` once per surviving option (`subject` = that option, linked from the `Options/` page). **Like-for-like enforced:** every option's projection in one comparison uses identical `period-start`, `increment`, `horizon`, `scenarios`, and `preset` (e.g. every franchise option from the Franchise preset); a mismatch is refused and flagged, never silently normalized, and changing one option's period parameters later prompts the same change across the rest. Projection summary outputs (break-even increment, peak cash need, horizon-end cumulative net) become available as economic criteria in the weighted matrix, and the foreclosed-cost column is quantified with the non-chosen option's horizon-end cumulative net and break-even timing relative to the chosen one. Open `impact: high` projection issues whose answers could change the ranking are stated as a defer-gate input, and listed in the memo as caveats on the recommendation. Workbooks are written under `Outputs/Opportunity Cost Options Comparison/`.
- **Output template:** options-comparison memo skeleton (decision framed, defer-gate result, options considered, musts/wants filter results, weighted matrix, foreclosed-cost analysis, regret-check answer, recommendation) that `Operation: draft` fills when targeting this flavor's Outputs path.
- **Deadline hook:** when the defer gate's result is "defer," the `Options/` page's `target-date` feeds into both core `Operation: review`'s deadline sweep and `Operation: plan-day`'s morning synthesis — same underlying mechanism every other flavor's Deadline hook uses.
- **Boundaries addition:** `Operation: compare-options` is not complete without a recorded regret-check answer — a comparison page missing one is treated as a lint failure, not just a style note; a comparison page with `defer-gate-result: defer` and no `target-date` set is treated as a lint failure the same way; never state a foreclosed-cost claim without naming which specific alternative it's relative to; an economic criterion or foreclosed-cost figure taken from a projection cites that projection's `revision`, so a later update visibly invalidates a stale score.
- **Independence:** deliverables live under their own `Outputs/Opportunity Cost Options Comparison/` path, kept separate from any other active flavor's outputs.
- **Recommended plugins:** Bases/Dataview (filter comparisons by status, criteria, defer-gate result, or upcoming `target-date`).

### Module: Meeting Transcript Ingestion

**Module version: 2.0**

**Use case:** capturing full meeting transcripts from external recording/note tools (Krisp, Granola, Google Meet/Gemini, etc.) as a source type, then extracting participant links, decisions, and action items so a transcript's content reaches the rest of the wiki rather than sitting as one large unlinked file.

- **Folders:** no new top-level folder — meeting transcripts land in the existing `Raw/` as `R - <Meeting title or topic> (<date>).md`, distinguished by a third `source-type: meeting-transcript` value alongside `article`/`video`.
- **Frontmatter additions (meeting-transcript source-type only):** `meeting-date`, `platform` (`krisp` / `granola` / `google-meet` / `other`), `participants` (wikilinks to `Contacts/`/`People/` where they exist — bare names otherwise, never auto-created), `duration` (optional).
- **Ingestion tier:** manual export/paste only — export the transcript from the source tool and paste/drop it in; never fabricate missing content, same rule as the video-ingest fallback. Tool-specific pull (a tool's API/MCP) and push (a tool's webhook) integrations are named as future tiers, not built — a push tier specifically needs its own human-review gate before it could ever write to `Raw/` unattended. At least one common tool class (summary-only meeting-notes products with no transcript API) has no automation path at all by design — manual paste is a permanent tier there, not a temporary gap.
- **Participant-linking convention:** speaker names are resolved against `Contacts/` (Personal CRM) or `People/` (Team/Org KB), whichever is active, and wikilinked; unresolved names stay bare mentions — never used to silently create a new page.
- **Decision/action-item extraction (confirm-then-place):** decisions become their own atomic claims, same jigsaw discipline as any source. Candidate action items are scanned separately; if found, the full list is presented for the user to confirm/drop, then each confirmed item is placed as its own `Projects/` Idea-column card or grouped into one per-meeting follow-up card, per the user's choice. Nothing auto-creates. Without `Projects/` active, confirmed items just list on the transcript's Summary page.
- **Cross-module hand-off, not ownership:** updates whichever of Personal CRM, Team/Org KB, or Project Work Planning is active with what the transcript surfaced; does nothing further if none are active.
- **Tags:** none beyond `#type/source`, differentiated by `source-type: meeting-transcript`.
- **Operations:** `Operation: ingest-meeting <transcript file|paste>` — meeting-specific entry into core `ingest`, replacing its step 1 with: input → ask about redaction, then write to `Raw/` → Summary → participant-linking → decision/action-item extraction → index updates.
- **Boundaries addition:** ask about redaction/exclusion before writing anything — a raw transcript can carry sensitive content the article/video pipeline never has to consider. No automated pull/push tier, if ever built, writes to `Raw/` without an equivalent human review gate.
- **Recommended plugins:** none required beyond core; Bases/Dataview once volume justifies querying by participant/platform/date.

### Module: Due Diligence

**Module version: 4.1**

**Requires:** Research, Projections

**Declared citation-rigor:** standard

**Use case:** ingesting due-diligence source material (financial documents, business plans, meeting transcripts, and other data-room content) as citable Raw sources, extracting and cross-referencing the claims within them, tracking open questions/red flags through to resolution, and projecting the opportunity's financials on the Projections base — verifying whether an opportunity's underlying facts are trustworthy, distinct from whether it's worth pursuing (Product Discovery / Decision-Making), buildable (Product Feasibility), or the best of the available options (Opportunity Cost / Options Comparison). Composes with the standalone Meeting Transcript Ingestion module for the meeting-transcript half of its inputs, if that module is also active — no duplicate ingestion path.

- **Folders:** `Diligence/` — one page per open item/question (frontmatter: `type: diligence-item`, `category` [financial / legal / operational / hr / technology / commercial / environmental / regulatory], `status` [open / answered / blocking / resolved], `severity` [informational / watch / elevated / critical], `owner`, `opportunity` [optional wikilink to the Project/Opportunity page this diligence effort serves — same convention as Product Feasibility's `initiative` field], `source-docs` [wikilinks to the Raw source(s) that raised or answer the item]).
- **Financial-document ingest convention:** Raw frontmatter for financial/business-plan source types gains `document-type` (financial-statement / business-plan / cap-table / pro-forma / other) and `period` (the reporting period the document covers), so figures stay comparable across documents and time — distinguished by frontmatter, not a separate folder, same convention `Raw/` already uses for `source-type`.
- **Spreadsheet ingest convention:** a CSV/XLSX source gets the same `Raw/` treatment as any other source (key figures extracted into frontmatter/prose per the convention above) plus the original file is kept in `Assets/`, extending the vault's existing convention for non-markdown evidence rather than inventing a new storage location. The Raw page links to its `Assets/` original so the full tabular data can be reopened later.
- **Financial model (cost estimates, break-even analysis):** one `Projections/` page (plus its `.xlsx` workbook) per `opportunity`, built on the Projections base's shared skeleton — period grid (monthly over 12 months by default), cost buckets, revenue drivers, scenarios, break-even point and increment, peak cash need, confidence labels, open-issues table. This module contributes only the profile below.
- **Projection profile (`due-diligence`):** `build-projection` gathers assumptions from every `Diligence/` item and financial-document/spreadsheet `Raw` source linked to `opportunity` (`document-type`/`period` let figures line up to the right increment). A seller-supplied `document-type: pro-forma` is loaded as a comparison line beside the model, not as its assumptions — a disagreement with a sourced figure from another document raises a `conflict` issue routed through core Contradiction handling. **Issue routing:** any projection issue rated `impact: high` is promoted to a `Diligence/` item via `raise-issue` (`category: financial`, linked both ways), inheriting severity tracking and, if `elevated`/`critical`, the auto-created Board card; resolving that item via `resolve-issue` marks the linked projection issue `answered`/`resolved` in the same pass and prompts an `update-projection` run. Workbook written under `Outputs/Due Diligence/`.
- **Migration note (from 3.x):** a vault that used the older `build-model` has `.xlsx` models under `Outputs/Due Diligence/` but no `Projections/` page. On the first `build-model` run for such an opportunity, ask the user whether to use the existing workbook as input; if yes, read its populated assumption cells into the new projection, keeping each cell's source note as that assumption's citation, and leave the old workbook in place. Anything unclear — ask the user rather than guessing; no attempt to auto-convert every workbook layout.
- **Cross-referencing convention:** no bespoke reconciliation mechanic — when a newly-ingested document's claim conflicts with one already recorded from an earlier document in the same diligence effort, it runs core `## Contradiction handling` as-is.
- **New pages:** diligence-memo pages living in this flavor's own Outputs path.
- **Tags:** `#type/diligence-item`, `#type/diligence-memo`.
- **Operations:**
  - `Operation: raise-issue <question> <category> [opportunity]` — creates a `Diligence/` page: records the question, `category`, an initial `severity` assessment, `owner`, `opportunity` link if given, `status: open`. If `opportunity` names a page with prior diligence items already linked to it, surfaces those items' status/severity as context first.
  - `Operation: resolve-issue <item> <answer>` — records the answer with a citation to the source document/claim that answers it, and moves `status` to `answered` (a documented answer now exists) or `resolved` (the underlying concern is fully closed) — the caller states which; never silently guessed.
  - `Operation: build-model <opportunity>` — shorthand kept for continuity: runs `Operation: build-projection <opportunity> due-diligence` on first use, and `Operation: update-projection` against that opportunity's existing `Projections/` page thereafter. All model behavior is the Projections base's, not redefined here.
- **Cross-module hand-off, not ownership:** a `Diligence/` item with `severity: elevated`/`critical`, or `status: blocking`, automatically gets a `Projects/Board.md` card — a deliberate departure from Meeting Transcript Ingestion's confirm-then-place default, since reaching high severity via `raise-issue`/`resolve-issue` is already a deliberate, sourced act, not unreviewed candidate text. The card states which `Diligence/` item raised it and why, and carries the matching `#status/blocked`/`#status/waiting-on-answer` tag from `Projects (core)` for highlighting. This module never owns the card afterward, only raises it.
- **Output template:** due-diligence memo / risk register skeleton (open items by category and severity, resolved items with their citations, outstanding blockers, overall read) that `Operation: draft` fills when targeting this flavor's Outputs path.
- **Boundaries addition:** a `severity: critical` item is never marked `resolved` without a cited answer — a lint failure, not a style note; `document-type`/`period` are required Raw frontmatter on any source ingested specifically for a diligence effort (an `opportunity` link present), optional otherwise; an auto-created Board card is kept in sync with its originating item's status/severity in the same pass as any change that affects it; the Projections base's no-fabricated-number and every-unsourced-assumption-has-an-issue boundaries apply in full; a promoted projection issue and its `Diligence/` item never diverge in status — whichever is updated, the other follows in the same pass.
- **Dashboard contribution:** a counts widget — open items by severity, most severe unresolved item surfaced by name. A Bases/Dataview query, no new plugin needed.
- **Independence:** deliverables (memos and `.xlsx` financial models alike) live under their own `Outputs/Due Diligence/` path, kept separate from any other active flavor's outputs.
- **Tooling note:** the workbook's spreadsheet-authoring dependency belongs to the Projections base — without it, the `Projections/` page's markdown period grid is the full model. Every `Diligence/` mechanic works with no such capability.
- **Recommended plugins:** Bases/Dataview (filter `Diligence/` items by category, status, severity, or `opportunity`).

### Module: Stand-up Comedy

**Module version: 5.0**

**Use case:** developing your own stand-up material, from idea → premise → branches → bit → (chunk) → set, with performance feedback flowing back into the bits. All joke content is the user's. Claude structures, links, times, checks, researches, gives feedback and suggests, but never writes into the user's wording.

- **Folders:**
  - `Inbox/`: raw ideas, as core quick captures. Frontmatter `type: idea`. Voice-memo transcripts land here too. No structure required: capture fast.
  - `Comedy/Premises/`: one page per premise (a topic plus an attitude, e.g. "X is weird/scary/stupid because…"). Frontmatter: `type: premise`, `status` (`exploring` / `developed` / `parked`), `from-idea` (link to the Inbox capture), `themes` (list). Holds the premise statement in the user's words and a `## Branches` section (see Branching).
  - `Comedy/Bits/`: one page per bit, the core working unit. Frontmatter: `type: bit`, `status` (see Bit lifecycle), `premise` (link), `themes`, `runtime` (estimated minutes, e.g. `1.5`), `current-version` (integer), `sets-up` (list of bits this plants something for), `callback-to` (list of bits this pays off), `derived-from` (link, when grown from a burned or retired bit), `derived-bits` (list, the reverse link), `prior-use` (`unchecked` / `clear` / `similar-premise` / `close-match`), `prior-use-checked` (date), `prior-use-version` (the `current-version` that check covered), `feedback-version` (the `current-version` last given craft feedback, empty if never), `research-checked` (date of the last topic research, empty if never), `last-performed` (date), `stage-count`, `recent-scores` (list, newest first, last 5), `burned-in` (link to its Release page) + `burned-date` (only when burned), `locked` (`true` only when burned).
  - `Comedy/Chunks/` (optional): a themed run of bits always performed together in a fixed order with fixed segues, used as a single unit in sets. Frontmatter: `type: chunk`, `bits` (ordered list), `runtime` (sum), `themes`. The body embeds each bit in order, with the chunk's own segue lines between them, so segues live in one place. Scaffolded from the start but not required: useful once there's 10+ minutes of material, and until then sets reference bits directly. **Using part of a chunk:** a set may use a whole chunk (embedded as one unit) or only some of its bits. When it uses only some, the set embeds those bits individually, and `build-set` flags that the chunk's segues and internal callbacks no longer apply, so they can be checked. The chunk page itself is unchanged.
  - `Comedy/Sets/`: one page per reusable set. Frontmatter: `type: set`, `target-length` (minutes), `context` (e.g. open mic, showcase, feature, headline), `status` (`draft` / `active` / `archived`). The body is an ordered list of embeds, `![[Bit - Name#Current]]`, so reading the set page gives the full script. Editing a bit updates every set that uses it, and set pages never hold their own copy of bit text.
  - `Comedy/Performances/`: one page per show. **Never edited after creation, same as `Raw/`.** The one exception is filling an empty `transcript` field once a transcript arrives later. Frontmatter: `type: performance`, `date`, `venue` (link to its Entity), `set` (link), `recording` (original link, optional), `transcript` (link to its Raw transcript, optional). The body snapshots the running order as performed, with each bit's version number at the time. Set pages keep changing, so the performance page is the only accurate record of what was actually done that night. It also holds one score per bit and the user's notes.
  - `Comedy/Releases/`: one page per public release of material, whether recorded or broadcast (a special, album, TV/streaming spot, podcast appearance, social clip, anything else). It's the evidence record behind any burn decision. Frontmatter: `type: release`, `kind` (free text, e.g. special / album / tv / podcast / clip), `release-date`, `platform`, `url` (original link), `transcript` (link to its Raw transcript, optional), `availability` (e.g. public / paywalled / taken down, as last checked, with the date), `bits-reviewed` (list), `bits-burned` (list). The body holds `## Evidence` (every link and source used, each with a one-line note on what it shows) and `## Burn decisions` (one entry per bit reviewed; see Burn review).
  - **Recording transcripts:** when a performance or release has a recording, it's transcribed where possible and saved as an immutable `Raw/` source (`R - <date> <venue or release> Transcript.md`, frontmatter `source-type: performance-recording` or `release-recording`, `source-url` set to the **original link**, always kept). How: if the recording is on a video platform, follow the vault's video-ingest transcript steps; if it's a local audio/video file, use a speech-to-text tool if one is available in the session; otherwise ask the user to paste a transcript or skip it. **Never fabricate or reconstruct transcript content.** If it can't be transcribed, only the original link is recorded.
  - Entities: venues, rooms, bookers, and other comics as ordinary Entity pages. If Personal CRM is also active, bookers and comics are CRM contacts instead.
- **New pages:** `Comedy/Comedy Board.md` is a Kanban board for early-stage material, with columns `Idea → Premise → Drafting → Workshopping`. `Comedy/Comedy Library.base` (Bases, or a Dataview table where Bases isn't available) covers stage-tested material, i.e. bits in `working` / `a-material` / `retired` / `burned`, sortable by status, runtime, themes, recent scores, last performed and prior-use verdict. **Board ↔ library hand-off:** a card follows its material from Idea (the Inbox capture) to Premise (the premise page). When a branch is chosen, that bit gets its own card in Drafting. A premise's card is archived once none of its branches is still `exploring`. A bit's card is archived when the bit reaches `working`, and from then on the library table shows it.
- **Migration note (from 4.x):** `Comedy/Board.md` and `Comedy/Library.base` are renamed to `Comedy/Comedy Board.md` and `Comedy/Comedy Library.base`. The old names clashed with the core `Projects/Board.md` and with other modules' library views. Rename both; renaming inside Obsidian updates links and embeds. Check each existing `[[Board]]` link and point it at the board it meant, asking the user where that isn't clear.
- **Tags:** `#type/idea`, `#type/premise`, `#type/bit`, `#type/chunk`, `#type/set`, `#type/performance`; `#status/burned` on burned bits (on top of the frontmatter `status`) so they stand out in graph and search.
- **Bit lifecycle:** `drafting → workshopping (tried on stage) → working → a-material`. Any status from `workshopping` onward can go to `retired` or `burned`.
  - **Retired:** set aside by choice (it stopped working, got outgrown, or no longer fits). It can come back at any time to `workshopping` or `working`, reworked or not, **unless it has since been burned.**
  - **Burned:** released publicly in a way that spends it for live sets. **There is no fixed list of release kinds that count.** Whether a special, a clip or a podcast appearance burns a bit depends on context: reach, whether it's still available, and how much of the bit was actually shown. So every potential burn goes through a Burn review (below), and **only the user decides.** A burned bit **cannot go back to retired or any active status.**
- **Burn review (burning is permanent, so the decision is evidence-backed):** triggered whenever a release is mentioned anywhere, whether in `log-set`, in conversation, or by the user directly. Claude never burns a bit on its own. The review:
  1. **Find or create the Release page** and record the original link.
  2. **Gather full context.** Transcribe the release where possible (see Recording transcripts). Search the web as needed for release date, platform, reach, availability and whether it's still publicly up. Record every source in `## Evidence` with a note on what it shows. If the context is still thin, say so and name what's missing rather than presenting a weak basis as solid.
  3. **Surface every potential match.** Offer all candidate bits, not just the obvious ones: any bit whose material appears in the release (found by comparing the transcript against each bit's `## Current` and version history, or from the user's list). Each candidate shows the extent of the match (whole bit / core punchline / only a tag / only the premise), the version that matches, and the evidence for it.
  4. **The user decides per bit:** `burned` or `not burned`, with a short justification in their own words. A partial match (e.g. only one tag was released) can be burned as-is, or handled by creating a derived bit first that carries the unreleased parts forward. The user picks which.
  5. **Record the decision** in the Release page's `## Burn decisions` and in a `## Burn record` section on each burned bit. Each record has the release link, the matched version, the extent of the match, the evidence links, the user's justification, and the decision date. A burn needs at least one evidence link. With none, it's recorded as `user-stated, no evidence link`, and the user is asked whether to proceed or wait for evidence.
  6. **Confirm before locking.** Restate that burning is permanent, then apply the lock.
- **Burned-material lock:** marking a bit burned freezes it as a record. It sets `locked: true`, `burned-in` (the Release page), `burned-date` and `#status/burned`, and adds a `> [!burned]` callout at the top of the page naming the release. From then on, Claude makes no edits to that page's `## Current`, `## Version history` or `## Burn record`, apart from appending to its `derived-bits` list. **New work grows from it as a new bit.** The premise and any parked branches are still usable, and only the released context and wording are spent. The new bit links back with `derived-from: [[Burned Bit]]`. Obsidian has no real file lock, so the lock is enforced by this module's operations and boundaries; the callout makes it visible when editing by hand.
- **Branching (on premise pages):** the `## Branches` section lists the directions a joke could go, A, B, C…. Each branch has a one-line description in the user's words and a status (`exploring` / `chosen` / `parked` / `dead`). A `chosen` branch becomes its own Bit page linked by `premise`, so one premise can produce several bits. `parked` branches stay on the page for later and are the first place to look for tags, callbacks, or new work growing from a burned bit. Claude's suggested branches go in a `> [!suggestion]` callout below the user's list. The user promotes the ones they want, in their own wording.
- **Bit versioning (one file per bit):** each bit page has `## Current` (the live version, in the user's words, with setup, punchline(s), tags, act-outs and segue notes) and `## Version history` (earlier versions, dated and numbered, newest first). A new version moves the old `## Current` into the history, fills a new `## Current`, and bumps `current-version`. The filename never changes, so embeds and links never break. Following core append-don't-overwrite, earlier versions are never rewritten or deleted.
- **Callbacks and ordering:** a bit declares `sets-up` (it plants something) and `callback-to` (it pays off something earlier). Segue notes (`segue-in` / `segue-out`) live in `## Current`. These links become ordering rules in `build-set`:
  1. A callback must come after the bit it refers to.
  2. If a set drops a setup bit, its callbacks are flagged as broken.
  3. A plant with no payoff in the set is flagged as a missed callback chance.
  4. A callback to a burned bit is flagged, because the audience may know the original.
  The same links answer "what could come before or after this bit" on any Bit page.
- **Performance scores:** one enum value per bit per performance, `killed | solid | soft | bombed`, recorded on the Performance page. No other metrics, such as laughs per minute. A bit's strength is a summary of its recent scores (e.g. "last 5: 3 killed, 2 solid") stored in `recent-scores`, never hand-entered or turned into a single number.
- **Craft feedback (on request, or at wrap-up):** structural notes on a bit, written in a `> [!feedback]` callout in the bit's `## Feedback` section and dated with the version reviewed. Never edited into the user's text.
  - **What it covers:** economy of the setup (anything the joke doesn't need), whether the punch word lands at the very end, clarity of the misdirection and of the assumption the audience has to make, room to grow (tag chances, act-out moments, callback links to other bits), and whether the bit earns its `runtime`.
  - **When:** only when the user asks for it, or when the user accepts it in the wrap-up offer (below). Never unprompted during drafting.
  - **Going stale:** feedback covers one version. It's marked outdated once `current-version` moves past `feedback-version`.
- **Topic research (context and perspective, not jokes):** outside research that helps the user sharpen, update or widen a bit. Findings go in the bit's (or premise's) `## Research notes` section, each note cited to its source link and dated. A substantial source the user wants kept can go through core `Operation: ingest`. Four types:
  - **Facts and specifics:** real details, numbers and recent developments on the topic that could make a bit sharper or more current.
  - **Shared experience:** how people commonly talk about or complain about the topic (forums, reviews, discussion threads), showing which angles are widely relatable and which are niche.
  - **Audience-reach check:** flags references in the bit that are regional, generational, dated or insider knowledge, with research showing how widely they're known. Each flag notes whether the reference may need a line of setup for a wider audience.
  - **Fact-check:** confirms the factual claims a bit relies on, reporting each as `confirmed`, `outdated` or `wrong`, with sources.
  - **When:** on request, or **offered when Claude spots a clear opening**, such as a factual claim in the bit, a reference that may be dated or niche, or a premise that's thin on specifics. Each opening is offered once, in one line, and never re-offered if declined. Accepted research can run in the background, like the prior-use check.
  - **Guardrails:** research **never produces joke text**. Claude may point out what the research suggests (e.g. "most complaints focus on X, not Y"), and the user writes the joke. **Other comedians' jokes on the topic are never shown or summarized.** If research turns one up, it's logged only as a lead for the prior-use check. Queries are paraphrased, the same rule as the prior-use check.
- **Prior-use check:** checks whether other comedians have done the same or a very similar joke, to avoid accidental copying. This is the only search that looks at other comedians' material.
  - **What it searches:** the web (special transcripts, clip titles and descriptions, reviews, joke databases), plus a local comparison against the user's own burned bits, so a new bit doesn't restate released material.
  - **Queries are paraphrased.** They use keywords for the premise and angle, **never the bit's full text**, so unreleased material isn't sent to a search service word for word.
  - **Overlap has two levels:** premise overlap (common and usually fine, since many comics have done "airline food") and angle/punchline overlap (the level that matters).
  - **Verdicts:** `clear` / `similar-premise` / `close-match`, logged in the bit's `## Prior-use checks` section with the date, the version checked, the queries used, the sources checked, and the specific close items with links. `close-match` means rewrite before stage time, and the user decides how.
  - **Search scope (v2.0):** general web search. Specific sources may be named later once testing shows what actually turns up matches.
  - **Built-in limit:** most stand-up is never transcribed online, so `clear` always means "nothing similar found in the sources checked," never "original." That wording is used every time.
  - **A check goes stale** when the bit's `current-version` moves past `prior-use-version`. Its verdict then reads as outdated, not current.
- **Wrap-up offer on context switch (prior-use check + craft feedback):** both are offered when work on a bit pauses, not while it's being written.
  - When the session moves off a bit whose draft changed in this session, Claude makes **one** offer covering whichever of the two is due. Moving off means going to another bit, a set, a premise, or anything else. A prior-use check is due when the bit has no current check (`prior-use: unchecked`, or `prior-use-version` older than `current-version`). Craft feedback is due when `feedback-version` is older than `current-version` or empty. Example: "Run a prior-use check and craft feedback on *Airport Security* while we start the next thing?" The user can accept both, either one, or neither.
  - **Timing:** never during active drafting and never on every prompt about the bit. Only at the switch, and only once per bit per switch. If the user declines, neither is offered again until the bit changes.
  - **Several pending bits:** when more than one bit is waiting at the end of a session, one combined offer covers them all.
  - **If accepted:** each accepted item runs as a background or parallel task where the agent tool supports one, and work on the next item carries on. Otherwise it waits until the current request is finished and then runs. Results are written into the bit page (`## Prior-use checks`, `## Feedback`), and a one-line summary of each is reported when it finishes. A `close-match` is reported right away and never just filed.
  - **Required gate:** a current `clear` or `similar-premise` verdict is **required** before a bit becomes `a-material`. Craft feedback is never a gate.
- **Operations:**
  - `Operation: develop-bit <idea or premise or bit>`: (1) turn an Inbox idea into a premise page if it isn't one yet, stating the premise back in the user's words; (2) check for duplicates in the vault (existing premises and bits with the same topic or angle, including burned ones) and surface related bits as callback or chunk candidates; (3) suggest branches in a `> [!suggestion]` callout, which the user promotes; (4) for a chosen branch, create the Bit page and structure the user's material into setup / punchline(s) / tags / act-outs, keeping their wording as-is; (5) propose `sets-up` / `callback-to` links for the user to confirm; (6) if a clear research opening shows up (a factual claim, a possibly dated or niche reference, a thin premise), offer the matching topic research in one line; (7) move or create the board card. Revisions to an existing bit follow the versioning rules above. Craft feedback and the prior-use check are **not** run here. They come from the wrap-up offer when work moves on, or from a direct request.
  - `Operation: feedback-bit <bit>`: give craft feedback on the bit's `## Current` (see Craft feedback) and set `feedback-version`. Normally triggered by the wrap-up offer and also available directly.
  - `Operation: research-bit <bit | premise> [facts | experience | reach | fact-check]`: run topic research on a bit or premise. It does all four types unless specific ones are named, writes to `## Research notes` and sets `research-checked`. Normally triggered by an accepted offer and also available directly.
  - `Operation: check-prior-use <bit | all-pending>`: run the prior-use check above on one bit or on every bit with no current check. Normally triggered by the wrap-up offer and also available directly.
  - `Operation: build-set <target-length> [context] [themes]`: (1) gather candidate bits (`working` / `a-material`, or `workshopping` for workshop sets, with the context deciding which) and exclude burned bits; (2) propose an opener and closer from recent scores; (3) order the middle by themes and the callback ordering rules; (4) total the runtime against `target-length` and state the difference; (5) flag broken callbacks, missed callback chances, missing segues, and any bit whose prior-use verdict is `close-match` or stale; (6) write the Set page as embeds. It proposes; the user decides the final order.
  - `Operation: log-set <set> [date] [venue] [notes or recording link]`: (1) if a recording is given, transcribe it where possible into `Raw/` with the original link (see Recording transcripts); (2) create the Performance page, with the running order and version numbers snapshotted; (3) record one score per bit from what the user reports, **asking for any not given rather than guessing**. A transcript's laughter markers can be shown as context but never replace the user's score; (4) update each bit's `last-performed`, `stage-count` and `recent-scores`, and append a dated entry to its `## Stage history`; (5) if a transcript exists, compare what was said on stage against each bit's `## Current` and show the differences (ad-libbed tags, reworded punches). For those, or for changes the user reports, ask whether any should become a new `## Current` version, **in the user's own on-stage wording**; (6) suggest status changes backed by the scores (e.g. `workshopping → working`) for the user to confirm; (7) if the notes, recording or conversation suggest the set was released publicly, offer a Burn review.
  - `Operation: review-burn <release | bit>`: run the Burn review above for a release (checking all candidate bits) or for one bit (checking it against known releases). Normally triggered by a release being mentioned and also available directly.
  - `Operation: review-material`: list bits with no stage time in 30+ days (core staleness window), premises still `exploring` with no chosen branch, parked branches on premises whose bits have been burned (good starting points for new work), sets that include retired or burned bits, prior-use checks that are stale or missing, and early board columns growing faster than material is moving forward.
- **Boundaries addition:**
  - Never write into the user's joke wording. Claude's alternatives, branches and tags go in a `> [!suggestion]` callout, and craft feedback goes in a `> [!feedback]` callout. Only the user moves anything into the text.
  - Never take joke material from outside sources. Topic research produces cited notes, never joke text. Other comedians' jokes are never shown or summarized outside the prior-use check, which reports them only as overlap evidence.
  - Never run craft feedback unprompted during drafting, and never repeat a declined research or wrap-up offer until the bit changes.
  - Never send a bit's full text to a search service, for research or for prior-use checks. Use paraphrased premise and angle keywords only.
  - Never state that a bit is original. Only report what the sources checked did or didn't show.
  - Never mark a bit burned without a Burn review and the user's explicit per-bit decision. Never present a burn candidate without its evidence, or leave out a plausible candidate because it seems minor. Never edit a burned bit's page after it's locked, and never move a burned bit back to an active or retired status.
  - Never fabricate or reconstruct a transcript, and always keep the original recording link.
  - Never record a performance score the user didn't give, never mark a bit `working` without stage data behind it, and never move a bit to `a-material` without a current prior-use verdict of `clear` or `similar-premise`.
  - Never edit a Performance page after creation.
  - Flag material naming real private people (family, exes, coworkers) before it goes into a set for a recorded show, as a prompt for the user to decide on, not a block.
  - WIP discipline: an Idea or Premise column that keeps growing while Drafting stays empty is flagged as a signal to develop material, not just capture more.
- **Deadline hook:** a booked gig can be a Projects Milestone with a Tasks due date, linked to its Set page. `review` and `plan-day` then surface upcoming shows the usual way, along with the set's runtime difference and any unresolved flags.
- **Dashboard contribution:** a library summary (bit count by status, total `working` + `a-material` runtime in minutes), bits awaiting a prior-use check, any `close-match` verdicts, and the next booked gig with its set's runtime difference.
- **Independence:** `Comedy/Comedy Board.md` is this module's own board, separate from `Projects/Board.md` and from Content Production's `Content/Content Board.md`. Stacking never merges them.
- **Page templates:** scaffolded as `Comedy/Premises/_Template.md`, `Comedy/Bits/_Template.md`, `Comedy/Sets/_Template.md`, `Comedy/Performances/_Template.md`, `Comedy/Releases/_Template.md`.
  - **Bit page:**
    ```
    ---
    type: bit
    status: drafting
    premise: "[[<Premise>]]"
    themes: []
    runtime:
    current-version: 1
    sets-up: []
    callback-to: []
    derived-from:
    derived-bits: []
    prior-use: unchecked
    prior-use-checked:
    prior-use-version:
    feedback-version:
    research-checked:
    last-performed:
    stage-count: 0
    recent-scores: []
    tags: [type/bit]
    ---

    # Bit - <Name>

    ## Current
    <!-- v1 · <date> · user's wording only -->
    **Setup:**
    **Punch:**
    **Tags:**
    **Act-outs:**
    **Segue in / out:**

    ## Version history

    ## Research notes

    ## Feedback

    ## Stage history

    ## Prior-use checks
    ```
  - **Premise page:** frontmatter as under Folders; body `## Premise` (user's words), `## Branches` (a list, each item `A — <description> · <status>`, with `→ [[Bit - …]]` once chosen), then any `> [!suggestion]` callout, and `## Research notes`.
  - **Set page:** frontmatter as under Folders; body `## Running order` (numbered embeds), `## Runtime` (a Dataview sum of `runtime` over the linked bits, compared with `target-length`), `## Flags` (written by `build-set`).
  - **Performance page:** frontmatter as under Folders; body `## Running order as performed` (a table: #, bit, version, score), `## Notes`.
  - **Release page:** frontmatter as under Folders; body `## Evidence` (a list: link · what it shows · date checked), `## Burn decisions` (a table: bit, matched version, extent, decision, justification, date).
  - **Bit page, once burned:** a `> [!burned]` callout at the top, plus a `## Burn record` section (release link, matched version, extent, evidence links, the user's justification, decision date) added during the Burn review. It's locked after that.
- **Archive behavior:** burned bits are locked records and can't be archived or deleted, and neither can the Release pages their burn records cite. Other material (retired bits, parked premises, old sets) archives normally. A set's `status: archived` only marks the set as out of use; moving material out of the live vault is `Operation: archive`. `Comedy/Performances/` pages follow the same archive rules as `Raw/`: moved and deleted only through the archive operations, never edited.
- **Recommended plugins:** Kanban (for `Comedy/Comedy Board.md`), Bases or Dataview (for `Comedy/Comedy Library.base` and set runtime totals), Tasks (only if gigs are tracked as dated Milestones).

### Module: Investment Strategy

**Module version: 5.0**

**Requires:** Research

**Declared citation-rigor:** standard

**Use case:** building your own investing rules from cited research, grouping them into strategies for specific needs, running those strategies inside a portfolio policy derived from your investor profile, grading strategies on imported backtests and your own trades, and recording every improvement or invalidation. **Requires the Research base module** for sourcing and credibility. Every rule's reasoning cites where it came from. All rules and decisions are the user's. Claude structures, checks, imports, computes from imported data, flags weaknesses and suggests, but never places trades and never presents a rule as advice about a specific security.

- **Supported assets:** `stock`, `etf`, `crypto`. Every strategy, rule, backtest and trade declares `asset-classes` (a list; a trade or backtest usually has one). A rule or strategy may apply to several asset classes or only one (e.g. ETF only). Grades are always given per asset class and never carried from one to another: a strategy graded A on ETFs is ungraded on crypto until tested there. The list can be extended per vault (e.g. options or futures later). An extended class may need its own fields, added in that vault's instructions.
- **Every source is data to be checked, not an authority.** Investing sources are varied (articles, videos, books, forum posts, community scripts) and often make performance claims that aren't backed up. So each source's claims are treated as data to compare against everything else the vault holds, and trust is earned from that comparison, not from who said it.
  - **Tracked on the source's Summary page,** since `Raw/` is never edited. Fields:
    - `trust` (`unassessed` / `low` / `medium` / `high`), with a one-line reason
    - `performance-claims` (`none` / `unverified` / `corroborated` / `contradicted` / `reproduced` / `not-reproduced`)
    - `corroborated-by` and `contradicted-by`: links to other sources, backtests or trades
  - **Trust changes as evidence arrives.** `ingest` compares a new source's claims with what's already there: other Summaries and Concepts, and the vault's own Backtests and Trades. It updates the fields on both sides, and genuine conflicts go through core Contradiction handling. When a backtest tests a rule taken from a source, its result is linked back to that source's Summary as `reproduced` or `not-reproduced`. Each change to `trust` is dated in a `## Trust log` on the Summary.
  - **A claimed result is a hypothesis.** A figure like "80% win rate" becomes a rule to test, never a cited result. A rule's rationale may cite a low-trust source, and the rulebook shows that source's trust next to the citation.
- **Indicator-based rules:** every rule's trigger is built from **conditions** (see Conditions), each a test on indicator values, which makes it testable. A pattern the user wants to use (a chart pattern, a divergence, a setup) is turned into a **custom indicator** that outputs a signal the rule can reference, rather than being described in words. A rule whose trigger can't be stated as indicator conditions yet stays `draft`, and the indicator it needs is recorded as `status: needed`.
- **Conditions (one condition, many rules):** a condition is a single named, testable statement on indicator values. Examples: "RSI(14) below 30", "price above its 200-day SMA", "average daily traded value above $5M", "SPY below its 200-day SMA". Each lives on its own page and is **written once and used by any number of rules.**
  - A rule's trigger combines conditions with AND/OR, e.g. `[[Cond - RSI Oversold]] v2 AND [[Cond - Above 200-day SMA]] v1`.
  - **Scope:** `symbol` for a condition on the security being traded, `market` for a condition on the market as a whole (an index, a volatility measure, BTC for crypto). Market-scope conditions are what Scenarios use.
  - **Versioned like rules.** A change to a condition flags every rule using the old version (see Changes cascade).
  - Conditions aren't graded themselves. Their contribution is shown only through comparison backtests (a rule with and without the condition).
  - **Checked for reuse:** `define-rule` looks for an existing condition before creating a new one, so the same test isn't written twice with slightly different wording or parameters.
- **Portfolio layer (the overall rules every strategy works within):**
  - **Investor Profile → Portfolio Policy → strategies → rules.** The profile states who is investing and why. The policy turns that into limits. Each strategy declares its share of those limits, and its sizing and stop rules must fit inside them.
  - **Limits are ceilings.** A strategy or rule may be stricter than the policy, never looser.
  - **Encouraged, never required, and can be put off.** Rules and strategies can be built, backtested and graded with no Investor Profile or Portfolio Policy. Research ingested along the way is expected to shape both, along with the user's own needs and goals. Until they exist, every policy check reads `unchecked (no policy)`, never a pass or a breach.
    - **Each policy limit is optional too.** A limit left blank reads `not set` and isn't checked. A policy can start with just a per-trade risk figure and grow from there.
    - **Offered at setup, then an occasional reminder.** The first time the module is used, Claude offers `set-profile` / `build-policy` once and accepts a deferral. After that, one line is shown in the following cases:
      - each `review-rules` run, while either page is missing or thin (only some sections stated or limits set)
      - each `build-rulebook`, whose policy summary reads "no portfolio policy yet"
      - the first time a strategy moves to `forward-testing`, since real or paper money is now involved
    - **Never more than that.** No per-session or per-prompt nudging, and a declined reminder isn't repeated within the same operation run.
  - **Investor Profile** (`Investing/Portfolio/Investor Profile.md`, one per vault, versioned). All in the user's words and values:
    - **Goals and outlook:** what the money is for and the user's own view of how they want to invest (e.g. growth, income, capital preservation).
    - **Time horizon:** target date (e.g. retirement year), with years remaining calculated from it. Also any earlier dated needs (a house, tuition).
    - **Risk capacity:** how much loss the user can *afford*: income stability, emergency fund held outside the investable amount, other assets, and dependants.
    - **Risk tolerance:** how much loss the user is *willing* to sit through, e.g. the largest drop from peak they'd hold through without abandoning the plan. **Where capacity and tolerance differ, the lower one governs the policy.**
    - **Liquidity needs:** planned withdrawals and when.
    - **Experience:** per asset class and per style (long-term holding vs active trading).
    - **Constraints and exclusions:** asset classes, sectors or instruments the user won't hold, and whether leverage, margin or short selling is allowed at all.
    - **Accounts:** each with a type (e.g. taxable, retirement, crypto exchange), the asset classes it can hold, and its constraints (e.g. no margin or shorting in a retirement account). Labels only. Never account numbers.
    - **Market outlook (optional):** the user's current dated view of the market, with cited research. It informs market conditions and policy reviews but never sets a limit on its own.
  - **Portfolio Policy** (`Investing/Portfolio/Portfolio Policy.md`, versioned like a strategy, each limit with a rationale citing the profile and any research behind it):
    - **Allocation:** target percentage per asset class, and a **core vs active split**: a long-term core and an active sleeve. Both are run by strategies (see Long-term strategies). Each target has a rebalancing band.
    - **Per-trade risk:** the most any one trade can lose if its stop is hit, as a percentage of account value. The standard sizing input: position size = (account × risk %) ÷ distance to the stop.
    - **Position limits:** the largest single position as a percentage of account, overall and per asset class.
    - **Total open risk ("portfolio heat"):** the most the account can lose if every open position hit its stop at once.
    - **Per-strategy allocation cap:** the largest share of the active sleeve any one strategy may use, and the most open positions it may hold.
    - **Concentration limits:** per symbol, per sector and per group of closely correlated holdings. Crypto assets are treated as one correlated group unless the policy says otherwise. **This is an exposure check only:** it adds up what the account holds in one symbol across strategies, to see the total risk. **Results are never combined by ticker.** Grades, metrics and discipline always stay per strategy, since the point is to find the best strategy for each need.
    - **Cash reserve:** minimum cash held inside the investable account, separate from the emergency fund in the profile.
    - **Leverage, margin and shorting:** allowed or not, and limits if allowed. Never looser than the profile's constraints or the account's.
    - **Custody:** the largest share of crypto held on an exchange rather than in the user's own wallet.
    - **Drawdown circuit breakers:** staged responses to losses from the account's peak value, e.g. at −X% halve per-trade risk, at −Y% pause new active trades and review. Optionally also daily or weekly loss limits for active trading. The user sets the levels.
    - **Horizon glide path:** a table of limits by years remaining (e.g. 20+, 10–20, 5–10, under 5). The active sleeve, crypto cap and per-trade risk typically shrink as the target date gets closer. When the profile's years remaining crosses into a new band, the policy is flagged for review, not changed automatically.
    - **Review triggers:** a set period (e.g. yearly), a change to the profile, a glide-path band crossed, a circuit breaker hit, or a planned withdrawal coming up.
  - **Liquidity lives in the entry rules, not the policy.** A minimum average daily traded value, so a position can be exited at its stop, is usually part of a strategy's entry criteria: a `filter` rule. It matters most for small-cap stocks and small crypto assets. `define-rule` mentions it as useful context when a strategy has no liquidity filter. It isn't required.
  - **Claude proposes the numbers, the user sets them.** `build-policy` proposes each limit with its reasoning and any cited typical ranges, and flags any proposed limit that conflicts with the profile. Only the values the user confirms are written to the policy.
  - **Portfolio snapshots:** `Investing/Portfolio/Snapshots/` holds one page per imported holdings export (a position and balance statement), **never edited after creation, same as `Raw/`**, with the original file in `Assets/`. Snapshots give account value over time. That's what allocation drift, portfolio heat and the drawdown from peak are measured against.
  - **Policy changes cascade:** when a new policy version tightens a limit, every strategy whose declared allocation or sizing now exceeds it is flagged. It must be brought within the limit in a new strategy version before its next rulebook. Strategies never run on an out-of-date policy silently.
- **Folders:**
  - `Investing/Portfolio/`: `Investor Profile.md`, `Portfolio Policy.md` and `Snapshots/` (see Portfolio layer). Snapshot frontmatter: `type: portfolio-snapshot`, `date`, `accounts` (labels), `total-value`, `cash`, `by-asset-class` (values), `policy-version` (the policy in force), `report` (link to the original in `Assets/`). Body: holdings table, allocation against target, and computed checks (see `check-portfolio`).
  - `Investing/Strategies/`: one page per strategy, which is the graded unit. Frontmatter: `type: strategy`, `need` (the goal it serves, in the user's words), `asset-classes`, `timeframe` (chart interval, e.g. `1D`, `4h`), `benchmark` (what it's measured against, e.g. SPY for US stocks, BTC for crypto; defaults to buy-and-hold of the same symbols), `sleeve` (`core` / `active`), `allocation` (its share of that sleeve, as a percentage), `risk-per-trade` (as a percentage of account, at or under the policy's), `max-positions`, `policy-version` (the Portfolio Policy version it was last checked against), `status` (see Strategy lifecycle), `current-version` (integer), `grades` (per asset class, e.g. `{etf: B, stock: insufficient-sample}`), `evidence-level` (per asset class: `none` / `in-sample` / `out-of-sample` / `forward`), `last-graded` (date), `grade-version` (the `current-version` those grades cover). Body: `## Current` pins the exact rule set, as a list of rules each with its version (e.g. `[[Rule - RSI Pullback Entry]] v3`), plus the strategy's scenarios (see Scenarios). Also `## Version history`, `## Grade history` and `## Changelog`.
  - `Investing/Rules/`: one page per rule. Frontmatter: `type: rule`, `kind` (`entry` / `exit` / `stop` / `sizing` / `filter`), `asset-classes`, `timeframe`, `conditions` (links, each with its version), `indicators` (links, derived from its conditions), `strategies` (links to every strategy that uses it), `status` (`draft` / `tested` / `retired` / `invalidated`), `current-version`, `derived-from` (link, when grown from a retired or invalidated rule), `themes`. Body: `## Current` holds the trigger (its conditions, combined with AND/OR and pinned to versions), the action, parameters with their values, when it applies (asset classes, regimes), and its **rationale**, cited to the Concepts or Summaries it came from. Also `## Version history` (earlier versions, dated and numbered, newest first), `## Evidence` (see Evidence ledger) and `## Changelog`.
  - `Investing/Conditions/`: one page per condition (see Conditions). Frontmatter: `type: condition`, `scope` (`symbol` / `market`), `indicators` (links, with versions), `asset-classes`, `timeframe`, `current-version`, `used-by` (links to rules and strategies' scenarios), `status` (`draft` / `in-use` / `retired`). Body: `## Current` holds the statement, written precisely enough to test (indicator, comparison, value, timeframe), plus `## Version history` and `## Changelog`.
  - `Investing/Indicators/`: one page per indicator the rules use. Frontmatter: `type: indicator`, `source` (`built-in` / `custom` / `community`), `platform` (e.g. `tradingview`), `status` (`needed` / `in-use` / `retired`), `current-version`, `outputs` (the plots or signals rules can reference), `repaints` (`no` / `yes` / `unknown`), `used-by` (links to conditions). The body holds its purpose, its inputs and their defaults, and for a custom indicator its script, either in a fenced code block or linked from `Assets/`, with version history. A pattern-detecting custom indicator also states the pattern it's meant to find, in the user's words, so its logic can be checked against that intent.
  - `Investing/Backtests/`: one page per imported backtest run. **Never edited after creation, same as `Raw/`.** The one exception is appending to its `## Review` section. Frontmatter: `type: backtest`, `strategy` (link) + `strategy-version`, `rule-versions` (the pinned rule set actually tested), `indicator-versions`, `asset-class`, `symbols` (or the universe, e.g. "S&P 500 members as of 2026-01-01"), `timeframe`, `period-start`, `period-end`, `sample` (`in-sample` / `out-of-sample`), `platform` (e.g. TradingView Strategy Tester), `costs` (commission and slippage assumed; `none stated` if the report doesn't say), `sizing` (initial capital and position sizing used), `optimization-runs` (how many parameter variants were tried on this same data, if known), `compares` (optional: another backtest this one is a with/without comparison against), `report` (link to the original export in `Assets/`), `bias-flags` (list). Body: `## Metrics` (see Grading), `## Benchmark` (buy-and-hold of the same symbols over the same period, from the report or computed from imported price data), `## Bias check` and `## Review`.
  - `Investing/Trades/`: one page per closed position (entry to exit), created by `import-trades`. Frontmatter: `type: trade`, `symbol`, `asset-class`, `account-type` (`paper` / `live`), `direction` (`long` / `short`), `entry-date`, `entry-price`, `exit-date`, `exit-price`, `size`, `fees`, `pnl`, `r-multiple` (profit or loss divided by the planned risk, if a stop was recorded), `strategy` (link) + `strategy-version`, `rules` (links, each with its version), `attribution` (`confirmed` / `proposed` / `unassigned`), `followed` (`yes` / `partial` / `no` / blank until answered), `account` (label from the profile), `risk-at-entry` (the loss at the planned stop, as a percentage of account value at entry; blank if no stop was recorded), `policy-version` (the Portfolio Policy in force at entry), `policy-breaches` (list, empty if none), `screenshots` (optional links to chart images in `Assets/`, e.g. at entry and at exit, showing the indicators the rules used), `import` (link to the Raw import it came from). **Imported fields (symbol through fees and pnl) are never edited after creation.** Attribution, `followed` and `## Review` notes are filled in afterwards.
  - **Trade-history imports:** a broker or exchange export is ingested as a Raw source, `R - <Broker> Trades <start>–<end>.md`, frontmatter `source-type: trade-history`, `period`, `account-type`, with the original CSV/XLSX kept in `Assets/` (the same spreadsheet convention Due Diligence uses). Account numbers and personal identifiers are removed from the Raw page and never copied onto Trade pages.
- **New pages:** `Investing/Grading Policy.md` (the editable thresholds used for grading; see Grading). `Investing/Investing Library.base` (Bases, or a Dataview table where Bases isn't available): strategies and rules, sortable by status, asset class, grade, evidence level and last graded. Rulebook pages live in `Outputs/Investment Strategy/`.
- **Migration note (from 4.x):** `Investing/Library.base` is renamed to `Investing/Investing Library.base`, so it can't clash with another module's library view. Rename it and update any embeds of it.
- **Tags:** `#type/investor-profile`, `#type/portfolio-policy`, `#type/portfolio-snapshot`, `#type/strategy`, `#type/rule`, `#type/condition`, `#type/indicator`, `#type/backtest`, `#type/trade`, `#type/rulebook`. `#status/invalidated` on invalidated rules and strategy versions (on top of frontmatter `status`), so they stand out in graph and search.
- **Strategy lifecycle:** `draft → backtested → forward-testing → active`, plus `probation`, `retired` and `invalidated`.
  - `draft`: rules pinned, no graded backtest yet.
  - `backtested`: at least one graded in-sample backtest.
  - `forward-testing`: passed an out-of-sample backtest and now running on paper or with small live size.
  - `active`: meets the Grading Policy's promotion gate. It's current best practice for its need, in the asset classes it's graded for.
  - `probation`: forward results have drifted below the backtest, or new evidence weakens it. Still usable, flagged in every rulebook.
  - `retired`: set aside by choice. Can come back.
  - `invalidated`: evidence shows this version doesn't work. **Invalidation applies to a version.** The version's record and grades stay in history. A revised version may continue on the same page, starting again at `draft`, because its grade doesn't carry over.
  - **Status changes are proposed by `grade-rule` or `review-rules` and confirmed by the user.** They're never applied silently.
- **Versioning (rules, strategies, indicators):** each page has `## Current` and `## Version history`. A change moves the old `## Current` into the history, fills a new one and bumps `current-version`. The filename never changes, so links never break. Following core append-don't-overwrite, earlier versions are never rewritten or deleted.
  - **Changes cascade:** indicator → condition → rule → strategy. Changing an indicator's version flags every condition using it. A new condition version flags every rule using it, and a new rule version makes every strategy pinning the old one out of date. The next strategy version pins the new one, and its grade starts over.
  - **Changelog entries:** every version change adds an entry to the page's `## Changelog`: date, old → new version, what changed, and **why**, linking the evidence or research that prompted it.
- **What gets graded:** a backtest tests a set of rules together, since an entry means nothing without an exit and a stop. So **grades belong to a strategy version, per asset class.** A rule page shows the grades of every strategy version it's part of. A rule's own contribution is only claimed from a comparison backtest: the same strategy with and without the rule, or with the rule's old and new version, linked through `compares`. It's never inferred from the combined result.
- **Long-term strategies (the core):** core holdings are run by strategies with `sleeve: core`, tracked and graded separately from active ones like every other strategy. One can be very basic, e.g. "hold a broad index ETF, add monthly, rebalance to target once a year". Or it can have its own rules for longer-term holdings, e.g. valuation-based entries, fundamentals filters, or trimming when a holding exceeds its position limit. The same pages, versioning and evidence ledger apply. Grading differs only where few trades happen (see Grading).
- **Evidence ledger (on every rule and strategy):** the `## Evidence` table is append-only. Each row has a date, kind (`research` / `backtest` / `trade-review` / `comparison`), a link, the version it bears on, the effect (`supports` / `weakens` / `invalidates` / `neutral`) and a one-line note. Research rows can support or weaken a rule's **rationale**. Only backtest, comparison and trade-review rows can change a **grade**.
- **Grading (per strategy version, per asset class, per `Investing/Grading Policy.md`):**
  - **Metrics:** taken from the imported backtest report, or computed from its imported trade list with the method stated. Covers: number of trades, win rate, average win and average loss, expectancy per trade after costs, profit factor, maximum drawdown, net return against the buy-and-hold benchmark, and time in the market. Forward metrics are computed the same way from Trade pages where `followed: yes`.
  - **Two parts, always shown together:** a **performance grade** (`A`–`F`) and an **evidence level** (`none` / `in-sample` / `out-of-sample` / `forward`), e.g. "B · out-of-sample, 64 trades". Below the policy's minimum sample, the grade reads `insufficient-sample`, never a letter.
  - **Starting defaults (editable on the policy page):**
    - A letter grade needs at least 30 trades per asset class. **Long-term strategies** that trade rarely use a minimum **period** instead: by default a backtest of 10+ years that includes at least one bear market. They're graded mainly on return and maximum drawdown against their benchmark. Forward evidence comes from snapshot history rather than trade count.
    - Performance grade by profit factor after costs: A ≥ 1.75, B ≥ 1.4, C ≥ 1.15, D ≥ 1.0, F < 1.0 or expectancy ≤ 0.
    - A maximum drawdown worse than the benchmark's lowers the grade one letter.
    - **Promotion gate to `active`:** a C or better on both in-sample and out-of-sample backtests, then at least 20 forward trades with positive expectancy.
    - **Drift trigger for `probation`:** after 20+ forward trades, forward expectancy below half the out-of-sample expectancy, or a forward profit factor below 1.0.
  - **Weaker evidence:** a backtest with unresolved bias flags counts as weaker evidence. It's shown with its flags, and it can't be the only backtest behind a promotion.
- **Bias check (on every imported backtest):** flags, each written to `bias-flags` and explained in `## Bias check`.
  - `repainting`: any indicator used has `repaints: yes/unknown`.
  - `no-costs`: commission or slippage not stated.
  - `survivorship`: the universe was defined as of today rather than as of the test period.
  - `look-ahead`: signals use data not available at the bar they act on.
  - `overfit-risk`: a high `optimization-runs` count on the same data, or parameters tuned on the period being reported.
  - `small-sample`: below the policy minimum.
  - `short-period`: the period covers only one market regime (e.g. only a bull market).
  - `sizing-mismatch`: the backtest's position sizing differs from the strategy's `risk-per-trade` under the current policy, so its drawdown and return figures don't reflect how the strategy would actually be run. Returns scale with sizing. Drawdown doesn't scale in a straight line, so it isn't adjusted, only flagged.
  - A flag the report can't settle is recorded as `unknown`, never assumed clear.
- **Trade attribution and discipline:** `import-trades` proposes which strategy and rules each trade belongs to, based on the symbol, timeframe, dates and any notes, and marks it `attribution: proposed`. The user confirms or corrects in one batch table. It never assumes attribution silently. Trades that match no strategy stay `unassigned` and count as discretionary. `followed` is asked, never guessed.
  - **Trades that broke the rules don't count toward the grade:** `partial`/`no` trades don't count toward a strategy's grade. They count toward a **discipline** figure shown next to it (e.g. "17 of 20 followed"), so a bad rule and a rule that wasn't followed stay distinguishable.
  - **Policy breaches:** `import-trades` checks every trade against the policy version in force at its entry date. Checks cover per-trade risk, position size, the strategy's allocation and position count, concentration, portfolio heat (using the nearest earlier snapshot plus the other open trades), whether the account allows it, and whether a circuit breaker was in effect. Any breach is written to `policy-breaches`. A breach is a discipline issue, not a rule result, so it doesn't change the grade. The discipline figure reports it separately, e.g. "17 of 20 followed · 2 policy breaches". A check that can't be run for lack of data (no stop recorded, no snapshot) is shown as `unchecked`, never assumed to pass.
  - **Paper and live trades both count** as forward evidence, labeled by `account-type`. Grades and discipline figures show the split (e.g. "24 forward: 18 paper, 6 live"). Whether live trades should weigh more is left for later.
- **Scenarios (market conditions):** a scenario is a market-scope condition, or a combination of them (e.g. "SPY below its 200-day average", "BTC 30-day volatility above X"). The same condition can drive scenarios in many strategies. A strategy's `## Current` lists the scenarios it responds to and what changes in each: rules suspended, sizing changed, or the strategy switched off. Backtests report per-regime results where the report or the imported data allows it. Rulebooks show each active strategy's scenario table.
- **New research that bears on existing rules:** when core `Operation: ingest` brings in a source relevant to an existing rule or indicator (the same indicator, theme or strategy need), it adds a `research` row to that rule's evidence ledger and flags the rule for the next `review-rules`. It doesn't change the rule. A source that contradicts a claim the rule's rationale cites goes through core `## Contradiction handling`. The rule is flagged, never auto-changed.
- **Operations:**
  - `Operation: set-profile`: create or revise the Investor Profile by interview.
    1. Ask about each profile section in turn. Record answers in the user's words, and skip nothing silently: an unanswered section is marked `not yet stated`.
    2. Point out where risk capacity and risk tolerance differ, and which one governs.
    3. On a revision, move the old version to history with a Changelog entry, and flag the Portfolio Policy for review.
  - `Operation: build-policy`: create or revise the Portfolio Policy from the profile.
    1. Propose each limit with its reasoning, citing the profile section that drives it and any research on typical ranges.
    2. Flag proposed limits that conflict with the profile or with an account's constraints.
    3. Have the user set each final value.
    4. Write the new policy version, with a Changelog entry saying what changed and why.
    5. Check every strategy against it (see Policy changes cascade), and report which strategies now exceed a limit and by how much.
    6. Report whether the active strategies' allocations add up to more than the active sleeve.
  - `Operation: import-holdings <export>`: create a Portfolio Snapshot from a position and balance export, with the original in `Assets/` and account identifiers removed. Then run `check-portfolio` against it.
  - `Operation: check-portfolio [snapshot]`: check the latest (or named) snapshot against the policy in force. It checks allocation against target and the rebalancing bands, portfolio heat, concentration, cash reserve and custody. It also reports the drawdown from the peak snapshot value and which circuit-breaker stage applies, if any, plus years remaining against the glide-path bands. Reports each breach or rebalancing need with the numbers behind it. A newly reached circuit-breaker stage is reported first and added to the Portfolio Policy's `## Status log`. It stays in effect until the user confirms the review the policy calls for. Proposes actions (e.g. rebalance, reduce sizing, pause) for the user to decide on. Never assumes they've been done.
  - `Operation: define-rule <idea | research page> [strategy]`:
    1. State the rule back in the user's words.
    2. Rewrite its trigger as indicator conditions, and confirm that wording with the user.
    3. Break the trigger into conditions. Reuse existing Condition pages where the test matches, and create new ones (`status: draft`) otherwise. Link the indicators each needs. A pattern with no indicator yet gets an Indicator page with `status: needed`, which describes the signal it must output, and the rule stays `draft`.
    4. Record the rationale with citations.
    5. Check for duplicates and conflicts with existing rules, e.g. two entry rules in the same strategy with opposite conditions, or a rule already invalidated for the same asset class.
    6. For a `sizing` or `stop` rule, check it against the Portfolio Policy's per-trade risk, position limits and the account constraints, and flag anything that could exceed them.
    7. Attach it to a strategy if one was named, which pins it in a new strategy version. The new version is checked against the policy the same way a new policy version checks strategies.
  - `Operation: add-indicator <name> [script or link]`: create or version an Indicator page. For a custom script, record its inputs and outputs and ask whether it repaints (or mark `unknown`). Link it to the rules that use it. A new indicator version flags the dependent strategies (see Changes cascade).
  - `Operation: ingest-backtest <report file> [strategy]`:
    1. Keep the original export in `Assets/`.
    2. Create the Backtest page, pinning the strategy, rule and indicator versions. Anything the report doesn't make clear is asked, never assumed.
    3. Extract or compute the metrics and the benchmark.
    4. Run the bias check.
    5. Add a `backtest` (or `comparison`) row to the evidence ledger of the strategy and each rule.
    6. Offer to run `grade-rule`.
  - `Operation: import-trades <broker export>`:
    1. Ingest the export as a trade-history Raw source, with the original in `Assets/`, removing account identifiers.
    2. Create one Trade page per closed position. Open positions are listed on the Raw page and turned into pages once closed in a later import.
    3. Match each position against trades already imported so it isn't duplicated.
    4. Propose attribution in one table for the user to confirm.
    5. Ask `followed` for every attributed trade, batching the question.
    6. Run the policy-breach checks and fill `risk-at-entry`, `policy-version` and `policy-breaches`. Breaches are reported in one table.
    7. Add `trade-review` rows to the affected strategies' ledgers, and offer `grade-rule` for each.
  - `Operation: grade-rule <strategy | rule | all>`:
    1. Compute each asset class's grade and evidence level from the ledger, per Grading Policy. A rule argument grades every strategy that pins it.
    2. Compare forward results against backtest results for drift.
    3. Write the grade into `grades`/`evidence-level` and a dated `## Grade history` entry.
    4. Propose any status change (promotion, probation, invalidation) with the numbers behind it, for the user to confirm. A confirmed change adds a Changelog entry.
  - `Operation: review-rules`: lists what needs attention.
    - Strategies whose forward results are drifting from their backtests.
    - Grades that are out of date (`grade-version` behind `current-version`).
    - Rules flagged by new research since the last review.
    - `draft` rules and `needed` indicators blocking them.
    - Strategies stuck at `insufficient-sample`.
    - Trades still `unassigned` or missing `followed`.
    - Backtests with unresolved bias flags.
    - Strategies not graded in 30+ days (core staleness window).
    - Strategies on `probation` longer than the policy's review window.
    - Strategies checked against an out-of-date Portfolio Policy version, or exceeding its limits.
    - Portfolio Policy review triggers that have been reached. Covers a glide-path band crossed, a profile change, a circuit breaker waiting on its review, or the set review period passed.
    - No holdings snapshot in 30+ days, which leaves heat, drift and drawdown checks out of date.
  - `Operation: build-rulebook <need | strategy | all>`: write a dated rulebook to `Outputs/Investment Strategy/`. It covers:
    - **The overall rules first:** a summary of the Portfolio Policy version in force. That includes allocation targets and bands, per-trade risk, position, heat and concentration limits, circuit breakers and their current stage, and the current glide-path band. Also the latest snapshot's allocation against target.
    - Each strategy's allocation, `risk-per-trade` and `max-positions` within that policy.
    - Every `active` strategy for that need: its pinned rules in their current wording, scenario table, grade and evidence level per asset class, and discipline figure.
    - Strategies on `probation`, marked as such, with the reason.
    - Strategies in `forward-testing`, listed as candidates, not best practice.
    - **What changed since the previous rulebook for the same need:** promotions, probations, invalidations and version changes, each with its reason and evidence link.
    - Earlier rulebooks are never rewritten. Each new one links back to the one before it.
- **Output template:** the rulebook skeleton, filled by `build-rulebook` and by `Operation: draft` when targeting this module's Outputs path. It has: need, date, and the previous rulebook's link; portfolio policy summary; active strategies (rules, scenarios, grades, evidence, discipline); probation; candidates; what changed and why; and open weaknesses (bias flags, thin samples).
- **Deadline hook:** optional recurring Projects Milestones for rule review (e.g. `- [ ] Run review-rules 📅 <date> 🔁 every month`), for importing holdings, and for the Portfolio Policy's own review period (e.g. yearly). Dated needs from the Investor Profile (a planned withdrawal, the target date) can also become Milestones. `review` and `plan-day` then surface them the usual way. The periods are the user's choice at setup.
- **Boundaries addition:**
  - Never place, modify or cancel trades, and never connect to a brokerage or exchange account with trading access. Rulebooks describe the user's own rules and their evidence, not advice to buy or sell a specific security.
  - Never fabricate prices, metrics, backtest results or trades. Every metric comes from an imported report or is computed from imported data, with the method stated. A missing figure is shown as missing.
  - Never change a grade on research alone. Research changes a rule's rationale and flags it for review. Only backtest, comparison and trade-review evidence changes a grade.
  - Never give a letter grade below the policy's minimum sample. Never show a grade without its evidence level. Never carry a grade across asset classes or across versions.
  - Never promote a strategy to `active` on in-sample evidence alone, or on a backtest with unresolved bias flags as its only support. Never apply any status change without the user's confirmation.
  - Never assume a trade's attribution or whether the rule was followed; always ask. Trades that didn't follow the rules never count toward the rules' grade.
  - Never claim a single rule's contribution without a comparison backtest.
  - Never edit a Backtest page (apart from `## Review`) or a Trade page's imported fields after creation. Never rewrite version history, evidence ledgers, grade history, changelogs or earlier rulebooks. Invalidation is recorded, never deleted.
  - Never copy account numbers or personal identifiers from an import into the vault.
  - Never set a profile value or a policy limit the user hasn't confirmed. Claude proposes with reasoning, and the user decides. Never let a strategy or rule be looser than the policy, or the policy looser than the profile's constraints or an account's.
  - Never treat a breach, a rebalancing need or a circuit breaker as handled until the user says what was done. Never lift a circuit breaker without the review the policy calls for.
  - Never report a portfolio check as passing when the data behind it is missing. It's `unchecked`.
  - Never edit a Portfolio Snapshot after creation.
- **Dashboard contribution:**
  - Portfolio status: the latest snapshot's allocation against target, portfolio heat against its limit, drawdown from peak and any circuit-breaker stage in effect, and days since the last snapshot.
  - Strategies by status.
  - Every `active` strategy with its grade and evidence level per asset class.
  - Strategies on `probation` and drift alerts.
  - `draft` rules waiting on a `needed` indicator.
  - Trades awaiting attribution or `followed`.
  - The date of the last `review-rules` run.
  - Bases/Dataview queries only, no new plugin.
- **Archive behavior:** the Investor Profile and Portfolio Policy can't be archived or deleted; their history stays on the pages. Backtest pages, Trade pages, Portfolio Snapshots and trade-history Raw imports follow the same archive rules as `Raw/`: moved and deleted only through the archive operations, never edited. An `active` or `probation` strategy, and any rule or indicator it pins, can't be archived until the strategy is retired. A rulebook that is the latest for its need can't be archived while its strategies are still active. Retired and invalidated material archives normally. Their evidence goes with them, and the rulebooks that cite them keep marked links.
- **Independence:** rulebooks live under their own `Outputs/Investment Strategy/` path, kept separate from any other active flavor's outputs. With Due Diligence stacked, a holding's diligence items may be linked from a rule's evidence ledger as `research` rows, but the two modules' pages and outputs stay separate.
- **Out of scope, deliberately deferred:** tax treatment. That covers wash-sale windows, short- vs long-term holding periods and tax-lot selection. It was raised during design (2026-09-29) and set aside: it depends on the jurisdiction and isn't the focus of finding the best strategies. A vault that needs it can add optional policy lines or trade flags in its own instructions.
- **Tooling note:** this module needs no trading-platform integration. Backtests are run elsewhere (e.g. TradingView's Strategy Tester) and imported as report exports, and trades come from broker or exchange exports. Computing metrics or benchmarks from an imported trade list or price data needs a code-execution or spreadsheet capability in the agent tool. Without one, only metrics stated in the report itself are used, and anything else is shown as missing. **Future direction:** driving backtests directly through a locally running TradingView app or server, with access to its charts, symbols and indicators, including the custom ones. That would also allow automatic chart screenshots on trades and backtests, automated chart analysis, and switching indicators as rules need them. A backtest run that way would still produce an ordinary Backtest page with the same pinned versions and bias check, so nothing else in this module would change.
- **Page templates:** scaffolded as `Investing/Portfolio/Investor Profile.md` and `Investing/Portfolio/Portfolio Policy.md` (both with empty sections, filled by `set-profile` and `build-policy`), `Investing/Portfolio/Snapshots/_Template.md`, `Investing/Strategies/_Template.md`, `Investing/Rules/_Template.md`, `Investing/Conditions/_Template.md`, `Investing/Indicators/_Template.md`, `Investing/Backtests/_Template.md`, `Investing/Trades/_Template.md`, plus `Investing/Grading Policy.md` pre-filled with the starting defaults above.
  - **Rule page:**
    ```
    ---
    type: rule
    kind: entry
    asset-classes: []
    timeframe:
    conditions: []
    indicators: []
    strategies: []
    status: draft
    current-version: 1
    derived-from:
    themes: []
    tags: [type/rule]
    ---

    # Rule - <Name>

    ## Current
    <!-- v1 · <date> -->
    **Trigger:** <conditions with versions, combined with AND / OR>
    **Action:**
    **Parameters:**
    **Applies to / when:** <asset classes, market conditions>
    **Rationale:** <cited>

    ## Version history

    ## Evidence
    | Date | Kind | Link | Version | Effect | Note |
    |---|---|---|---|---|---|

    ## Changelog
    ```
  - **Strategy page:**
    ```
    ---
    type: strategy
    need:
    asset-classes: []
    timeframe:
    sleeve: active
    allocation:
    risk-per-trade:
    max-positions:
    policy-version:
    status: draft
    current-version: 1
    grades: {}
    evidence-level: {}
    last-graded:
    grade-version:
    tags: [type/strategy]
    ---

    # Strategy - <Name>

    ## Current
    <!-- v1 · <date> -->
    **Rules (pinned):**
    - [[Rule - …]] v1
    **Scenarios:**
    | Scenario (market condition) | What changes |
    |---|---|

    ## Grades
    | Asset class | Grade | Evidence level | Trades (paper / live) | Discipline | Graded version | Date |
    |---|---|---|---|---|---|---|

    ## Version history

    ## Evidence
    | Date | Kind | Link | Version | Effect | Note |
    |---|---|---|---|---|---|

    ## Grade history

    ## Changelog
    ```
  - **Backtest page:**
    ```
    ---
    type: backtest
    strategy: "[[Strategy - <Name>]]"
    strategy-version:
    rule-versions: []
    indicator-versions: []
    asset-class:
    symbols: []
    timeframe:
    period-start:
    period-end:
    sample: in-sample
    platform:
    costs:
    sizing:
    optimization-runs:
    compares:
    report:
    bias-flags: []
    tags: [type/backtest]
    ---

    # Backtest - <Strategy> v<n> · <asset class> · <period>

    ## Metrics
    | Trades | Win rate | Avg win | Avg loss | Expectancy | Profit factor | Max drawdown | Net return | Time in market |
    |---|---|---|---|---|---|---|---|---|
    Source: <report | computed from imported trade list — method>

    ## Benchmark
    ## Bias check
    ## Review
    ```
  - **Investor Profile page:**
    ```
    ---
    type: investor-profile
    current-version: 1
    target-date:
    years-remaining:
    governing-risk: <capacity | tolerance>
    tags: [type/investor-profile]
    ---

    # Investor Profile

    ## Current
    <!-- v1 · <date> · user's words and values -->
    **Goals and outlook:**
    **Time horizon:** <target date, years remaining, earlier dated needs>
    **Risk capacity:**
    **Risk tolerance:** <largest drop from peak you'd hold through>
    **Liquidity needs:**
    **Experience:**
    **Constraints and exclusions:** <incl. leverage / margin / shorting allowed?>
    **Accounts:**
    | Label | Type | Asset classes | Constraints |
    |---|---|---|---|
    **Market outlook (optional, dated, cited):**

    ## Version history

    ## Changelog
    ```
  - **Portfolio Policy page:**
    ```
    ---
    type: portfolio-policy
    current-version: 1
    profile-version:
    glide-path-band:
    circuit-breaker: none
    next-review:
    tags: [type/portfolio-policy]
    ---

    # Portfolio Policy

    ## Current
    <!-- v1 · <date> · every value confirmed by the user -->
    ### Allocation
    | Asset class | Target % | Band | Core / active split |
    |---|---|---|---|
    ### Risk limits
    | Limit | Value | Rationale (profile section / research) |
    |---|---|---|
    <per-trade risk, position size, portfolio heat, per-strategy cap, concentration, cash reserve, leverage/margin/shorting, custody>
    ### Circuit breakers
    | Drawdown from peak | Response | Review needed to lift |
    |---|---|---|
    ### Glide path
    | Years remaining | Active sleeve % | Crypto cap % | Per-trade risk % | Other changes |
    |---|---|---|---|---|
    ### Review triggers

    ## Status log
    <!-- circuit-breaker stages reached and lifted, glide-path bands crossed -->

    ## Version history

    ## Changelog
    ```
  - **Indicator page:** frontmatter as under Folders. Body: `## Purpose` (for a pattern indicator, the pattern in the user's words), `## Inputs and outputs`, `## Current` (the script or its `Assets/` link), `## Version history`, `## Changelog`.
  - **Condition page:** frontmatter as under Folders. Body: `## Current` (the testable statement: indicator, comparison, value, timeframe), `## Version history`, `## Changelog`.
  - **Trade page:** frontmatter as under Folders. Body: `## Charts` (embedded `screenshots`, if any) and `## Review` (the user's notes: setup, execution, mistakes).
  - **Grading Policy page:** the starting defaults above as editable values: minimum sample, grade thresholds, drawdown adjustment, promotion gate, drift trigger, probation review window. Also a `## Changelog`: a change to the policy is dated, and grades computed under an older policy say which policy date they used.
- **Recommended plugins:** Bases or Dataview (for `Investing/Investing Library.base`, the dashboard queries and metrics tables), Tasks (only for the recurring review Milestone).

### Module: Travel Planning

**Module version: 3.0**

**Use case:** planning vacations and road trips, domestic or international: researching destinations, comparing ways to get between places, choosing stays and activities with basic cost estimates for the actual party, preparing on a timeline (bookings, documents, country rules, packing), assembling a trip plan with an itinerary sized to the trip, and optionally logging the trip afterward. Standalone module. Claude researches, structures, estimates, checks and suggests, but never books, pays or cancels anything; it records only what the user has done.

- **Folders:**
  - `Travel/Places/`: one page per place, shared across trips. `place-kind`: `country` / `region` / `city` / `park` / `poi` (a sight or attraction) / `eat` (food and drink) / `shop` / `stay` (lodging worth remembering, separate from any one booking). Frontmatter: `type: place`, `place-kind`, `country`, `region`, `location` (`[lat, lng]`, optional, the shape Map View reads), `best-seasons`, `want-level` (someday / soon / must, optional), `visited` (list of trip links, maintained by `log-trip`), `rating` (from past visits, optional), `sources`, `checked`. Venue kinds (`poi`, `eat`, `shop`, `stay`) may add `reservation-needed`, `price-level` and `themes` (e.g. waterfall, brewery, playground). Body: highlights, getting there, typical costs, things to know (seasonal closures, local tips), visit notes. **Country pages** also hold the country check (see International trips).
  - `Travel/Trips/<trip>/`: one folder per trip, holding every page that belongs only to that trip, so a finished trip archives as one unit. The folder name is the trip's name, starting with year and month (`2026-11 Smokies Road Trip`), which keeps names unique when the same place is visited twice.
    - `<trip>.md`: the trip page, which is also the trip's card on the Travel Board (see Trip page).
    - `<trip> Board.md` and `<trip> Tasks/`: only for trips planned with their own task board (see Trip size).
    - `Legs/`, `Stays/`, `Activities/`: the trip's options and bookings (see Trip items).
    - `Days/`: only when the itinerary is per-day (see Itinerary).
    - `<trip> Packing.md`: the trip's packing checklist (see Packing).
    - `<trip> Brief.md`: the final itinerary and trip details, written by `trip-brief` (see Operations).
- **New pages:**
  - `Travel/Travel Board.md`: Kanban board, one card per trip, columns `Idea → Researching → Planning → Booked → Underway → Done`, plus `Cancelled`. Named `Travel Board`, not `Board`, so it never clashes with the core `Projects/Board.md`.
  - `Travel/Travel Profile.md` (optional, one per vault): usual travelers, each with birth month and year (so ages at travel time can be worked out), passport country, passport issue and expiry dates, any travel authorizations or visas (country, expiry, which passport they're linked to), and, for drivers, licence country and year first licensed; vehicles (fuel type, MPG or EV range); home airport or starting point; pace; lodging preferences; a preferred daily driving limit; accessibility or dietary needs. **No document numbers.** Offered the first time the module is used and accepted as a deferral; everything it holds can instead be given per trip.
  - `Travel/Travel Prep Timeline.md`: editable default lead times that `plan-trip` uses to date booking and prep tasks (see Prep timeline). Scaffolded with starter values, each marked as general guidance with where it came from.
  - `Travel/Travel Packing List.md`: an editable master packing list, grouped by category and tagged by when each item applies (every trip, kids by age band, road trip, flight, international, cold or hot weather). `pack` builds each trip's list from it. Scaffolded with a short starter list.
- **Trip page** (`<trip>.md`). Frontmatter: `type: trip`, `status` (matches the Travel Board column: idea / researching / planning / booked / underway / done / cancelled), `trip-kind` (`day-trip` / `multi-day`), `start-date`, `end-date`, `flexible-dates` (optional note), `origin`, `destinations` (Place links), `countries` (worked out from destinations and legs, transit countries included), `international` (true when any country differs from a traveler's passport country), `mode` (road-trip / fly / rail / cruise / mixed), `vehicle` (road trips), `party`, `budget` (optional), `buffer` (percent added to the estimate, default 10), `pace`, `planning` (`checklist` or `board`), `task-board` (link, when `board`), `itinerary` (`combined` or `per-day`), `est-total`, `booked-total`, `actual-total`, `log` (`pending` / `done` / `declined`, set once the trip ends). Body: goal and interests, party, cost summary, checklist (when `planning: checklist`), decisions, spending (see Costs), itinerary (when combined), trip log (if logged).
- **Party:** asked during `plan-trip` every time, never assumed: how many adults and how many children, with **each child's age at the time of travel** (ages change between trips, so they're stored per trip, not reused blindly). Pre-filled from the Travel Profile when one exists, then confirmed. Stored as `party: [{name, kind: adult | child, age, driver, passport-country}]`; names are optional. Ages are used for child fares and admission, room occupancy, activity age and height minimums, car seats, driving limits, vaccines and pace. A suggestion that fails a party member's age or height minimum is flagged, never silently included.
  - **International trips ask a little more,** only what the country check needs: each traveler's passport country; for each child, whether both parents or guardians are traveling; for each driver, age, licence country and years licensed; and whether anyone carries prescription medication (yes or no, no details).
- **Trip size (checklist or board), the user's choice:** `plan-trip` asks: *does this trip need its own task tracking board, or will a simple checklist be OK?* It gives context for the decision from what it knows so far (number of stops and overnight locations, nights, party size, how many bookings and prep tasks it expects), but sets no threshold and makes no default choice.
  - **Checklist** (`planning: checklist`): planning tasks are checklist items on the trip page, with Tasks-plugin due dates where they matter. Usually enough for a short or simple trip. A **day trip** (`trip-kind: day-trip`) is always a checklist trip with no stays, and skips the itinerary-form question.
  - **Board** (`planning: board`): the trip gets its own task board, `<trip> Board.md`, columns `To Do → On Hold → In Progress → Done`, with one page per task in `<trip> Tasks/` (frontmatter: `type: trip-task`, `trip` link, `task-kind` (research / route / stay / activity / booking / prep), `status`, `due`). Usually worth it for a trip with several stops, many nights, a larger party, international travel or many bookings. `On Hold` is for a task deliberately parked (waiting on other travelers, waiting for a price drop); core card-state tags still apply on top of it.
  - The user decides. A checklist trip can be moved up to a board later, in which case open checklist items become task pages, with done items left on the trip page as history. A board is never turned back into a checklist.
- **Tasks and results are separate.** A task is the work ("where to stay in Asheville"); its results are trip items (two Stay options, then one chosen and booked). The trip plan and itinerary are built from items, never from tasks, so closing a task never loses what it found.
- **Trip items** (`Legs/`, `Stays/`, `Activities/`), one page each:
  - Shared frontmatter: `type` (leg / stay / activity), `trip` link, `status` (`option` / `chosen` / `booked` / `cancelled` / `dropped`), `place` (Place link), `start`, `end` (local date and time where known), `est-cost`, `cost-basis` (per-person / per-night / per-vehicle / total), `cost-source` (researched / user / quoted / booked), `checked`, `booking-ref` (only as given by the user), `cancel-by`, `pay-by`, `actual-cost` (after the trip), `source`.
  - Legs add `from`, `to`, `leg-mode` (drive / flight / train / bus / ferry / rental-car / other), `start-tz` and `end-tz` (time zones, so times are always local to where they happen), `distance`, `duration`, `estimate` (true when distance or duration is approximate). Drive legs add `fuel-est` (see Costs) and `tolls`. A **rental car** is its own leg, from pickup to drop-off, with the rental company's terms: minimum and maximum driver age, years licensed, young-driver surcharge, International Driving Permit requirement, border-crossing limits and car seats requested. These are the company's rules, so they live on the rental, not the Place.
  - Stays add `check-in`, `check-out`, `rooms`, `occupancy-ok` (checked against the party), and `crib` (for infants: bring one or confirm the lodging's).
  - Activities cover anything at a time and place: sights, tours, tickets, dining reservations. They add `duration`, `day-part` (morning / afternoon / evening, for items without exact times), `age-min`, `height-min`, `priority` (must / want / maybe / backup). A `backup` activity is a fallback (e.g. an indoor option near a planned stop for bad weather or tired kids); it shows under its day as an alternative, not in the plan.
  - **Cancelled items are kept**, with any refund or credit noted, never deleted. Travel credits often matter later.
  - **Page names** start with the trip's name (`2026-11 Smokies Road Trip - Stay - Asheville Inn`), so they stay unique across trips.
- **Itinerary, generated from items:** the dated `chosen` and `booked` items are the single source of truth. The itinerary is built from them by `build-itinerary` and rebuilt whenever they change, inside a marked generated block, so the user's own notes outside that block are never overwritten.
  - **Form asked, sized by length:** `plan-trip` asks whether the user wants a per-day itinerary or one combined itinerary, suggesting combined for about four days or fewer and per-day for longer trips. The choice can be changed later; switching only rebuilds the view, since the items don't change.
  - `combined`: an itinerary section on the trip page, grouped by day.
  - `per-day`: one page per day in `Days/` (`<trip> - Day 03 - 2026-11-05`, frontmatter `type: trip-day`, `trip`, `date`, `overnight` Place link), each with a generated block and a free notes section.
  - Within a day, timed items are listed in local time, with the time zone shown when it changes; untimed items are grouped by `day-part`. Items still at `option` never appear; days with no plan show as open.
- **Prep timeline:** `plan-trip` seeds booking and prep tasks with due dates counted back from `start-date`, using `Travel/Travel Prep Timeline.md`, and only the ones that apply to this trip (international items only for international trips, driving items only with drive legs, kids' items only with children). A task whose date has already passed is created as due now and flagged as late. The starter timeline, all general guidance the user can edit:
  - **Bookings:** international flights about 6–8 months ahead, domestic 3–6 months; lodging at a popular destination 3–6 months (national park lodges 9–12); lodging along a road-trip route 2–3 months in peak season, 2–4 weeks off-peak; international rental cars 3–6 months; trains when booking opens (often about 90 days); tours and activities 1–3 months; dining 2–4 weeks.
  - **Documents and cover:** passport renewal at least 8 weeks before it's needed; travel authorizations or visas once the trip is booked (some take days to decide); International Driving Permit before departure; travel insurance when the trip is booked ("cancel for any reason" cover within 14 days of the first deposit); a doctor's check on vaccines or preventive medicine for international trips with children.
  - **Before leaving:** money (tell the bank, check foreign-transaction fees, currency), phone plan or e-SIM, offline maps and tickets 2–4 weeks out; home prep (pet or house sitter, mail hold, alarm company) 1–2 weeks out; packing (see Packing). When the trip crosses several time zones with children, shifting their sleep schedule 2–3 days before departure.
- **Packing:** `pack` builds `<trip> Packing.md` from the master list, keeping the items that apply to this trip's party (kids by age band), mode (road trip, flight), countries (international, plug adapters) and season. Road trips can group the list by where things go in the car (driver area, kids' area, snacks, trunk), so needed items stay reachable. Packed items are checked off; the trip's list can be edited freely without changing the master. Offered by `plan-trip` and rebuilt on request; `check-trip` notes an unpacked list in the last few days before departure.
- **Road trips:**
  - **Daily driving limit:** the user's own limit from the trip or Travel Profile wins. Without one, `plan-trip` suggests one from the party and says it's a rule of thumb, not a rule: by the youngest child's age (under 2: 3–4 hours; 3–5: 4–5; 6–10: 5–6; 11 and over: 6–8), or about 4–6 hours of driving (roughly 250–400 miles) for adults only.
  - **Stops:** a break about every two hours (more often, every 90–120 minutes, with children under 6), planned as real stops at Places along the route, with a `backup` indoor option near each.
  - **Shape:** routes are built around 2–3 anchor destinations, long drives are split into days with overnight stops, and a buffer day with no firm plans is suggested, adding about one day to the driving-hours estimate.
  - **Car seats:** each child needs the right seat for their age and size on every drive leg and rental; seat rules can vary by state or country on the route, so `check-trip` names the places to check.
  - **Distances:** from web research they're approximate and marked `estimate: true`; a maps or routing tool, when available in the session, is used instead and noted as the source.
- **International trips (country check):** for each country on the trip (transit included), `scout` builds a **country check** on that country's Place page, and `check-trip` tests the party against it. Each rule records its source, the source's own last-updated date, the date Claude checked it, and which passports it applies to. Rules come from official sources first: the traveler's own government's travel advice for their passport, the destination government for entry (the final authority), a health agency for vaccines, and the rental company for rental terms. If an official page can't be read (some block automated access), Claude says so and asks the user to check it, and never fills the gap from memory. Categories:
  - **Advisory:** the current travel advisory level and any regional warnings (per passport).
  - **Entry and passport validity:** the destination's actual rule (e.g. months valid after departure, issue date), never a flat six-month assumption (per passport).
  - **Visas and travel authorizations:** whether each traveler needs one, children and infants included, at the destination and any transit point; cost, decision time and validity (per passport).
  - **Stay limits:** e.g. 90 days in any 180 across a region (per passport).
  - **Traveling with minors:** consent letters or custody papers when a child isn't traveling with both parents; age rules at lodging.
  - **Medications:** whether medicines legal at home are restricted there, and what documents to carry.
  - **Customs:** food bans, cash declaration limits.
  - **Health:** health notices; vaccines recommended or required for entry (kept apart), by age and planned activities.
  - **Insurance:** whether health and auto cover apply abroad; medical and evacuation cover.
  - **Local laws:** rules that catch visitors out (ID carrying, conduct fines, drugs, restricted traffic zones).
  - **Driving** (only with drive or rental legs): licence acceptance and International Driving Permit, minimum driving age, side of the road, tolls or vignettes, required in-car equipment, child-seat rules.
  - **Emergency and help:** emergency number, embassy or consulate, embassy alert enrollment (e.g. STEP for U.S. citizens).
  - **Convenience (lower priority):** currency, tipping, plug type, transport strikes.
- **Costs, basic estimates only:** each item's `est-cost` comes from research or user input, scaled to the party by its `cost-basis` and any child pricing found. Drive legs estimate fuel as miles ÷ the vehicle's MPG × the fuel price (or the EV equivalent), plus tolls and parking. The trip page totals estimated, booked and actual costs by category (getting there, stays, activities, food and other), adds the trip's `buffer` to the estimate, and compares against an optional `budget`. Estimates are always labeled with their source and checked date. **Spending during the trip** can be added as it happens with `add-expense` (e.g. each fuel fill-up), into a Spending table on the trip page that feeds `actual-total`. This is a planning and total-cost tool: it doesn't split costs between people or track who paid; Claude can work out a split on request, but nothing is built in for it.
- **Choosing between options (lightweight):** `choose` compares the options for one decision (e.g. Saturday afternoon, or where to stay in one town) on fit to the time available, estimated cost for the party, suitability for the party's ages, and the user's interest or `priority`. It records the choice and a short **"what this rules out"** note on the trip page's Decisions section, naming what the time and money spent on the winner forecloses (on a trip, time is usually the scarcer resource). **Escalation:** when Opportunity Cost / Options Comparison is also active, a big one-off decision (which destination, fly vs. drive, rental car vs. trains) can be handed to `compare-options` instead, with the trip's cost estimates as economic criteria. Offered, never required.
- **Tags:** `#type/trip`, `#type/place`, `#type/trip-task`, `#type/leg`, `#type/stay`, `#type/activity`, `#type/trip-day`, `#type/packing-list`, `#type/travel-profile`, `#type/prep-timeline`.
- **Operations:**
  - `Operation: plan-trip <idea | trip>`: create or continue a trip. Creates the trip folder, trip page and Travel Board card. Asks about dates (and how flexible), origin, the party (adults, children and ages, plus the international questions when they apply), budget (optional), pace, interests and mode; then asks whether the trip needs its own task board or a checklist will do (with context, see Trip size) and which itinerary form to use. Seeds planning tasks (research destinations, routes between stops, a stay per overnight location, activities) and dated prep tasks from the Prep timeline, drafts a route and day outline, offers `pack`, and offers to move the card from Idea to Researching or Planning.
  - `Operation: scout <place | criteria>`: research a destination, or find destinations matching criteria (e.g. "4-day trip within 6 hours' drive, good for a 7-year-old, in November"). Creates or updates Place pages with highlights, best seasons, getting there, typical costs and things to know, each with sources and a checked date. For a place in another country, also builds or refreshes that country's check. With criteria, returns a shortlist; when run for a trip, links the results to it.
  - `Operation: find-routes <trip> <from> <to> [date]`: compare ways to get between two places (drive, fly, train, bus, ferry): time door to door, estimated cost for the party, and tradeoffs. Records each as a Leg with `status: option`. For long drives, proposes how to split them against the daily driving limit, with stops.
  - `Operation: choose <trip> <decision>`: the lightweight comparison above. Sets the winner to `chosen` and the others to `dropped` (kept, so the decision can be revisited).
  - `Operation: add-booking <trip> <confirmation>`: turn a pasted confirmation (email text, PDF or screenshot) into a booked Leg, Stay or Activity, or update an existing `chosen` one: times and time zones, cost, `booking-ref`, `cancel-by`, `pay-by`, and rental terms. Fields the confirmation doesn't state are asked for or left blank, never guessed. Rebuilds the itinerary.
  - `Operation: add-expense <trip> <amount> <what>`: add a line to the trip's Spending table (date, category, amount, note), updating `actual-total`.
  - `Operation: build-itinerary <trip>`: rebuild the itinerary in its chosen form from the trip's items. Run automatically by `add-booking` and `choose`; can be run directly after hand edits.
  - `Operation: pack <trip>`: build or refresh the trip's packing list from the master list (see Packing).
  - `Operation: check-trip <trip>`: find gaps and risks: nights with no stay, days that don't connect, overlapping items, drive days over the daily limit or without planned stops, items failing a party member's age or height minimum, stays whose occupancy doesn't fit, missing car seats or cribs, overdue prep tasks, upcoming `cancel-by` / `pay-by` dates, estimates older than about 90 days on unbooked items, estimated total (with buffer) vs. budget, and an unpacked list close to departure. For international trips, it tests each traveler against every country check: passport validity by the destination's rule, travel authorizations (transit included), minors' consent, medications, vaccines, and, for drivers, licence and permit, driving age and the rental's age terms; country checks older than about 30 days, or with no official source, are flagged to re-check. Reports findings and offers fixes; changes nothing on its own.
  - `Operation: trip-brief <trip>`: write the final itinerary and trip details to `<trip> Brief.md` in the trip folder: party, itinerary, every booking with its reference, times and address, cancel-by dates, key contacts, and for international trips the emergency number and embassy contact for each country. Rewritten on each run, with the date it was built. Readable offline; packaging it for sharing (e.g. PDF) is not part of this version.
  - `Operation: log-trip <trip>` (optional): after the trip, take in what the user provides (notes, a pasted journal, receipts, photos' captions), saving the user's own notes as a `Raw/` source (`source-type: trip-notes`), then ask a few follow-up questions: highlights, what to skip or repeat, how each place and stay was, how the party (especially kids) found it, and actual spending. Writes a Trip log section on the trip page, sets `actual-cost` where known, and updates each Place's `visited`, `rating` and visit notes, so the next trip benefits.
- **Trip status and completion:** the Travel Board column and the trip's `status` move together, and only with the user's confirmation. Claude suggests moves when the facts support them: to `Booked` once every overnight has a booked stay and every leg is booked, to `Underway` on `start-date`, to `Done` after `end-date`. **When a trip has ended** (noticed by any travel operation, `review`, `plan-day` or the dashboard), Claude offers once to move it to Done and, separately, offers `log-trip`. **Logging is never required to reach Done.** A declined offer sets `log: declined` and isn't repeated; the user can still run `log-trip` any time.
- **Volatile facts:** prices, hours, availability, seasonal closures and country rules always carry a `checked` date and a source (country rules also carry the source's own updated date). `check-trip` flags old ones. Approximate distances and drive times are marked as estimates; suggested driving limits are marked as rules of thumb.
- **Deadline hook:** trip `start-date`, prep-task and task-page `due` dates, dated checklist items on trip pages, item `cancel-by` and `pay-by` dates, and passport or travel-authorization expiry that fails a planned trip's country rule feed both core `Operation: review`'s deadline sweep and `Operation: plan-day`'s morning synthesis. Ended trips not yet moved to Done feed them too, as the completion prompt above.
- **Dashboard contribution:** upcoming trips (next 90 days) with status and days until departure; deadlines in the next 14 days (prep tasks, cancel-by, pay-by, task due dates); overdue prep tasks; trips with gaps (nights with no stay), counted from Stay coverage; ended trips awaiting Done or a log offer. Bases/Dataview queries over `Travel/**`, since the core needs-attention widget only covers `Projects/**`.
- **Output template:** trip brief skeleton (trip, dates, party; day-by-day itinerary; bookings table with references and cancel-by dates; addresses and contacts; emergency numbers and embassies for international trips; packing or prep notes) that `trip-brief` fills as `<trip> Brief.md` in the trip folder.
- **Archive behavior:** archiving a trip moves its whole trip folder (brief and packing list included) and any `log-trip` Raw notes. Its Travel Board card is marked `*(archived)*` like any retained page's link. **Place pages, country checks included, are never archived with a trip**, since they're shared across trips; their `visited` links to the trip get the usual archived marker. The Travel Profile, Prep Timeline and master Packing List are never archived. A trip can only be archived from `Done` or `Cancelled`; archiving one in any other column is refused with a note to move it first.
- **Boundaries addition:**
  - Never books, pays, cancels or contacts a provider; only records what the user reports having done.
  - Never invents booking details (references, times, prices, addresses); missing fields are asked for or left blank.
  - Never moves a trip card or changes a trip's `status` without the user's confirmation.
  - Never stores passport, licence, visa or other ID numbers, or medication details; only document types, countries and dates, and a yes/no for medication.
  - Never drops a cancelled booking; it's kept with its refund or credit.
  - Never presents a researched price, hour or rule without its checked date, an approximate distance or duration as exact, or a suggested driving limit as a rule.
  - Never states a country rule from memory: each comes from a source checked for this trip, or it's flagged as unchecked for the user to confirm. Country checks are information, not legal advice; the destination government is the final authority.
  - Doesn't split costs between people or track who paid; done on request only.
  - `log-trip` is offered, never required; a declined offer isn't repeated.
- **Independence:** everything a trip produces, its brief and packing list included, lives in its own trip folder; the Travel Board and per-trip boards are separate from core `Projects/` boards and from every other module's board.
- **Recommended plugins:** Kanban (Travel Board and per-trip boards), Tasks (dated checklist items and task due dates, for the Deadline hook), Bases/Dataview (dashboard queries, cost totals, Place lists by `place-kind`, `want-level` and `best-seasons`), Map View (optional: plots Place pages that have a `location` field). The required set is kept short on purpose: plugin-heavy travel setups mostly fail at setup.
- **Recommended integration:** a maps or routing tool (e.g. a maps MCP server), if one is available to the agent, makes `find-routes` and drive-day splitting accurate instead of approximate. Optional; everything works from web research without it.
