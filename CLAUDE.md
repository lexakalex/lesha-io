# lesha-io

Public website (lesha.io) — landing pages and client download links (Android feed, Windows installer).

## Critical rules

- **Everything here is outward-facing on merge** — a pushed change is live user-visible content; double-check download links and version references against the actual release feeds before pushing.
- **Push and release autonomously** — once work is verified, commit and push without asking; report what changed. **Pre-push review:** substantive diffs get a fresh-context review (`/code-review` medium) first.
- **Bugs and features go in the fleet tracker** — file them as GitHub issues in [`lexakalex/terrabond`](https://github.com/lexakalex/terrabond/issues), the single tracker for all fleet repos, labeled `repo:lesha-io` (+ type + priority). Not in this repo's issues, and not left as a TODO comment. Convention: [.llm/issue-tracking.md](.llm/issue-tracking.md).
