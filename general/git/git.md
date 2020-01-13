## Gitignore

After creating a repository, it is recommended to add .gitignore to tell Git which files to ignore.

```
touch .gitignore

# install vim (ref: http://macappstore.org/vim/ on Mac)
vi .gitignore


# edit .gitignore (ref: https://github.com/jinhojang6/jinho-notes/blob/master/.gitignore)
```

- .DS_Store: stores custom attributes of its containing folder, such as the position of icons or the choice of a background image (ref: https://en.wikipedia.org/wiki/.DS_Store)

- node_modules/ should be ignored to make the work faster and recompile the modules in a different development machine (ref: https://flaviocopes.com/should-commit-node-modules-git/

- Executable files(e.g., .exe) should be ignored as well for the same reason.

- Github Help : https://help.github.com/en/articles/ignoring-files

<br/>


## Ammend commit
Git checkout remote branch lets us switch to (and work on) a remote branch, just like we’d switch to a local one.
```
git commit --amend --no-edit -S
```

<br/>

## Check out a remote branch 
To gpg sign old commits
```
git fetch origin
git checkout -b branchxyz origin/branchxyz

or 
git branch branchxyz origin/branchxyz

reference: https://dzone.com/articles/what-is-git-checkout-remote-branch-how-it-works-wh
```
