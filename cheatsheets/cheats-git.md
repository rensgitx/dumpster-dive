---
title: Git Snippets
parent: Cheatsheets
layout: default
nav_enabled: true
---

# Git Cheatsheet

## Set an alias for git log graph

```sh
git config --global alias.graph "log --all --graph --decorate --oneline"
```

## Remove all branches other than main

```sh
git branch | grep -v "main" | xargs git branch -D
```

## Pull all remote branches to local

```sh
git fetch --all && \
for branch in $(git branch -r | grep -v '\->'); \
do git branch --track "${branch#origin/}" "$branch" 2>/dev/null; \
done && \
git pull --all
```

## Github CLI - Create a repo and push to remote

[Github CLI](https://cli.github.com/manual)

```sh
gh repo create <my-project> --<public|private> --source=. --remote=upstream
```

## Tutorials

- [Code Refinery tutorial](https://coderefinery.github.io)

- [Atlassian tutorial](https://www.atlassian.com/git/tutorials)
