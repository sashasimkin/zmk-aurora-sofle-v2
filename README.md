
## How to integrate Aurora Sofle V2 updates from main

#3 on https://stackoverflow.com/a/30386041

### Do this the first time:

```
git remote add -f -t main --no-tags zmk https://github.com/zmkfirmware/zmk.git
git checkout zmk/main
git subtree split -P app/boards/shields/splitkb_aurora_sofle -b temporary-split-branch
# Back to my main branch
git checkout main
git subtree add --squash -P boards/shields/splitkb_aurora_sofle temporary-split-branch
# cleanup
git branch -D temporary-split-branch
```

#### In future, you can merge in additional changes as follows:

```
# Maybe it's a new checkout
git remote add -f -t main --no-tags zmk https://github.com/zmkfirmware/zmk.git
git checkout zmk/main
git subtree split -P app/boards/shields/splitkb_aurora_sofle -b temporary-split-branch
# Back to my main branch
git checkout main
git subtree merge --squash -P boards/shields/splitkb_aurora_sofle temporary-split-branch
# Now fix any conflicts if you'd modified third_party/git-completion.
git branch -D temporary-split-branch
```
