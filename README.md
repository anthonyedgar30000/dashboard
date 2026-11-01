# dashboard

Anthony's dashboard, hosted on GitHub Pages and rendered from a single data
file (`board.json`) that sits next to the page. This repo holds **only** the
renderer and the share-curated board extract — the personal records of record
stay in the private `fulcrum-data` repo; the systems/specs live in
`muse-systems`.

## How it stays current

- Muse is responsible for updating `board.json` **every 15 minutes**: a
  scheduled sync folds the latest records (workflows, meals, latest mood
  interpretation) into `board.json` and commits — but only when the content
  actually changed, so the history stays meaningful.
- GitHub Pages republishes automatically on each commit (about a minute).
- The page itself displays the data's age and the mood read's age, computed
  live in the browser — staleness is shown, never hidden.
- In-event updates still happen in the same turn something is logged (the
  records land in `fulcrum-data` immediately); the 15-minute sync is what
  carries them onto this page.

## Rules

- Private always for the source records; this page carries only the
  share-curated extract, with weighing factors kept **name-free**.
- Anthony's stated mood is ground truth. Only Anthony moves the solid
  set-mood cursor; Muse's dashed interpretation is a labelled, timestamped
  draft that decays under the 60-minute factor rule.
- The set-mood anchor persists as ground truth; signal factors count only
  while under 60 minutes old.

## Layout

- `index.html` — the renderer (single file, no build step; fetches
  `board.json` same-origin).
- `board.json` — the board extract: set mood, latest interpretation,
  workflows, parked items, recent meals, Bunzy card.
