# silentorb-cursor

Rules-only [Cursor plugin](https://cursor.com/docs/plugins) for shared agent guidance across Silent Orb projects.

This package ships **rules** only (no skills, MCP servers, hooks, or commands).

## Rules

| Rule | Purpose |
| --- | --- |
| `plan-commit-workflow` | Language-agnostic plan commit strategy, full-suite verification gate, and deferred commit until the user asks |

Version bump / preview-bump workflows stay in each consuming project’s `.cursor/rules` (they can reference this commit workflow).

## Enable locally

### silentorb-workbench (Dev Container)

When this repo is mounted as `.mnt/silentorb-cursor`, the workbench installs a **copy** into the container’s Cursor local-plugins directory on start/attach:

`~/.cursor/plugins/local/silentorb-cursor`

That path is what remote/Dev Container sessions load. A copy under the Windows host `%USERPROFILE%\.cursor\plugins\local` does **not** replace it while you are attached to the container.

After attach (or after running `bash scripts/install-silentorb-cursor-plugin.sh` from the workbench), reload the window if needed, then check **Customize → Plugins** for **silentorb-cursor**.

### Other environments

Copy this repo into the Cursor profile that matches how you opened the window (local vs remote):

```bash
mkdir -p ~/.cursor/plugins/local
rm -rf ~/.cursor/plugins/local/silentorb-cursor
cp -R /path/to/silentorb-cursor ~/.cursor/plugins/local/silentorb-cursor
```

Prefer a real copy over a symlink to a path outside `plugins/local` — Cursor often skips those. Reload the window afterward.

## License

MIT — see [LICENSE](./LICENSE).
