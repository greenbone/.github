# Using Conventional Commits at Greenbone <!-- omit in toc -->

- [What are Conventional Commits?](#what-are-conventional-commits)
- [Why do we want to use Conventional Commits?](#why-do-we-want-to-use-conventional-commits)
- [How to create a Conventional Commit message?](#how-to-create-a-conventional-commit-message)
- [Conventional Commit Types](#conventional-commit-types)

## What are Conventional Commits?

Conventional Commits use git commit messages to provide structured information
about changes in a project. Using the structured information allows to create
changelog entries for release notes. At Greenbone, [pontos] and [git-cliff] are
used to derive release notes from the git history automatically.

## Why do we want to use Conventional Commits?

Manually handling and maintaining changelog files leads to several issues
especially when having to maintain several release branches:

 * Merge conflicts through maintaining different versions (21.04, 21.10 ...)
 * Inconsistency in a changelog: E.g. Adding a fix in 20.8.4 and 21.4.3. Where
   should we add the changelog entry? If we add it in 20.8.4, it won't show up
   in the 21.04 changelog.
* Additional unnecessary overhead by having to write a changelog entry, a commit
  message and a pull request description.

## How to create a Conventional Commit message?

The commit message should be structured as follows:

```
<type>: <title/description>

<details, reason and background for the commit>
```

## Conventional Commit Types

By default, the following conventional commit types are recognized when using
the [Greenbone `git-cliff` configuration]:

| Type        | Description                                                          | Example                                |
|-------------|----------------------------------------------------------------------|----------------------------------------|
| Add         | Add something new to one/multiple files, like a new function         | `Add: Add new feature x ...`           |
| Change      | Change one/multiple things in one/multiple files                     | `Change: Change the behavior of y ...` |
| Remove/Drop | Remove something from one/multiple files, removed one/multiple files | `Remove: Remove feature z ...`         |
| Fix         | Fix a bug in one/multiple files                                      | `Fix: Resolve the behavior of x ...`   |
| Deps        | Dependency updates                                                   | `Deps: Update foo from 1.x.y to 2.0.0` |
| Doc         | Changes affecting documentation                                      | `Doc: Mention foo in README.md`        |
| Test        | Add or fix tests                                                     | `Test: Verify x is set correctly`      |
| Chore       | Repository maintenance tasks                                         | `Chore: Update .gitignore`             |
| CI          | Changes to automated workflows                                       | `CI: Run deployment for x`             |
| Misc        | Commits not fitting into any other type                              | `Misc: Do something`                   |

Note that the colon (`:`) and capitalization is optional, so commit message
titles like `Add new feature x ...` or `ci: run deployment for x` are valid and
will be recognized as well.

Additional characters in the prefix are accepted as well, meaning commit
message titles like `docs: mention foo in README.md` are also recognized.


[pontos]: https://github.com/greenbone/pontos
[git-cliff]: https://git-cliff.org/
[Greenbone `git-cliff` configuration]: https://github.com/greenbone/actions/blob/main/cliff.toml

