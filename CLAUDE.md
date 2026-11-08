# lesha-io

Public website (lesha.io) — landing pages and client download links (Android feed, Windows installer).

## Critical rules

- **Everything here is outward-facing on merge** — a pushed change is live user-visible content; double-check download links and version references against the actual release feeds before pushing.
- **Changes ship as pull requests** — unless the user explicitly asks for a direct push, commit on a branch, push it and open a PR against `main` without asking, with a high-level description (what and why, the plan doc it delivers, how it was verified); don't merge it yourself. Merging to `main` deploys to production. **Pre-PR review:** substantive diffs get a fresh-context review (`/code-review` medium) first. Full rule and PR template: [terrabond/.llm/pull-requests.md](../terrabond/.llm/pull-requests.md).
- **Bugs and features go in the fleet tracker** — file them as GitHub issues in [`lexakalex/terrabond`](https://github.com/lexakalex/terrabond/issues), the single tracker for all fleet repos, labeled `repo:lesha-io` (+ type + priority). Not in this repo's issues, and not left as a TODO comment. Convention: [.llm/issue-tracking.md](.llm/issue-tracking.md).
