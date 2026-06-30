# Git Zsh Aliases (Oh My Zsh)

Nguồn: Oh My Zsh plugin `git` (`plugins=(git)` trong `~/.zshrc`).

Xem alias đang active:
```bash
alias | grep "^g" | sort
```

> **Lưu ý:** Script custom trong `~/Documents/scripts/git/` (`commit`, `stash`, `gitlog`, `push`...) là executable trong PATH, **không phải alias**. Chỉ `glog` trùng tên với alias Oh My Zsh — dùng `gitlog` cho script custom.

---

## General

| Alias | Command |
|-------|---------|
| `g` | `git` |
| `grt` | `cd "$(git rev-parse --show-toplevel \|\| echo .)"` |
| `ghh` | `git help` |
| `gcf` | `git config --list` |

## Add

| Alias | Command |
|-------|---------|
| `ga` | `git add` |
| `gaa` | `git add --all` |
| `gapa` | `git add --patch` |
| `gau` | `git add --update` |
| `gav` | `git add --verbose` |

## Apply / Patch

| Alias | Command |
|-------|---------|
| `gap` | `git apply` |
| `gapt` | `git apply --3way` |

## Am (apply mailbox)

| Alias | Command |
|-------|---------|
| `gam` | `git am` |
| `gama` | `git am --abort` |
| `gamc` | `git am --continue` |
| `gams` | `git am --skip` |
| `gamscp` | `git am --show-current-patch` |

## Bisect

| Alias | Command |
|-------|---------|
| `gbs` | `git bisect` |
| `gbsb` | `git bisect bad` |
| `gbsg` | `git bisect good` |
| `gbsn` | `git bisect new` |
| `gbso` | `git bisect old` |
| `gbsr` | `git bisect reset` |
| `gbss` | `git bisect start` |

## Blame

| Alias | Command |
|-------|---------|
| `gbl` | `git blame -w` |

## Branch

| Alias | Command |
|-------|---------|
| `gb` | `git branch` |
| `gba` | `git branch --all` |
| `gbd` | `git branch --delete` |
| `gbD` | `git branch --delete --force` |
| `gbm` | `git branch --move` |
| `gbnm` | `git branch --no-merged` |
| `gbr` | `git branch --remote` |
| `ggsup` | `git branch --set-upstream-to=origin/$(git_current_branch)` |
| `gbg` | `LANG=C git branch -vv \| grep ": gone\]"` |
| `gbgd` | xóa (safe) các branch gone trên remote |
| `gbgD` | xóa (force) các branch gone trên remote |

## Checkout / Switch

| Alias | Command |
|-------|---------|
| `gco` | `git checkout` |
| `gcor` | `git checkout --recurse-submodules` |
| `gcb` | `git checkout -b` |
| `gcB` | `git checkout -B` |
| `gcd` | `git checkout $(git_develop_branch)` |
| `gcm` | `git checkout $(git_main_branch)` |
| `gsw` | `git switch` |
| `gswc` | `git switch --create` |
| `gswd` | `git switch $(git_develop_branch)` |
| `gswm` | `git switch $(git_main_branch)` |

## Cherry-pick

| Alias | Command |
|-------|---------|
| `gcp` | `git cherry-pick` |
| `gcpa` | `git cherry-pick --abort` |
| `gcpc` | `git cherry-pick --continue` |

## Clean / Clone

| Alias | Command |
|-------|---------|
| `gclean` | `git clean --interactive -d` |
| `gcl` | `git clone --recurse-submodules` |
| `gclf` | `git clone --recursive --shallow-submodules --filter=blob:none --also-filter-submodules` |

## Commit

