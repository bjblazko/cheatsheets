# SSH cheat sheet

Most credits go to Martin Leyrer, for example most of this is taken from https://www.youtube.com/watch?v=qvdlLTyUJ5I (German language)

## Creating keys

### Example

```shell
ssh-keygen -t ed25519 -a 420 -f ~/.ssh/github -C "bjblazko on Github"
```

### Explained

* `-t`: key type, crypto algorythm; advice is to use ED25519 for modern systems and is also compact
* `-a`: rounds/cycles for key pair generation; the higher the more secure
* `-f`: file base name to generate to; when ommitted, a default will be proposed
* `-C`: comment; when using mulitple keys, ensure to but target system and your contact in it
