# Can we end up with signed commits in `trunk` if GitHub is merging PRs?

| PR merge strategy | Can we fast-forward? | Was merge signed by me? |
|-------------------|----------------------|-------------------------|
| Merge-commit      | ✅                   | 🚫                      |
| Merge-commit      | 🚫                   |                         |
| Force-merge       | ✅                   |                         |
| Squash-merge      | ✅                   | 🚫                      |
| GH Squash-merge   |                      |                         |

Does it matter if GitHub has "prevent bypassing these rules" on the branch
protection? I was able to merge and push to `trunk` with a fast-forward
merge commit.

## Notes

Squash merge is `git merge --squash` and prepares the working copy
with the results of what the merge would produce. I could not push
my squashed commit to `trunk` due to branch protection rules.

GH Squash merge is an attempt to inspect what GitHub does when it
creates a squash-and-merge commit.
