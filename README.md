# folkways command

The brain repo for building [folkways](https://github.com/sumsolution/folkways) with folkways.
New to the repo? Until `@folkways/cli` 0.1.0 is on npm, put the CLI and hook tarballs in `vendor/`
(built with `scripts/pack.ts` in the `folkways` repo), then `pnpm install` (not `--frozen-lockfile`:
rebuilt tarballs change their hashes), open Claude Code or Copilot CLI here, and run the `onboard` skill.

| Path | Holds | Changes by |
|---|---|---|
| `folkways.yaml` | Team config | PR |
| `knowledge/` | Durable facts, each with `Last verified:` | PR |
| `state/` | Live trackers, one file per track | direct push |
| `efforts/<KEY>-<slug>/` | Shared efforts, each with `00-STATUS.md` | direct push |
| `overlays/<skill>/` | Team changes to framework skills | PR |
| `people/<handle>/` | Inbox, work | direct push |
| `.claude/skills/` | Framework skills (synced) and team skills | PR |
| `.folkways/` | Framework files. Don't edit; `folkways sync` replaces them | PR |
| `.local/` | Machine-local config (`me.yaml`). Not committed | — |

Direct pushes are rebased and linear. Upgrade the framework with `npx folkways upgrade <version>` (or
`pnpm exec folkways upgrade <version>`), then open a PR. Reinstall after pulling an upgrade.
