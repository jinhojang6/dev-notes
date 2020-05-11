## Configuration
```
git config --global user.name "name"
git config --global user.email "email"
git config --global user.signingkey 3AA5C34371567BD2
```

<br/>

## Check Git configuration
```
all: git config --list
email: git config user.email
name: git config user.name
```

<br/>

## Change Git configuration
```
# local
git config credential.username "new_username"

# global
git config credential.username --global "new_username"
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

<br/>

