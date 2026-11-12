# PR #197722 proof — physical line number for malformed JSON manifest rows

`terminal-capture.log` is the raw capture; `source-manifest-line-number-proof.svg` renders it.

Fixture (`run/bad.manifest.jsonl`): two blank lines, then `{bad "PRIVATE_LEAK_MARKER_9f3c" json}` — a
malformed row on physical line 3. `PRIVATE_LEAK_MARKER_9f3c` is a synthetic canary: it must never appear
in the diagnostic, because source manifests carry private payloads (message text, author fields).

- base = `main` at `fc6c25e9` (same file blob as the PR base `4efd662`)
- head = `fix/source-manifest-row-number-392` at `58dd44207fa`
