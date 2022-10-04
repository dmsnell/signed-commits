# Can we end up with signed commits in `trunk` if GitHub is merging PRs?

| PR merge strategy | Can we fast-forward? | Was merge signed by me? |
|-------------------|----------------------|-------------------------|
| Merge-commit      | ✅                   | 🚫                      |
| Merge-commit      | 🚫                   |                         |
| Force-merge       | ✅                   |                         |

Does it matter if GitHub has "prevent bypassing these rules" on the branch
protection? I was able to merge and push to `trunk` with a fast-forward
merge commit.

