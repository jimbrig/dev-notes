# Git Merges - Fast Forward Only

Utilize `git merge --ff-only <target merge branch>` to *fast forward* a branch to 
another specified branch given they share the same git history lineage.

A common example of this would be the following:

1. Merge a pull-request (develop -> main) on GitHub using the `merge-commit` method
2. Fetch and pull changes locally
3. Notice that main branch is ahead of develop due to the merge-commit from step 1.
4. Checkout develop, and merge with `ff-only` main into it 
5. Push develop to `origin`

In code:

```bash
# assuming just merged pr on github frmo branch develop into branch main
git fetch

# checkout main locally
git checkout main

# pull changes
git pull

# checkout develop
git checkout develop

# fast forward develop to main and push
git merge main --ff-only
git push
```
