# silentorb-cursor

Rules-only [Cursor plugin](https://cursor.com/docs/plugins) for shared agent guidance across Silent Orb projects.

This package ships **rules** only (no skills, MCP servers, hooks, or commands).

## Rules

| Rule | Purpose |
| --- | --- |
| `plan-commit-workflow` | Language-agnostic plan commit strategy, full-suite verification gate, and deferred commit until the user asks |

Version bump / preview-bump workflows stay in each consuming project’s `.cursor/rules` (they can reference this commit workflow).

## Enable locally

Mounting this repo under a workbench `.mnt/` path does **not** load the plugin by itself.

On the machine that runs Cursor, link or copy this repo into the local plugins directory, then enable it in Cursor (Plugins):

```bash
mkdir -p ~/.cursor/plugins/local
ln -sfn /path/to/silentorb-cursor ~/.cursor/plugins/local/silentorb-cursor
```

Reload the window if the plugin does not appear immediately.

## License

MIT — see [LICENSE](./LICENSE).
