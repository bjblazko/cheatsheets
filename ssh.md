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

## Publish public key

### Example

```shell
ssh-copy-id -i ~/.ssh/example.org.pub example.org
```
