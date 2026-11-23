# Changelog — AtTheFaire Stage Manager 2026

All notable changes to the 2026 web app (`stagemanager2026.html`). The same
history is kept in the app file itself, in the comment above `APP_VERSION`.
All versions below were built on November 23, 2026.

Version 1.3.2 was the first version published to GitHub as
`stagemanager2026.html`. Earlier versions lived only as local files.

## 1.5.1 — 2026-11-23

- The Export panel is a fixed overlay instead of a block in the footer —
  in the footer it opened below the fold and looked like nothing had
  happened.

## 1.5.0 — 2026-11-23

- The app opens empty, with a Load demo data button at the top of the
  Schedule view. From an empty start it loads in one click; if there is
  already data it asks first.
- Reset is now Clear all data (it used to reset to the demo lineup).
- Export always shows the data as copyable text in a panel, for when the
  file download is blocked (e.g. in a sandboxed preview).
- Acts can be sorted alphabetically (the original order) or by category,
  with acts alphabetical inside each category. One setting, with controls
  on the Schedule list and the Acts tab.

## 1.4.4 — 2026-11-23

- The header and tabs stay pinned to the top of the screen.
- The "Modern take on..." intro line is removed for now.

## 1.4.3 — 2026-11-23

- The acts column sticks while the page scrolls, and the act list scrolls
  inside itself, so the grid stays in view while picking an act further
  down the list.

## 1.4.2 — 2026-11-23

- Demo acts are 30 minutes with setup and teardown 0.

## 1.4.1 — 2026-11-23

- Slots the selected act can't use are greyed out on the grid, with the
  reason on hover — blocked slots used to look like ordinary empty cells.

## 1.4.0 — 2026-11-23

- Conflict rules: per-category cap (the 2010 conflicts number — at most
  that many acts of a type at once, default 2), performer groups (acts
  sharing a group never overlap), per-act exclusivity with an excepted
  category. The per-act conflicts field is retired.

## 1.3.2 — 2026-11-23

- Title is AtTheFaire Stage Manager 2026; "experiment" dropped from the
  visible title.

## 1.3.1 — 2026-11-23

- Batch edit confirms in place (modal dialogs can be suppressed by the
  viewer), and all stored values are type-checked on load/import.

## 1.3.0 — 2026-11-23

- Batch edit acts, and the version number shows in the header and footer.

## 1.2.0 — 2026-11-23

- Act categories own the colours (combat, music, comedy, magic/juggling,
  demo, childrens).

## 1.1.0 — 2026-11-23

- Default show 30 min (was 60).

## 1.0.0 — 2026-11-23

- First experiment: schedule grid with the v0.11 conflict rules,
  Days/Stages/Acts config screens, JSON export/import, seeded with the
  v0.11 lineup.
