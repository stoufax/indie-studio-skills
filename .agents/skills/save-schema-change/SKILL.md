---
name: save-schema-change
description: Add or change game save data, settings, or progression data without losing existing player data - explicit schema versioning, migration, missing and corrupt save handling, and round-trip tests. Use when implementing save/load, changing a save format or settings file, or adding progression fields.
metadata:
  pack: studio-crew
  version: "1.0"
---

# Save schema change

Player data written by an older build must still load, or fail safely, in the new one.

## Steps

1. **Inspect** the current save format, location, serialization, and any version field, using the project's existing conventions.
2. **Write the change down** in your report before coding: old schema, new schema, version number, and migration rule for each changed field, including defaults for new fields.
3. **Implement migration** from every version still in the wild. If there is no version field yet, add one and treat unversioned saves as version 0.
4. **Handle failure paths:**
   - missing save: start fresh without error;
   - corrupt or unreadable save: keep the original file, report it, start safely;
   - interrupted write: write to a temporary file, then replace;
   - repeated initialization and restart.
5. **Test** with the project's tooling when it supports it: save-load round trip, migration from each old version, corrupt input, missing file.
6. **Report** changed files, the schema and interface change, test commands and results, unverified platform storage behavior, and integration notes for the lead.

## Rules

- The save schema is a shared file with one owner; coordinate through the lead.
- Never delete or overwrite a player's save as part of a failed load.
- Do not add accounts, cloud saves, backends, analytics, or third-party SDKs unless the task authorizes them. Never embed credentials.
- A mock storage layer is not proof of device behavior; list device checks as not run.
