# External Contribution Process

### Identify Maintainers Before Soliciting Approval
**Source**: BLD-263 — OpenCode PR #22079 reviewer engagement
**Date**: 2026-04-18
**Context**: After fixing a rendering bug reported by KnutZuidema on PR #22079, alankyshum asked KnutZuidema how to get the PR approved. KnutZuidema responded that he is not a maintainer and cannot approve. This required identifying and tagging the actual maintainer separately, adding delay to the merge cycle.
**Learning**: External contributors and reviewers who comment on PRs are not necessarily maintainers with merge authority. A contributor with "CONTRIBUTOR" association can review and report bugs but cannot approve or merge. Maintainer status must be verified before requesting approval actions.
**Action**: Before asking a reviewer for approval guidance on external PRs, check their association level (maintainer vs. contributor) via the GitHub API or repo settings. Direct approval requests to confirmed maintainers only. When submitting to external repos, identify maintainers from CODEOWNERS, recent merge history, or the repo's contributor guidelines early in the PR lifecycle.
**Tags**: open-source, pr-workflow, maintainers, contributors, external-repos, cross-project

### Reimplement Stale PRs From Scratch Against Current Branch
**Source**: BLD-263 — OpenCode PR #22079 reimplementing #13704
**Date**: 2026-04-18
**Context**: PR #22079 reimplemented the markdown preview feature originally proposed in PR #13704 by @kimi-chen. The original PR became unmergeable due to significant codebase refactoring in OpenCode's `dev` branch.
**Learning**: When an external codebase has undergone significant refactoring, attempting to rebase an old PR is often harder and more error-prone than reimplementing the feature from scratch against the current branch. A clean reimplementation avoids merge conflict chains and ensures the code follows current patterns.
**Action**: When picking up a stale external PR (>2 months old or with significant upstream changes), start by checking how much the target codebase has changed. If core modules have been refactored, implement from scratch against the current default branch rather than attempting to rebase the old PR. Reference the old PR for design intent but write new code.
**Tags**: open-source, pr-workflow, rebase, stale-prs, reimplementation, cross-project
