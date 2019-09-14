**Check for existing Key**
```
ls -al ~/.ssh
```

**Generating a new Key**
```
ssh-keygen -t rsa -b 4096 -C "<github-email>"
```
Enter file in which to save the key (/Users/plawanrath/.ssh/id_rsa): *[Press Enter]*
Enter passphrase (empty for no passphrase): *[Enter a passphrase]*
Enter same passphrase again: *[Enter Passphrase again]*

**Start the ssh-agent**
```
eval "$(ssh-agent -s)"
```

**Update config file**
```
vim ~/.ssh/config
```
```
Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_rsa
```

**Add ssh key**
```
ssh-add -K ~/.ssh/id_rsa
```

**Copy the ssh key to clipboard to add it to Github**
```
pbcopy < ~/.ssh/id_rsa.pub
```

**Add the SSH Key to Github in settings**
