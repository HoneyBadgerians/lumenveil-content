# Lumenveil content delivery

Public JSON delivery for Lumenveil. Application code remains in its separate private repository.

- `manifest.json`: catalog revision, HTTPS pack URL and SHA-256 checksum.
- `packs/catalog-1.2.0.json`: initial catalog of 120 original nonogram stages in 12 rooms.

The app checks the manifest at launch, verifies the downloaded pack, caches it on device and keeps working offline. Publishing a compatible data pack does not require an app-store update.

For future releases, keep existing stage IDs and artwork unchanged. Add new IDs, increment the revision, upload the immutable pack first, then update the manifest and checksum. Never overwrite an older pack filename with different content. Schema version 1 supports 5×5, 10×10, 15×15 and 20×20 binary art and the existing difficulty and subject categories. New gameplay mechanics require an app update.

The private app repository includes export and validation scripts. All stages in this release are fully solvable with line deduction, without guessing.

## Current app: schema 2

`v2/manifest.json` points to `v2/packs/catalog-2.0.0.json`. This feed adds 30×30 art and the Master tier, with 120 regular challenges in 16 rooms, including 43 new 30×30 puzzles. The snapshot also preserves 43 old quick records marked `practice` for existing saves. All 163 records pass logical deduction checks; regular challenges require at least three deduction rounds and a grid of at least 10×10.

Keep the original root schema-1 manifest and packs unchanged for older apps. Publish future schema-2 snapshots under `v2/packs/`, increment the v2 revision, and update only the v2 manifest. The private application adds card animations and an interactive tutorial; these features require an app update.
