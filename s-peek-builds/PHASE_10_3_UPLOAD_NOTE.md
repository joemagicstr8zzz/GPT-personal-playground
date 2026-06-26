# S-Peek Phase 10.3 Upload Note

This folder is reserved for the S-Peek Phase 10.3 doodle persistence fix build.

The patched archive created in ChatGPT was:

```text
s-peek-phase10-3-doodle-persistence-fix.zip
```

Included changes:

- Replaced built-in doodles now behave as the active saved versions.
- Normal Restore Original doodle flow was removed/hidden.
- Built-in doodles are treated as starter templates.
- Settings cleanup from Phase 10.2 remains included.
- Two-way Inject connection cleanup from Phase 10.2 remains included.
- Version bumped to `versionCode = 12` and `versionName = "1.11"`.

Important note: the ChatGPT GitHub connector's simple file upload path only supports UTF-8 text files. The actual `.zip` binary needs to be uploaded through GitHub's normal web interface, GitHub Desktop, Git CLI, or a binary-capable GitHub upload path.
