# 2b — Second Brain

An AI agent–run Obsidian second brain. You add sources, and your agent moves them through Raw → Inbox → Wiki → Outputs as cited, interlinked notes. One portable file, `2b-init.md`, sets up each new vault for its use case.

*Written for `2b-init.md` Generator version 4.36.*

## What it is

`2b-init.md` is a generator, not a ruleset. You put it in an empty Obsidian vault and ask your AI agent to run it. The agent asks what the vault is for, then writes a tailored `2b-instructions.md` for that vault, creates the folders and starter pages, and adds small pointer files (`CLAUDE.md`, `AGENTS.md`, `.cursorrules`, `GEMINI.md`) so any agent tool finds the instructions later.

After that you choose the sources and ask the questions. The agent summarizes, cross-references, keeps the wiki consistent, and tracks work, and it cites a source for every claim. Anything it can't back with a source is marked `unverified`, and speculation stays in one folder set aside for it.

The design suits vaults of hundreds of pages, not millions. At that size the agent can read the whole index and follow links directly.

## What you need

- [Obsidian](https://obsidian.md)
- An AI agent that can read and write files in your vault folder, such as Claude Code, Codex, Cursor or Gemini CLI.
- Optional but recommended: [git](https://git-scm.com), so you can see and undo what the agent changes. Setup checks for it and offers to set up a repo.

## Get started

1. **Create an empty folder** for the new vault and open it in Obsidian as a vault.
2. **Download `2b-init.md`** from the [latest release](https://github.com/michaelbarone/2b--second-brain/releases/latest) (or the repo root) and put it in the vault's root folder.
3. **Start your agent in that folder** and tell it:

   > Read 2b-init.md in full, then run Operation: init-vault against it.

4. **Answer the interview.** The agent asks about:
   - **Purpose:** what the vault is for, in your own words.
   - **Modules:** name a recipe (see below) or describe your goal and let the agent suggest one. You confirm the list before anything is built.
   - **Naming:** whether `Outputs/` should have a more specific name, such as `Playbooks/` or `Findings/`.
   - **Tone:** how the agent should write.
   - **Digest topics:** only if you want web news scans.
5. **Install the recommended plugins.** The agent lists which are missing. It can't install plugins itself; do that in Obsidian under Settings → Community plugins → Browse. Everything still works without them, just with fewer features.
6. **Set up version control.** If the vault isn't a git repo yet, the agent recommends one and offers to create it: `git init`, a `.gitignore` for Obsidian's per-device files, and a first commit. Connecting it to GitHub or another remote is up to you. The Obsidian Git plugin can commit and push automatically.

Keep `2b-init.md` in the vault root after setup. It's the reference copy that updates and new modules are read from. It is never the vault's active ruleset.

## Update an existing vault

Tell your agent: `Run Operation: check-for-updates`.

It checks this repo's latest release against your vault's `2b-init.md`. If a newer version is out, it shows what changed and asks before downloading it. It then offers to run `update-vault` to apply the changes to your vault.

To update by hand instead, download `2b-init.md` from the [latest release](https://github.com/michaelbarone/2b--second-brain/releases/latest), replace the copy in your vault root, and tell your agent `Run Operation: update-vault`.

`update-vault` compares versions and skips anything unchanged. For each changed section it shows you the change and asks before applying it. It also adds any modules an updated module now depends on, asks how to handle content affected by the change, and suggests related modules you might want. It never overwrites anything silently.

To add a module later, run `Operation: add-use-case`.

## How a vault is organized

Every vault has these folders. Modules add their own on top.

| Folder | What goes there |
|---|---|
| `Raw/` | Original sources, never edited after they're added |
| `Inbox/` | Quick captures, digests and anything waiting for a decision |
| `Assets/` | Images, screenshots and other attachments |
| `Wiki/` | The knowledge layer the agent maintains: `Index.md`, `Log.md`, `Entities/`, `Concepts/`, `Summaries/`, and `Arguments/` for open questions and speculation |
| `Outputs/` | Finished conclusions and deliverables, every claim cited |
| `Projects/` | Kanban boards for tracking real work, one page per project |
| `Routines/` | Recurring jobs and their last-run status |
| `Ecosystem.md` | Tools, subscriptions and integrations the vault uses |
| `Dashboard.md` | Optional overview page, built with `Operation: dashboard` |
| `Archived/` | Finished topics moved out of the way, restorable |

Other conventions:
- Pages link to each other by name.
- Tags follow `#type/*`, `#status/*` and `#topic/*`.
- Dates are always absolute.
- Standard Obsidian settings and graph colors are applied for you, with your confirmation.

## Operations

Tell your agent `Run Operation: <name>`. `Operation: help` lists what's available in your vault.

**Vault setup and updates**

| Operation | What it does |
|---|---|
| `init-vault` | Run once in a new vault to set it up |
| `check-for-updates` | Download a newer `2b-init.md` release, then offer `update-vault` |
| `update-vault` | Pull in changes from a newer `2b-init.md` |
| `add-use-case` | Add a module to an existing vault |

**Everyday use**

| Operation | What it does |
|---|---|
| `help [module or recipe]` | Module and recipe menu, or the operations available in this vault |
| `config [key] [value]` | Review or change vault-wide settings, such as citation rigor |
| `ingest <url or file>` | Add a source: saved to Raw, summarized, then linked into the wiki |
| `query <question>` | Answer from the wiki, and save the answer if it's new synthesis |
| `lint` | Check the wiki for broken links, missing tags and other problems |
| `review` | Periodic review of deadlines, stalled items and tools |
| `digest` | Scan the web for news on your topics and put it in Inbox (never added automatically) |
| `check-watchlist <playlist or all>` | Check YouTube watchlists for new videos |
| `draft <Outputs page> <topic>` | Assemble cited claims into a first draft |
| `find-open-questions [scope] [focus]` | Find open, unclear or conflicting points in what's been added |
| `dashboard` | Build or refresh `Dashboard.md` |
| `plan-day` / `close-day` | Morning plan (due items plus one old item resurfaced) and evening log |
| `plan-project [board] <topic>` | Scope a project into milestones and move it to In Progress. For bigger projects it offers milestone dependencies, phases, a budget and a close-out punch list; you only get the ones you accept |
| `new-board <topic>` | Create a separate Projects board (also used to give a large project a board of its own) |
| `check-project <project>` | What's ready next, what's waiting, what's overdue, and how the budget looks |
| `close-project <project>` | Punch list, close-out note, then Done once you confirm |
| `log-cost <project> <amount> <what>` | Add a committed or paid cost to a project's budget |
| `log-work <project> <notes>` | Add a dated progress note and tick off what's done |
| `archive <topic or page>` | Move a finished topic into `Archived/` |
| `restore <archive>` | Bring an archived topic back |
| `delete <archive> [files]` | Permanently delete an archive (asks separately to confirm) |

Modules add their own operations, listed with each module below.

## Modules

Most vaults use one or two. Research and Projections are **base modules**: you never pick them directly, and they're added automatically (with your confirmation) when a module that needs them is chosen.

| Module | Use it for | Operations |
|---|---|---|
| General Wiki | A broad, growing reference with no pipeline attached | — |
| Content Production | A recurring content pipeline (video, newsletter, podcast) with sponsors or collaborators | `new-topic`, `prep-piece`, `update-sponsor`, `analyze-performance` |
| Team / Org Knowledge Base | Shared team memory, including the reasons behind decisions | `check-workflow-currency` |
| Personal CRM / Relationships | People, interactions and follow-ups | `log-interaction` |
| Meeting Transcript Ingestion | Keeping full meeting transcripts as sources, with decisions and action items pulled out | `ingest-meeting` |
| Stand-up Comedy | Writing and performing your own material: premises, versioned bits, sets, stage results | `develop-bit`, `feedback-bit`, `research-bit`, `check-prior-use`, `build-set`, `log-set`, `review-burn`, `review-material` |
| Travel Planning | Planning vacations and road trips, at home or abroad: destinations, routes, stays and activities with cost estimates, dated prep, packing, country checks for international trips, and an itinerary built from your bookings | `plan-trip`, `scout`, `find-routes`, `choose`, `add-booking`, `add-expense`, `build-itinerary`, `pack`, `check-trip`, `trip-brief`, `log-trip` |
| Physical Projects | Renovations, sheds and garages, vehicle restorations, woodworking, landscaping and moves, as ordinary projects with extras: pages for each home, vehicle or yard that outlive projects, project-type profiles, local rules researched for your area, materials and parts lists, bids, and maintenance hand-off | `add-property`, `check-local`, `weigh-options`, `add-bid`, `compare-bids`, `redate`, plus extra steps in the core project operations |

**Research modules** (each adds Research, a shared citation system and source list):

| Module | Use it for | Operations |
|---|---|---|
| Academic Paper | Papers, theses and other work that must pass a citation check | — |
| Competitive Intelligence | Tracking how competitors, products or markets change over time | `research-competitor` |
| Product Discovery / Decision-Making | Deciding what to build, from evidence | `score-idea` |
| Product Feasibility | Time-boxed investigations of whether something can be built | `run-spike` |
| Opportunity Cost / Options Comparison | Comparing options, including what each choice rules out | `compare-options` |
| Due Diligence | Checking a business, investment or acquisition before a go/no-go decision | `raise-issue`, `resolve-issue`, `build-model` |
| Investment Strategy | Building, testing and grading your own investing rules | `set-profile`, `build-policy`, `import-holdings`, `check-portfolio`, `define-rule`, `add-indicator`, `ingest-backtest`, `import-trades`, `grade-rule`, `review-rules`, `build-rulebook` |

Due Diligence, Opportunity Cost / Options Comparison and Product Discovery / Decision-Making also add **Projections**, which builds month-by-month cost and revenue forecasts (`build-projection`, `update-projection`). Every assumption is labeled by how well it's supported.

Research modules each set a **citation rigor** level: `strict` (every claim cites a source and the exact location in it), `standard` (every claim cites a source) or `light` (citations recommended). If you use several, the vault uses the strictest.

## Recipes

Recipes are common module combinations. Name one during setup, for example "set this up for academic research", or describe your goal and the agent will suggest the closest match. You can add or remove modules from any recipe.

| Recipe | Modules | Optional additions |
|---|---|---|
| General Knowledge Base | General Wiki | — |
| Academic Research | Academic Paper | — |
| Team / Org Knowledge Base + Meetings | Team / Org Knowledge Base, Meeting Transcript Ingestion | Personal CRM |
| Content Creator Operations | Content Production, Competitive Intelligence | Personal CRM |
| Competitive / Market Watch | Competitive Intelligence | — |
| Product Strategy & Roadmap Decisions | Product Discovery, Product Feasibility, Opportunity Cost | Competitive Intelligence |
| Investment / Deal Due Diligence | Due Diligence, Meeting Transcript Ingestion | Product Feasibility, Opportunity Cost, Personal CRM |
| Personal CRM / Relationship-First | Personal CRM | Meeting Transcript Ingestion |
| Comedy Writer / Performer | Stand-up Comedy | Content Production, Personal CRM |
| Investor / Trader Strategy Development | Investment Strategy | Due Diligence, Competitive Intelligence, Opportunity Cost |
| Travel Planner | Travel Planning | Opportunity Cost, Personal CRM |
| Home & Physical Projects | Physical Projects | Opportunity Cost, Personal CRM |

## Recommended plugins

- **Bases** (built into Obsidian) or **Dataview**: live filtered lists and dashboards
- **Kanban**: shows `Projects/` boards as boards
- **Tasks**: due dates, repeating items and dependencies ("blocked until") on project milestones
- **Tasks Calendar Wrapper**: calendar view of those due dates

Modules may recommend more, for example PDF++ and a web clipper for research modules. The agent gives you the full list during setup.

## Tips

- **Ingest regularly.** The wiki only grows if sources move out of `Inbox/`.
- **Use more than one vault** if you have unrelated purposes, such as a personal knowledge base and a work vault. Each vault has its own instructions, so an agent only reads the one you point it at.
- **Check the Projects board.** Anything waiting on a decision gets a card there, so nothing is lost in `Inbox/`.
- **Keep small projects small.** A project can be just a goal and a checklist. Add dependencies, phases or a budget only when the work needs them. Park a project on purpose with a resume date (`status: paused`) so reviews don't nag about it.
- **Research what's local.** Permits, local rules, prices, deposit norms and weather depend on where you are. The agent lists them as research steps for your project instead of guessing.
- **Speculation goes in `Wiki/Arguments/`.** Ideas move to `Outputs/` only once they're backed by sources.
