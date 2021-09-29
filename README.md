
### Config windows
```
git config --global diff.tool meld
git config --global difftool.meld.path "C:\Program Files (x86)\Meld\Meld.exe"
git config --global difftool.prompt false

git config --global merge.tool meld
git config --global mergetool.meld.path "C:\Program Files (x86)\Meld\Meld.exe"
git config --global mergetool.prompt false
(Update the file path for Meld.exe if yours is different.)
```

### Config Linux
```
git config --global diff.tool meld
git config --global difftool.meld.path "/usr/bin/meld"
git config --global difftool.prompt false

git config --global merge.tool meld
git config --global mergetool.meld.path "/usr/bin/meld"
git config --global mergetool.prompt false
```

### Stash
```
$ git stash (Push changes on to stack)
$ git stash apply (Pop changes from stack)
```

### Squash and rebase
```
$ export EDITOR="$VISUAL"
$ export VISUAL=vim

$ git log.
* df71a27 - (HEAD feature_x) Updated CSS for new elements (4 minutes ago)
* ba9dd9a - Added new elements to page design (15 minutes ago)
* f392171 - Added new feature X (1 day ago)
* d7322aa - (origin/feature_x) Proof of concept for feature X (3 days ago)

$ git rebase -i HEAD~3
pick f392171 Added new feature X
squash ba9dd9a Added new elements to page design
squash df71a27 Updated CSS for new elements

$ git push origin <branch> -f
```

### Rebase to master
```
$ git checkout floating-pt-warn
$ git rebase origin/master
```
### Pushing upstream
```
$ git clone https://github.com/Mehul2802/pmacct.git
$ git remote add upstream https://github.com/pmacct/pmacct.git
$ git remote -v
$ git pull upstream master
$ git push origin master
```

### To view remote URL
```
$ git remote show origin
```

### git patch
```
$ git diff rev1 rev2 > patch.diff
$ git apply patch.diff
```

### Staging all removed files
```
$ git ls-files --deleted -z | xargs -0 git rm 
```

### Tagging
```
$ git tag v1.0 ec32d32
Where v1.0 is the tag name and ec32d32 is the commit you want to tag
Once done you can push the tags by:
$ git push origin --tags
```

### Change current commit message
```
git commit --amend -m "New commit message."
git push origin <branch_name> -f
```

### Merge
```
$ git checkout -b new-feature
$ git commit -m "fast forward"
$ git checkout master
$ git merge new-feature
$ git branch -d new-feature
```

### Assume Unchange files

- The way you git ignore watching/tracking a particular dir/file. you just run this:
```
$ git update-index --assume-unchanged <file>
```

- To get undo/show dir's/files that are set to assume-unchanged run this:
```
git update-index --no-assume-unchanged <file>
```


- To get a list of dir's/files that are assume-unchanged run this:
```
git ls-files -v|grep '^h'
```

### meld diff
```
git config --global diff.tool meld
```

### Bonus 😄 
```
svn diff --diff-cmd='meld'
```

### Reference
- [Rebase PR](https://github.com/edx/edx-platform/wiki/How-to-Rebase-a-Pull-Request)
- [Assume Unchange](http://stackoverflow.com/questions/17195861/undo-git-update-index-assume-unchanged-file)
- [Git Server](https://www.linux.com/learn/how-run-your-own-git-server)
