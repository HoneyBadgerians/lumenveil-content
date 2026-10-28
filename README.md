# Lumenveil content delivery

Public JSON delivery for Lumenveil. Application code remains in its separate private repository.

- `manifest.json`: catalog revision, HTTPS pack URL and SHA-256 checksum.
- `packs/catalog-1.2.0.json`: initial catalog of 120 original nonogram stages in 12 rooms.

The app checks the manifest at launch, verifies the downloaded pack, caches it on device and keeps working offline. Publishing a compatible data pack does not require an app-store update.

For future releases, keep existing stage IDs and artwork unchanged. Add new IDs, increment the revision, upload the immutable pack first, then update the manifest and checksum. Never overwrite an older pack filename with different content. Schema version 1 supports 5×5, 10×10, 15×15 and 20×20 binary art and the existing difficulty and subject categories. New gameplay mechanics require an app update.

The private app repository includes export and validation scripts. All stages in this release are fully solvable with line deduction, without guessing.
