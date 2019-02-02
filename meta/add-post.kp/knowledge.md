---
title: Add a new snippet-repo post
authors:
- FlorentF9
tags:
- meta
- knowledge-repo
created_at: 2019-02-02 00:00:00
updated_at: 2019-02-02 23:08:29.823089
tldr: This meta-post explains how to add a new post to the snippet-repo.
---

### Adding a new post to the snippet-repo

#### Create and submit the post

Use the template to write a snippet, e.g. using the Jupyter notebook template. Choose a category or sub-category for you post and add it to the knowledge-repo:

```shell
$ knowledge_repo add my_post.ipynb -p category/sub/my-post
```

This will automatically create a new branch.  Then, preview the post using:

```shell
$ knowledge_repo preview category/sub/my-post
```

If everything looks fine, submit the pull request: 

```shell
$ knowledge_repo submit category/sub/my-post
```

#### Merge the branch into master

```shell
$ git checkout master
$ git pull
$ git merge category/sub/my-post.kp
$ git push
```

Eventually, delete the branch:

```shell
$ git branch -d category/sub/my-post.kp
```