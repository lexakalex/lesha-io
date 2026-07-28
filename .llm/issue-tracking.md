# Issue tracking

**Bugs and feature requests for this repo are NOT filed here.** The whole LeSha fleet
uses a single tracker — [`lexakalex/terrabond`](https://github.com/lexakalex/terrabond/issues) —
and the repo an issue is *about* is recorded as a `repo:<name>` **label**. For this repo
that label is **`repo:lesha-io`**.

Canonical convention (why one tracker, label taxonomy, issue body shape, lifecycle):
[terrabond/.llm/issue-tracking.md](../../terrabond/.llm/issue-tracking.md) in this
workspace, or [on GitHub](https://github.com/lexakalex/terrabond/blob/main/.llm/issue-tracking.md).

## File one from here

Two fleet skills wrap this and are available from this repo (their scripts run from the
terrabond root): **`file-issue`** validates the label triple, infers scope from the git
remote, scans for duplicates, and carries the issue body template; **`list-issues`** gives
the backlog as repo × priority plus filters, view, retriage, and close.

```sh
gh issue create --repo lexakalex/terrabond \
  --title "..." --body-file /tmp/issue.md \
  --label bug --label repo:lesha-io --label p2
```

Every issue carries **one type** (`bug` | `enhancement` | `documentation`), **at least
one `repo:`** (add a second when the fix spans repos — label where the *change* lands,
not only where the symptom shows), and **one priority**:

- `p1` — correctness/availability risk in the live fleet (traffic silently wrong,
  dropped, or blackholed; or an operator being told something false)
- `p2` — real defect with a workaround or bounded blast radius, or a committed feature
- `p3` — papercut, cleanup, speculative

Add `needs-design` when the change trips the design-doc-first rule (>1 module, a public
interface, a new dependency, or a schema change).

## What's open for this repo

```sh
gh issue list --repo lexakalex/terrabond --label repo:lesha-io
```

## Where an issue is *not* the right home

The tracker holds work that is **known but not started**. Once real planning begins the
content moves into this repo's own `design-docs/` (intent) and `iterations/` (build
record), and the issue keeps only a pointer — linked both ways, with the issue URL in the
doc's `related:` front-matter. Close an issue by naming the commit and the iteration and
saying what was verified; "should be fixed now" is not a close.

Title issues as an observable fact, not a task — "a download link points at a yanked release", not "fix the exit selection".
