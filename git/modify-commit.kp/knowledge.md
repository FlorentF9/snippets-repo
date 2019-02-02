---
title: Modifying a git commit
authors:
- FlorentF9
tags:
- git
created_at: 2019-02-02 00:00:00
updated_at: 2019-02-02 19:43:34.720305
tldr: Modifying the last git commit using amend.
---

One often wants to modify the last commit, for example if one forgot to include some modification in it, or if there was a typo in the commit message.

### Modifying the last git commit

First, add the modifications using `git add`. Then one can use the following command, that will update the last commit:

```shell
$ git commit --amend -m "New message"
```

Or, to keep the same commit message:

```shell
$ git commit --amend --no-edit
```

In case the last commit was already pushed to the remote branch, you can push using  the `-f` flag to overwrite it.  
```shell
$ git push -f
```
**When using this option, verify that you don't overwrite someone else's commit.**