| Alias | Command |
|-------|---------|
| `gc` | `git commit --verbose` |
| `gca` | `git commit --verbose --all` |
| `gcam` | `git commit --all --message` |
| `gcas` | `git commit --all --signoff` |
| `gcasm` | `git commit --all --signoff --message` |
| `gcmsg` | `git commit --message` |
| `gcsm` | `git commit --signoff --message` |
| `gcs` | `git commit --gpg-sign` |
| `gcss` | `git commit --gpg-sign --signoff` |
| `gcssm` | `git commit --gpg-sign --signoff --message` |
| `gcfu` | `git commit --fixup` |
| `gcn` | `git commit --verbose --no-edit` |
| `gc!` | `git commit --verbose --amend` |
| `gca!` | `git commit --verbose --all --amend` |
| `gcan!` | `git commit --verbose --all --no-edit --amend` |
| `gcans!` | `git commit --verbose --all --signoff --no-edit --amend` |
| `gcann!` | `git commit --verbose --all --date=now --no-edit --amend` |
| `gcn!` | `git commit --verbose --no-edit --amend` |
| `gwip` | WIP commit tự động (`--wip-- [skip ci]`) |
| `gunwip` | undo WIP commit gần nhất |

## Describe / Count

| Alias | Command |
|-------|---------|
| `gdct` | `git describe --tags $(git rev-list --tags --max-count=1)` |
| `gcount` | `git shortlog --summary --numbered` |

## Diff

| Alias | Command |
|-------|---------|
| `gd` | `git diff` |
| `gdca` | `git diff --cached` |
| `gds` | `git diff --staged` |
| `gdw` | `git diff --word-diff` |
| `gdcw` | `git diff --cached --word-diff` |
| `gdup` | `git diff @{upstream}` |
| `gdt` | `git diff-tree --no-commit-id --name-only -r` |

## Fetch

| Alias | Command |
|-------|---------|
| `gf` | `git fetch` |
| `gfa` | `git fetch --all --tags --prune --jobs=10` |
| `gfo` | `git fetch origin` |

## GUI / Gitk

| Alias | Command |
|-------|---------|
| `gg` | `git gui citool` |
| `gga` | `git gui citool --amend` |
| `gk` | `\gitk --all --branches &!` |
| `gke` | `\gitk --all $(git log --walk-reflogs --pretty=%h) &!` |

## Log / Reflog

| Alias | Command |
|-------|---------|
| **`glog`** | **`git log --oneline --decorate --graph`** |
| `gloga` | `git log --oneline --decorate --graph --all` |
| `glo` | `git log --oneline --decorate` |
| `glgg` | `git log --graph` |
| `glgga` | `git log --graph --decorate --all` |
| `glgm` | `git log --graph --max-count=10` |
| `glg` | `git log --stat` |
| `glgp` | `git log --stat --patch` |
| `glol` | graph + pretty format (relative date) |
| `glola` | glol + `--all` |
| `glols` | glol + `--stat` |
| `glod` | graph + pretty format (absolute date) |
| `glods` | glod + `--date=short` |
| `glp` | `_git_log_prettily` (custom pretty) |
| `grf` | `git reflog` |
| `gwch` | `git log --patch --abbrev-commit --pretty=medium --raw` |

## Pull

| Alias | Command |
|-------|---------|
| `gl` | `git pull` |
| `gpr` | `git pull --rebase` |
| `gprv` | `git pull --rebase -v` |
| `gpra` | `git pull --rebase --autostash` |
| `gprav` | `git pull --rebase --autostash -v` |
| `gprom` | `git pull --rebase origin $(git_main_branch)` |
| `gpromi` | `git pull --rebase=interactive origin $(git_main_branch)` |
| `gprum` | `git pull --rebase upstream $(git_main_branch)` |
| `gprumi` | `git pull --rebase=interactive upstream $(git_main_branch)` |
| `ggpull` | `git pull origin "$(git_current_branch)"` |
| `ggpur` | `ggu` (pull --rebase upstream current branch) |
| `gluc` | `git pull upstream $(git_current_branch)` |
| `glum` | `git pull upstream $(git_main_branch)` |

## Push

| Alias | Command |
|-------|---------|
| `gp` | `git push` |
| `gpd` | `git push --dry-run` |
| `gpv` | `git push --verbose` |
| `gpf` | `git push --force-with-lease --force-if-includes` |
| `gpf!` | `git push --force` |
| `gpsup` | `git push --set-upstream origin $(git_current_branch)` |
| `gpsupf` | push -u + force-with-lease |
| `ggpush` | `git push origin "$(git_current_branch)"` |
| `gpu` | `git push upstream` |
| `gpoat` | `git push origin --all && git push origin --tags` |
| `gpod` | `git push origin --delete` |

