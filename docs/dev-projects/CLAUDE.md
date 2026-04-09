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

### Common operations

**Change status:** `status: "in-dev", statusLabel: "In development"`

**Unlock embargo:** set `embargo: false`

**Mark incorporated:** set `incorporated: "1.5"` → moves from Roadmap to Incorporated tab

**Add new DP:** append to `projects` array, next ID is DP-46+

**Tag StratiGraph:** set `stratigraph: true` — displays a dark blue "StratiGraph" tag. Filterable via toolbar button.

**Merged DPs (April 2026):**
- DP-04 now includes former DP-14 (EM Surfaces — Artù)
- DP-17 now includes former DP-22 (Triple Store Database)

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
