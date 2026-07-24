# Contextual Sketch live rollout — 2026-07-24

The combined `dist/geo-trainer-all.apkg` was imported into the daily Anki
collection through AnkiConnect after a successful sync.

## Before

- Root: `Decks::Geography::GeoTrainer`
- Notes/cards: 1,699 / 1,699
- Exact note IDs, card IDs, fields, tags, deck assignments, and scheduling were
  captured under `20260724T150455-0700-before/`.
- A scheduled rollback package was exported as
  `20260724T150455-0700-before/geotrainer-before.apkg`. APKG files are ignored by
  Git, so this remains a local backup.

## Migration

- Import added 501 new Sketch notes/cards without duplicating any prior notes.
- The 501 Sketch cards were moved from the temporary top-level `GeoTrainer`
  tree into the existing nested tree.
- The exact 541 existing Draw cards were moved from `3 Draw` to `4 Draw`.
- The temporary top-level tree and the 17 old Draw deck shells were verified
  empty before deletion.

## Verification

- Final notes/cards: 2,200 / 2,200
- Sketch: 501 notes/cards in 17 `3 Sketch` leaf decks
- Draw: 541 cards in 17 `4 Draw` leaf decks
- Top-level stray `GeoTrainer` cards/decks: 0 / 0
- Old `3 Draw` cards/decks: 0 / 0
- All 1,699 original note IDs, card IDs, fields, tags, and note-type assignments
  are unchanged.
- All scheduling fields on the 1,699 original cards are byte-for-byte
  equivalent in the normalized before/after snapshots.
- Final sync completed successfully.

The generic combined package also registered 48 unused, zero-note variants of
existing GeoTrainer note types because the live collection's historical note
types have hash-suffixed names. AnkiConnect has no supported delete-note-type
action, so these harmless empty definitions were left untouched instead of
using database edits or unapproved GUI automation. The 69 used GeoTrainer note
types account for all 2,200 notes.
