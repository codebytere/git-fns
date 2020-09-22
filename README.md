# Git Functions

My personal collection of custom git functions.

## Usage

In order for you to effectively make use of this repository, you'll need to clone down
its contents and ensure that they are in your `PATH`.

**Nota Bene:** I keep this in my home directory, but you can put in anywhere
so long as it's added to your `PATH` accordingly.

```sh
$ cd $HOME
$ git clone https://github.com/codebytere/git-fns
$ export PATH=$PATH:$HOME/git-fns/fns
```

## Functions

### `git get-fork-branch [-r|--remote=<remote>] [-b|--branch=<branch>]`

* `-r|--remote=<remote>` - The username of the user whose fork you want to check out a branch from.
* `-b|--branch=<branch>` - The name of the remote branch to check out.

Check out a branch from an arbitrary fork.

Example:
```sh
electron on git:master ❯ git get-fork-branch -u=codebytere -b=testing
```

### `git patch-out [-l|--location=<location>] [-n|--name=<name>] [-a|--append]`

* `-l|--location=<location>` - The location on disk where the file will be created. Defaults to `$HOME/Desktop`.
* `-n|--name=<name>` - The name of the file to create or append to. Defaults to `local_diff`.
* `-a|--append` - Append to the file instead of overwriting it.

Allow a user to quickly export a diff in patch format to a file at a chosen location.  Defaults to a file named `local_diff` created at `$HOME/Desktop`.

Example:
```sh
electron on git:master ❯ git patch-out -l=$HOME/Downloads --append
```

### `git tack [-f|--filepath=<filepath>]`

* `-f|--filepath=<filepath>` - The path to the file to stage and add to the last commit.

A quick way to add a forgotten change to the most recent commit in a branch without needing to create a new one for a trivial change. Automatically pushes to the current working branch.

Example:
```sh
electron on git:master ❯ git tack README.md
```

### `git refresh [-r|remote=<remote>] [-b|--branch=<branch>]`

* `-r|remote=<remote>` - The name of the git remote. Defaults to `origin`.
* `-b|--branch=<branch>` - The name of the remote branch to rebase against. Defaults to `master`.

Cleanly rebase a local working branch on a remote branch.

Example:
```sh
electron on git:master ❯ git refresh -r=codebytere -b=testing
```

### `git patch-apply [-u|--url=<url>]`

* `-u|--url=<url>` - The url for the commit to apply to your current working branch.

Apply a patch from a remote commit url to your current working branch.

Example:
```sh
electron on git:master ❯ git patch-apply
```

### `git sync [-u|--upstream=<upstream>] [-o|--origin=<origin>]`

* `-u|--upstream=<upstream>` - The name of the upstream git remote. Defaults to `upstream`.
* `-o|--origin=<origin>` - The name of the origin git remote. Defaults to `origin`.

Fetch latest commits from an upstream branch and update your origin
with those commits.

Example:
```sh
electron on git:master ❯ git patch-apply https://github.com/electron/electron/commit/d2a82dbd1d2bd3869f910dd563001b98b3cec736
```

## Manpages

I've also included custom man pages for each of these new functions, which will need to be 
added to your `MANPATH` in order to work properly.

Assuming you have already cloned down the directory as directed above:

```sh
$ cd $HOME
$ export MANPATH=$MANPATH:$HOME/git-fns/man
```

You will then be able to run:

```sh
# Or any other custom function.
$ man git-tack
```

to see:

```sh
man(1)                         git tack man page                        man(1)

NAME
       git tack - Add a forgotten change to the most recent commit in a
       branch.
SYNOPSIS
       git tack [-f|--filepath=<path>]

DESCRIPTION
       A quick way to add a forgotten change to the most recent  commit  in  a
       branch without needing to create a new commit.  Automatically pushes to
       the current branch.

OPTIONS
       [-f|--filepath=<path>]
              The path to the file to stage and add to the last commit.

BUGS
       No known bugs.

AUTHOR
       Shelley Vohr <shelley.vohr@gmail.com>

1.0                              November 2019                          man(1)
```
