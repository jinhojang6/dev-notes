## GPG Setup 
- https://help.github.com/en/github/authenticating-to-github/managing-commit-signature-verification 

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

<br/>