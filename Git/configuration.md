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


## SSH - how to solove permission denied error
Create a ssh key
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
Copy the ssh key
```
sudo vim ~/.ssh/id_rsa.pub
```

- Generating new SSH(https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
- Adding a new SSH to Github(https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)
