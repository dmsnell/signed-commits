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

### Squash Merge

Squash merge is `git merge --squash` and prepares the working copy
with the results of what the merge would produce. I could not push
my squashed commit to `trunk` due to branch protection rules.

GH Squash merge is an attempt to inspect what GitHub does when it
creates a squash-and-merge commit.

### Rebase Merge

With the rebase merge we'll try and merge a single commit from an
approved branch that's behind the origin's `trunk`. We'll try a
few different approaches to push upstream.

 - `git rebase trunk && git checkout trunk && git merge branch && git push` fails
 - `git cherry-pick branch-HEAD && git push` fails

With merge-commits this isn't completely problematic, but if one
of the branch protection rules is to require a linear history
then it's not possible.

---

Looking also at merge commits vs. `HEAD` commits vs. merged commits.

---

Also need to examine commits from inside Github's editor.
Also the built-in VSCode editor…
