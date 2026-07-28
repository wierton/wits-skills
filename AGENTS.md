# Git commit messages

Commit messages should explain each commit in enough detail that a future reader can understand what changed and why without opening the diff immediately. The message does not need to list every touched file, but it should describe the functional areas changed, the motivation, and any relevant build/runtime impact.

Use a concise subject line plus a detailed body for non-trivial commits. Prefer bullets in the body when a commit covers multiple related changes.

Example:

```text
Align benchmark load order and native build wiring

- Force-load the target NAPI module before running ArkTS, Cangjie interop,
  and Cangjie NAPI benchmarks so the env-tag dispatch path is initialized
  in the expected order.
- Add the entry-module CMake configuration needed for `libbench1.so` to be
  built as part of the debug app.
- Keep the benchmark checksum behavior aligned between ArkTS and Cangjie by
  counting only the shared header fields.

Build impact: the debug app now includes the native benchmark library during
normal hvigor builds. Runtime impact: avoids dispatch failures caused by the
Cangjie hook side loading before the target NAPI module.
```

## Commit discipline

Commit each independently solved problem promptly so the failure and its fix remain traceable. Use a concise subject and a detailed body describing the behavior, motivation, and build/runtime impact. Write real newlines in commit messages. Never include literal `\n` text.
