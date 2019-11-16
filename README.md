# Git Functions

My personal collection of custom git functions.

## Usage

In order for you to effectively make use of this repository, you'll need to clone down
its contents and ensure that they are in your `PATH`.

**N.B:** I keep this in my home firectory, but you can put in anywhere
so long as it's added to your `PATH` accordingly.

```sh
$ cd $HOME
$ git clone https://github.com/codebytere/git-fns
$ export PATH=$PATH:$HOME/git-fns
```

## Functions

#### `git patch-out <file_location> <file_name>`

Allow a user to quickly dump a diff
in patch format to their desktop.

#### `git tack <file_name>`

A quick way to add a forgotten change to the most recent commit
in a branch without needing to create a new one for a trivial 
change. Automatically pushes to the current branch.

#### `git refresh <remote_branch>`

Cleanly rebase a local working branch on a remote branch,
which defaults to origin/master.

#### `git patch-apply <commit_url>`

Apply a patch to your current working branch from
a remote commit url.

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
man(1)                        git tack man page                       man(1)


NAME
       git tack - Add a forgotten change to the most recent commit in a
       branch.

SYNOPSIS
       git tack <filename>

DESCRIPTION
       A quick way to add a forgotten change to the most recent commit in a
       branch  without needing to create a new commit. Automatically pushes
       to the current branch.

OPTIONS
       <filename>
              The filename to stage.

BUGS
       No known bugs.
```
