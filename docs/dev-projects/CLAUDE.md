# EM Development Projects — Maintenance Guide

How to update the EM Development Projects page (`index.html`).

## Data Location

All data lives in JavaScript arrays inside `index.html`:
- `projects` — all Development Projects
- `emVersions` — EM version history with repo links

## Project Fields

```javascript
{
  id: "DP-XX",              // Unique sequential ID
  title: "Name",
  cat: "core",              // core | tool | extension | infra | research | collab
  embargo: false,           // true = hidden unless ?embargo=on in URL
  status: "planned",        // concept | planned | in-dev | partial | near | research
  statusLabel: "Planned",   // Human-readable
  desc: "Short description",
  full: "Detailed description",
  components: ["..."],      // Impacted EM components
  impacts: ["emtools"],     // Which tools affected (see below)
  targetVersion: "1.5",     // Target EM version
  incorporated: null,       // Set to "1.5" when shipped → moves to Incorporated tab
  notes: "",
  thesis: true,             // Thesis candidate flag
  stratigraph: false,       // true = funded/created within StratiGraph EU project
  keyStudy: "Needed",
  embargoNotes: ""          // Visible only in embargo mode (optional)
}
```

### Impact tags (multi-tool system)
- `emtools` — EMtools Blender add-on
- `s3d` — s3Dgraphy Python library
- `yed` — yEd palette / GraphML template (when a new node is proposed)
- `config` — s3Dgraphy JSON config files (formal rules, part of core language)
- `heriverse` — Heriverse online viewer

### Status values

`status` is an enum. Allowed values (see `statusOrder`, `statusGroupLabel`, `statusDot` in `index.html`):

| status        | statusLabel                | Meaning                                                              |
|---------------|----------------------------|----------------------------------------------------------------------|
| `done`        | `Incorporated`             | Shipped in the version set by `incorporated`. **Required when `incorporated` is set.** |
| `near`        | `Near completion`          | Feature almost done, still in Roadmap (not yet `incorporated`)        |
| `in-dev`      | `In development`           | Active work                                                          |
| `partial`     | `Partially implemented`    | Part of the scope shipped, rest open                                 |
| `planned`     | `Planned`                  | Committed for a future version, not started                          |
| `concept`     | `Concept`                  | Early idea, no design                                                |
| `research`    | `Research`                 | Research track, paper/prototype stage                                |

Keep `status` and `statusLabel` in sync. `statusLabel` is free text for the UI, but **must match the status family** (e.g. don't write `statusLabel: "Near completion"` with `status: "done"`).

### Common operations

**Change status:** update **both** fields. Example: `status: "in-dev", statusLabel: "In development"`.

**Unlock embargo:** set `embargo: false`.

**Mark incorporated:** whenever a DP ships, update **three** fields together:

```javascript
status: "done",
statusLabel: "Incorporated",
incorporated: "1.5"   // target EM version string; also keep `targetVersion` in sync if it differs
```

This moves the DP from the Roadmap tab to the Incorporated tab. Setting only `incorporated` leaves the status inconsistent (the DP would still display e.g. "Near completion" in the detail view).

**Update a released version summary:** when DPs are marked incorporated, keep the `emVersions` entry for that version up to date — list the shipped DPs explicitly and what is still open for that cycle. See the `emVersions` array, the `summary` field.

**Add new DP:** append to `projects` array; check the highest existing ID first.

**Tag StratiGraph:** set `stratigraph: true` — displays a dark blue "StratiGraph" tag. Filterable via toolbar button.

**Merge / supersede DPs:** if a DP's scope is absorbed by another, remove the obsolete entry from the array and note the merge in the surviving DP's `notes` (e.g. *"Absorbs former DP-44."*). Keep a short reference in this guide as well.

**Merged DPs (history):**
- DP-04 absorbs former DP-14 (EM Surfaces — Artù)
- DP-17 absorbs former DP-22 (Triple Store Database)
- DP-12 absorbs former DP-42 (Dashed Connector for alternative branches)
- DP-39 absorbs former DP-44 (Transformation Connector Documentation)

## EM Versions

Each version can have repo links:
```javascript
{ version: "1.6", date: "2027", status: "in-development", summary: "...",
  links: { "EMtools v1.6": "https://github.com/..." } }
```

## Embargo system

Public page: `index.html` — Developer page: `index.html?embargo=on`

## Syncing with ROADMAP.md

If a `ROADMAP.md` exists in the repo root, keep it in sync. Use checkbox format:
```markdown
## EM 1.5 (in development)
- [x] DP-10 Multigraph — near completion
- [ ] DP-03 TSU — in development
```

## Commit format
```
Update DP-XX Title: description
Unlock DP-XX Title: paper published
Add DP-XX New Title: description
```
