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

## Revision 2 / catalog 2.1.0

The v2 manifest now points to `v2/packs/catalog-2.1.0.json`: 126 playable challenges in 17 rooms, plus the unchanged 43 practice records (169 total). Six new 20×20 records in The Wandering Room use clearly asymmetric original compositions and solve by line deduction in at least three rounds. All previous stage IDs and artwork are unchanged. Older snapshot filenames remain immutable.

## Edition-aware feed: v3 / catalog 2.2.0

Clients 0.11.x use `v3/manifest.json` and `v3/packs/catalog-2.2.0.json`. The JSON data schema is still 2. This revision replaces 78 nearly symmetric challenge compositions with independently deducible asymmetric editions, retaining 42 existing asymmetric compositions and the six Wandering Room records. Normal play remains 126 challenges.

New IDs link back with `replaces`. Every prior ID and its art remains byte-for-byte unchanged in the 247-record snapshot. A 0.11 client can resume saved older editions from In progress and Collection. Keep root and v2 manifests unchanged for older clients whose UI does not support earlier-edition browsing.


## Natural compositions: v4 / catalog 2.3.0

Clients 0.12+ use `v4/manifest.json` and `v4/packs/catalog-2.3.0.json` (schema 2, revision 4). All original 120 slots were reviewed for readability. 86 current slots receive a new immutable edition: excessive rotations/shears are replaced with upright original silhouettes, recognizable side views and small subject-specific details. No minimum asymmetry score applies; symmetry is allowed when it suits the subject.

The original 120 active slots now contain 195 zero row/column clues instead of 268. Each axis has at most 20% empty lines. Every active puzzle solves by line deduction in at least three rounds. Normal selection still has 126 challenges in 17 rooms, including 43 at 30×30.

All 247 previously published IDs and images remain unchanged in this 333-stage snapshot. Clients follow `replaces` chains so saves and collection entries from either earlier edition remain accessible. Root, v2 and v3 feeds are intentionally unchanged for earlier clients.
