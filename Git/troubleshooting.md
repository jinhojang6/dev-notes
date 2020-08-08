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

<br/>

## Avoid re-entering password for each submodule

To enable git cache with default timeout (15 min) you type
```
git config --global credential.helper cache
```
To change default timeout type
```
git config --global credential.helper 'cache --timeout=3600'
```

- Reference: https://stackoverflow.com/questions/30180751/avoid-re-entering-password-for-each-submodule

