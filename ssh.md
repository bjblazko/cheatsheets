# SSH cheat sheet

Most credits go to Martin Leyrer, for example most of this is taken from https://www.youtube.com/watch?v=qvdlLTyUJ5I (German language)

## Creating keys

### Example

```shell
ssh-keygen -t ed25519 -a 420 -f ~/.ssh/example.org -C "bjblazko on Example"
```

This will create the keypair as follows:

* `~/.ssh/example.org`: private key - never ever let this file leave your machine!
* `~/.ssh/example.org.pub`: public key, can be published anywhere and provisioned to your target host (see `ssh-copy-id`) 

### Explained

* `-t`: key type, crypto algorythm; advice is to use ED25519 for modern systems and is also compact
* `-a`: rounds/cycles for key pair generation; the higher the more secure
* `-f`: file base name to generate to; when ommitted, a default will be proposed
* `-C`: comment; when using mulitple keys, ensure to but target system and your contact in it

It is recommended that you work with more than one SSH identity. When working with a single one -
once your access is compromised it is for all sites. Thus, better use a separate one per site which
you can then renew.

Handling multiple identities is covered throughout this document.

## Publish public key

### Example

```shell
ssh-copy-id -i ~/.ssh/example.org.pub example.org
```


## Multiple SSH identities

When dealing with multiple identities, you basically have two possibilities:

* using `-i` option to specify your identity (key pair) to use
* controling defaults using SSH configuration

### Manually specifying identity

```shell
ssh -i ~/.ssh/example.com user@example.com 
```

This will try to connect you to SSH host `example.com` with user `user` but
with your identity (key pair) saved to `~/.ssh/example.com` (private key)
and `~/.ssh/example.com.pub` (public key).

### Define default identities per target host

For regular use, better use a default configuration by specifying the `IdentityFile`
option:

```shell
Host github github.com
   Hostname github.com
   IdentityFile ~/.ssh/github
```

where:

* `Host github github.com` defines you configuration entry with aliases `github` (for simple `ssh` usage) and `github.com` so that external tools such as `git` can match
* `Hostname: github.com` the actual host/target domain to forward to based on alias
* `IdentityFile ~/.ssh/github`: pointing to your identity (private key) to use for all connections to the host specified

As stated above, by using a SSH config here, you have the benefit to have support to switch SSH
identity also for tools not offering the `-i` option such as Git, graphical SSH frontends,
your IDE etc.