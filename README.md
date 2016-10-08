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