## Merge

| Alias | Command |
|-------|---------|
| `gm` | `git merge` |
| `gma` | `git merge --abort` |
| `gmc` | `git merge --continue` |
| `gms` | `git merge --squash` |
| `gmff` | `git merge --ff-only` |
| `gmom` | `git merge origin/$(git_main_branch)` |
| `gmum` | `git merge upstream/$(git_main_branch)` |
| `gmtl` | `git mergetool --no-prompt` |
| `gmtlvim` | `git mergetool --no-prompt --tool=vimdiff` |

## Rebase

| Alias | Command |
|-------|---------|
| `grb` | `git rebase` |
| `grba` | `git rebase --abort` |
| `grbc` | `git rebase --continue` |
| `grbi` | `git rebase --interactive` |
| `grbo` | `git rebase --onto` |
| `grbs` | `git rebase --skip` |
| `grbd` | `git rebase $(git_develop_branch)` |
| `grbm` | `git rebase $(git_main_branch)` |
| `grbom` | `git rebase origin/$(git_main_branch)` |
| `grbum` | `git rebase upstream/$(git_main_branch)` |

## Remote

| Alias | Command |
|-------|---------|
| `gr` | `git remote` |
| `grv` | `git remote --verbose` |
| `gra` | `git remote add` |
| `grrm` | `git remote remove` |
| `grmv` | `git remote rename` |
| `grset` | `git remote set-url` |
| `grup` | `git remote update` |

## Reset / Restore / Revert / Rm

| Alias | Command |
|-------|---------|
| `grh` | `git reset` |
| `gru` | `git reset --` |
| `grhh` | `git reset --hard` |
| `grhk` | `git reset --keep` |
| `grhs` | `git reset --soft` |
| `groh` | `git reset origin/$(git_current_branch) --hard` |
| `gpristine` | `git reset --hard && git clean --force -dfx` |
| `gwipe` | `git reset --hard && git clean --force -df` |
| `grs` | `git restore` |
| `grss` | `git restore --source` |
| `grst` | `git restore --staged` |
| `grev` | `git revert` |
| `greva` | `git revert --abort` |
| `grevc` | `git revert --continue` |
| `grm` | `git rm` |
| `grmc` | `git rm --cached` |

## Show / Status

| Alias | Command |
|-------|---------|
| `gsh` | `git show` |
| `gsps` | `git show --pretty=short --show-signature` |
| `gst` | `git status` |
| `gss` | `git status --short` |
| `gsb` | `git status --short --branch` |

## Stash

| Alias | Command |
|-------|---------|
| `gsta` | `git stash push` |
| `gstaa` | `git stash apply` |
| `gstp` | `git stash pop` |
| `gstd` | `git stash drop` |
| `gstl` | `git stash list` |
| `gstc` | `git stash clear` |
| `gsts` | `git stash show --patch` |
| `gstall` | `git stash --all` |
| `gstu` | `gsta --include-untracked` |

## Submodule

| Alias | Command |
|-------|---------|
| `gsi` | `git submodule init` |
| `gsu` | `git submodule update` |

## SVN

| Alias | Command |
|-------|---------|
| `gsd` | `git svn dcommit` |
| `gsr` | `git svn rebase` |
| `git-svn-dcommit-push` | dcommit + push github |

## Tag

| Alias | Command |
|-------|---------|
| `gta` | `git tag --annotate` |
| `gts` | `git tag --sign` |
| `gtv` | `git tag \| sort -V` |
| `gtl` | list tags theo pattern |

## Ignore / Files

| Alias | Command |
|-------|---------|
| `gignore` | `git update-index --assume-unchanged` |
| `gunignore` | `git update-index --no-assume-unchanged` |
| `gignored` | `git ls-files -v \| grep "^[[:lower:]]"` |
| `gfg` | `git ls-files \| grep` |

## Worktree

| Alias | Command |
|-------|---------|
| `gwt` | `git worktree` |
| `gwta` | `git worktree add` |
| `gwtls` | `git worktree list` |
| `gwtmv` | `git worktree move` |
| `gwtrm` | `git worktree remove` |
