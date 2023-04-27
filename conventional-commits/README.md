# Using Conventional Commits at Greenbone <!-- omit in toc -->

- [What are Conventional Commits?](#what-are-conventional-commits)
- [Why do we want to use conventional commits?](#why-do-we-want-to-use-conventional-commits)
- [How to create a Conventional Commit message?](#how-to-create-a-conventional-commit-message)
- [Conventional Commit Types](#conventional-commit-types)

## What are Conventional Commits?

Conventional Commits use git commit messages to provide structured information
about changes in a project. Using the structured information allows to create
changelog entries for release notes. At Greenbone [pontos] is used to derive
release notes from the git history automatically.

## Why do we want to use conventional commits?

Manually handling and maintaining changelog files leads to several issues
especially when having to maintain several release branches:

 * Merge conflicts through maintaining different versions (21.04, 21.10 ...)
 * Inconsistency in a Changelog: E.g. Adding a fix in 20.8.4 and 21.4.3. Where
   should we add the changelog entry? If we add it in 20.8.4, it won't show up
   in the 21.04 changelog.
* Additional unnecessary overhead by having to write a changelog entry, a commit
  message and a Pull Request description.

## How to create a Conventional Commit message?

The commit message should be structured as follows:

```
<type>: <title/description>

<details, reason and background for the commit>
```

## Conventional Commit Types

By default the following conventional commit types are recognized.

| Type | Description | Example |
|------|-------------|---------|
|Add   |Add something new to one/multiple files. E.g. a new function.|`Add: Add new Feature x ...`|
|Change|Change one/multiple things in one/multiple files.|`Change: Change the behavior of y ...`|
|Remove|Remove something from one/multiple files. Removed one/multiple files.|`Remove: Remove Feature z ...`|
|Fix|Fix a bug in one/multiple files.|`Fix: Resolved the behavior of X ...`|


[pontos]: https://github.com/greenbone/pontos
