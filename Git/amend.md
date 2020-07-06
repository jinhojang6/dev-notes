## Amend a commit
To gpg sign an old commit

```
git commit --amend --no-edit -S
```

Sign specific commits
```
Go into interactive rebase mode.
Add the following line after each commit you want to sign

exec git commit --amend --no-edit -S
```

<br/>

## Git commit --amend for specific commits
```
git rebase --interactive commit_hash^
(each ^ indicates how many commits back you want to edit)
change the words pick to reword or edit
git rebase --continue
```

<br/>

## Update an author
```
git commit --amend --author="author <email>"
```

<br/>