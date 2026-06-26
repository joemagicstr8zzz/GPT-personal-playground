# S-Peek Phase 10.4 Branch

Branch: `speek-phase-10-4`

This branch is for the S-Peek Phase 10.4 two-way echo guard update.

Expected archive from ChatGPT:

```text
s-peek-phase10-4-two-way-echo-guard.zip
```

Key changes in this build:

- Two-Way Mode still supports drawing recognition.
- When `Identify simple drawings with AI` is enabled, drawing then tapping Save can identify a simple doodle and send the recognized word to Inject.
- Fixed the Two-Way Mode echo loop where S-Peek sends a value to Inject, immediately reads that same value back, and generates a reveal from its own sent value.
- After S-Peek sends a value in Two-Way Mode, live polling ignores that same value until Inject changes to something different.
- Removed the old POST-then-GET fallback behavior from the send path.
- Sending and reading are now treated as separate jobs:
  - Save = send to Inject
  - Live polling = read from Inject
  - Own sent value = ignored as echo
- Version bumped to `versionCode = 13` and `versionName = "1.12"`.

Manual test:

```text
Two-Way Mode ON
AI image reveal ON
Write hello
Tap Save
Inject updates to hello
S-Peek should NOT generate hello or Hello Kitty from its own sent value
Then change Inject to dog
S-Peek should reveal dog
```

Connector limitation:

The ChatGPT GitHub connector can create branches and UTF-8 text files, but it still does not expose a reliable direct binary `.zip` upload action here. The branch exists and this note records the build details, but the actual zip should be uploaded manually if you want the binary archive stored in GitHub.
