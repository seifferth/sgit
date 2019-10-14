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

## Usage

```
Usage: sgit <command> [options]

Commands:
    init    Initialize a new version control repository.

    save [subject]
            Add the current version to version control. Optionally
            include a subject to describe the changes.

    log     Show version history.

    push    Synchronize local revision history to remote copy. This
            can be used as a backup mechanism. An upstream has to be
            configured first for this command to work.

    checkout <version> [dir]
            Load a previous version. If "dir" is specified, the old
            version will be saved to that directory, rather than
            the main directory. If "dir" is omitted, the specified
            version will be saved to the main directory.
            You can always return to the most recent version using
            "sgit checkout latest".

    help    Print this help message and exit.

```

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
