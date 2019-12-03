# Configure user

```bash
git config --global user.name "John Doe"
git config --global user.email "john@example.com"
```

# Checkout/clone

```bash
  git clone git@github.com:bjblazko/simple-java-maven-app.git
```

# Update to branch#HEAD

```bash
git stash
```

See https://git-scm.com/docs/git-stash

# Show difference between local and remote (not including workspace)

Replace `master` by your according branch name, if required.

```bash
git fetch origin
git diff master origin/master
```

# Revision graph/tree

```bash
git log --all --decorate --oneline --graph
```

# Switch branch 

```bash
git fetch
git branch -a # list all branches available
git checkout [branch-name]
```
