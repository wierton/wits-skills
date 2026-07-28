---
name: gitcode
description: Operate GitCode through the bundled CLI. Use for GitCode PRs, issues, comments, labels, merges, releases, repositories, templates, commits, links, or token setup.
---

# GitCode

Run:

```bash
python3 scripts/power-gitcode.py <command> [args]
```

Use `--help` or `<command> --help` to discover commands and exact flags.

Authenticate with `gitcode_password` or `gitcode_token`. Create a token at:

```text
GitCode → 设置 → 安全设置 → 私人令牌
```

Never print a token. Validate it with `get_user`.

For PR or issue URLs, pass the path components separately:

```bash
python3 scripts/power-gitcode.py get_pr --owner <owner> --repo <repo> --number <n>
```

Confirm user intent before mutations and report returned URLs.
