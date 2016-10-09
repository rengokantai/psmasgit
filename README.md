# psmasgit
##1
###The index
compare:
```
git status  //repo <->working area
git diff //working area<->index
git diff --cached //index<->repo
```


##2
###Removing files
```
git rm file //remove both working area and index
git rm --cached file
```

###18 Solving conflicts
we have branch tomato, last commit = bf0  
we have branch master, last commit = d39  
then
```
git checkout master
git merge tomato  //conflict!
```
get MERGE_HEAD
```
cat .git/MERGE_HEAD  //bf0
git show bf0
```
then
```
vim conflictfile
```
then
```
git add conflictfile
git commit //no message needed
```


###Working with paths
```
git reset --hard HEAD filename  //wrong. cannot do hard reset with paths
git checkout HEAD filename  //ok
```

##4
###22 A commit by any other name
get second parent of two previous commit:
```
git show HEAD~2^2
```
###23 History Forensics
get which commit(s) affect this file
```
git blame filename
```

###24 Exploring the past
```
git log --grep apple --oneline  //show commit message contains apple
git log -Gapple --patch  //show commits contains apple  add/delete/change in files
```

```
git log HEAD^..HEAD~5
git log branch..master
```
###26 Changing the latest commit
```
git commit --amend
```
actually, this will create a new branch, and old commit will be gc'ed



###27 Fixing mistake
```
git rebase -i origin/master
```
from top to bottom, old->new commit,but
```
git log
```
from top to bottom, new->old commit  

If conflicts occur(10:00)
```
git add conflictfile
git rebase --continue
```

###28 The Reflog
```
git reflog HEAD
git show HEAD@{15}
git reflog refs/heads/master
```
