## Configuration
```
git config --global user.name "name"
git config --global user.email "email"
git config --global user.signingkey 3AA5C34371567BD2
```



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


## Add gpg sign to .gitconfig
```
[user]
    email = your@email
    name = Your Name
    signingkey = YOUR_GPG_KEY_ID
[commit]
    gpgsign = true
[gpg]
    program = gpg2
[alias]
    c  = commit --verbose --no-verify --gpg-sign 
    am = commit --verbose --no-verify --gpg-sign --amend
```
reference: https://help.github.com/en/github/authenticating-to-github/signing-commits


## Ammend commit
To gpg sign an old commit

```
git commit --amend --no-edit -S
```

<br/>

## Check out a remote branch 
Git checkout remote branch lets us switch to (and work on) a remote branch, just like we’d switch to a local one.
```
git fetch origin
git checkout -b branchxyz origin/branchxyz

or 
git branch branchxyz origin/branchxyz

reference: https://dzone.com/articles/what-is-git-checkout-remote-branch-how-it-works-wh
```

<br/>
## Git commit --amend for specific commits
```
git rebase --interactive commit_hash^
(each ^ indicates how many commits back you want to edit)
change the words pick to reword or edit
git rebase --continue
```
