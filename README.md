# Git Functions

My personal collection of custom git functions.

## Usage

In order for you to effectively make use of this repository, you'll need to clone down
its contents and ensure that they are in your `PATH`.

**N.B:** I keep this in my home directory, but you can put in anywhere
so long as it's added to your `PATH` accordingly.

```sh
$ cd $HOME
$ git clone https://github.com/codebytere/git-fns
$ export PATH=$PATH:$HOME/git-fns
```

## Functions

#### `git patch-out [-l|--location=<path>] [-n|--name=<name>] [--a|--append]`

* `-l|--location=<path>` - The location on disk where the file will be created.
* `-n|--name=<name>` - The name of the file to create or append to.
* `--a|--append` - Append to the file instead of overwriting it.

Allow a user to quickly export a diff in patch format to a file at a chosen location. 
Defaults to a file named `local_diff` created at `$HOME/Desktop`.

#### `git tack [-f|--filepath=<path>]`

* `-f|--filepath=<path>` - The path to the file to stage and add to the last commit.

A quick way to add a forgotten change to the most recent commit
in a branch without needing to create a new one for a trivial 
change. Automatically pushes to the current branch.

#### `git refresh [-r|remote=<name>] [-b|--branch=<name>]`

* `-r|remote=<name>` - The name of the git remote.
* `-b|--branch=<name>` - The name of the remote branch to rebase against.

Cleanly rebase a local working branch on a remote branch,
which defaults to origin/master.

#### `git patch-apply <commit_url>`

Apply a patch to your current working branch from
a remote commit url.

#### `git sync <upstream>`

Fetch latest commits from an upstream branch and update your origin
with those commits.

## Manpages

I've also included custom man pages for each of these new functions, which will need to be 
added to your `MANPATH` in order to work properly.

Assuming you have already cloned down the directory as directed above:

```sh
$ cd $HOME
$ export PATH=$PATH:$HOME/git-fns/man
```

You will then be able to run:

```sh
$ man git-tack # or any other custom function
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
