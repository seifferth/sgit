# Scholarly Git

`sgit` is a simple wrapper around git, optimized for writing projects
rather than for code. It uses date and time to reference commits, rather
than commit ids. It also wraps adding and committing into a single `save`
command and defaults to empty commit messages.

## Use Case

Versioning is great and you would probably want to use it for
everything. Git is also great, since it is incredibly reliable,
performant and feature-rich. It is rather adapted to tracking codebases,
however. After using git to track writing projects (in markdown) for
a while, I noticed, that many of the concepts that work great for code
don't make that much sense for writing. Since writing --- at least in my
view --- is not a process of making incremental atomic changes to files,
but rather a process of reshaping parts of texts, such as paragraphs or
chapters as wholes. As a result, I frequently have great difficulty coming
up with sensible commit messages and I do prefer to check out different
versions of files in subdirectories, rather than revert commits or merge
different branches. `sgit` is intended to ease the use of git in that
sort of workflow.

## Installing

`sgit` is a standalone, POSIX-compliant shell script. Simply adding
it to some directory included in `PATH` and marking it as executable
suffices as installation. Since `sgit` is a wrapper around `git`, `git`
also has to be found in `PATH`, obviously.

## Limitations

`sgit` works with an extremely limited subset of what git actually
offers. While pushing to a single remote is supported as a backup or
publishing solution, advanced usage such as branching, is not. `sgit`
works under the assumption that each repository contains only a single
master branch, which is continuously updated as a project progresses.
Since `sgit` is only a wrapper around `git`, however, it is possible to
switch to plain `git` at any point.
