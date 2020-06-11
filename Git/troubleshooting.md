## Set upstream
Problem
```
fatal: The current branch master has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin master
```

Solution
```
.git/config

[branch "master"]
    remote = origin
    merge = refs/heads/master

or

git branch --set-upstream-to=origin
```

<br/>


## Adding remote branch
```
git remote add origin git@github.com:status-im/status-tutorials.git
```