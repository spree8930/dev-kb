# SSH

## Multiple Github Accounts &  SSH Keys

### Generate SSH Keys

Default location is `~/.ssh`. Provide names like `id_algorithm_personal` and `id_algorithm_work` to differentiate keys. Enter a secure passphrase when prompted

```shell
ssh-keygen -t ed25519 -C "your_email@example.com"

// Older Systems
ssh-keygen -t rsa -C "your_email@example.com"
```

### Add key to the ssh-agent

Create config file if it doesn't exist

```
touch ~/.ssh/config
```

Update config file to include both keys

```
Host github.com-username1
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa
  IdentitiesOnly yes

Host github.com-username2
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ed25519
  IdentitiesOnly yes
```

Add private keys to ssh-agent. System defaults to first key in config file if this step is not done

```
ssh-add ~/.ssh/id_ed25519
```

Start ssh-agent if a connection could not be established to it and then run ssh-add

```
eval $(ssh-agent)
```

Add respective public keys in github account's settings before running git clone

### Global user picked for push instead of repo user

```
ERROR: Permission to repository denied to global-user.
fatal: Could not read from remote repository.
```

Remove all identities to fix above issue

```
ssh-add -D
```
