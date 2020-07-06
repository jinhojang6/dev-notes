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

## Case-sensive filenames
```
git config core.ignorecase false
```
- https://stackoverflow.com/questions/17683458/how-do-i-commit-case-sensitive-only-filename-changes-in-git

<br/>

## Why does pulling sometimes make me create a commit?
Simple answer: git pull is just a combination of git fetch and then a plain git merge.

As any merge, if Git finds out fast-forwarding is not possible, a traditional merge is necessary (one more commit with two parents), therefore this process asks for a commit message.

Reference: [Git docs for branching and merging](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)

- Answer from https://stackoverflow.com/questions/37796805/why-does-pulling-sometimes-make-me-create-a-commit

<br/>

## What is git fast-forwarding?
When you try to merge one commit with a commit that can be reached by following the first commit’s history, Git simplifies things by moving the pointer forward because there is no divergent work to merge together – this is called a “fast-forward.”

For more : http://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging

In another way,

If master has not diverged, instead of creating a new commit, git will just point master to the latest commit of the feature branch. This is a “fast forward.” There won't be any "merge commit" in fast-forwarding merge.

- Reference: [Stackoverflow: What is git fast-forwarding? [duplicate]](https://stackoverflow.com/questions/29673869/what-is-git-fast-forwarding)
