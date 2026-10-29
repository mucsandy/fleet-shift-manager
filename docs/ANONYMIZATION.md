# Publication review

[← Project](../README.md) · [Validation](VALIDATION.md)

The public artifact is derived from the separate English session demo, not from an operational app export. All people, registrations, reports and roster contacts in its source are fictional. Contact addresses use `example.invalid`.

## Checks performed

- The live authoring session reported zero business data sources and zero APIs before export.
- The archive's connection references are empty. The three remaining data-source schemas are built-in static Studio samples.
- Source and archive text were checked against a private deny list of operational identifiers. No matches remain. That deny list is not published.
- All nine exported source files and all effective runtime rules are byte-for-byte or structurally identical to the original English demo export.
- Embedded images retain their original bytes: a neutral globe icon and an artificial bumper photograph with a visible AI-generated demo label. No operational damage photos are included.
- Existing screenshot/GIF assets were visually reviewed as fictional demo captures and artwork.

## Metadata cleaned in the public copy

Three archive entries changed: `Properties.json`, `Controls/1.json` and `References/Resources.json`.

1. The originating cloud file identifier was replaced with a neutral new GUID.
2. Two disabled authoring-cache strings were refreshed from their effective English `OnStart` and `StartScreen` rules, removing stale references from an earlier app version.
3. A temporary signed media-origin address was cleared from the embedded local image resource. Its archive path, file and bytes are preserved.

No effective formula, control layout, source file or image was changed during this cleanup. See the artifact checksum in [`app/release-manifest.json`](../app/release-manifest.json).

These checks reduce publication risk; they are not a general security certification. The sanitized file passed a separate Studio import and core preview smoke test in the source environment. Another tenant/environment and physical devices remain untested. Original private exports, tenant identifiers, connection-bearing templates and private review helpers are excluded from the public repository.
