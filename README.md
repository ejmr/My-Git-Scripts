My Git Scripts and Utilities
============================

This is my personal collection of simple and small [Git][] utilities.
They are mostly shell scripts that automate or make easier some task
related to Git repositories, which is the source-control program I use
for nearly all my programming projects.  I try to write the scripts for
`sh` or `bash` when I can, since those shells are available by default
on most systems, thus improving the portability of those scripts.
However, my preferred shell is [Fish][] and I do not hesitate to
write scripts directly for it when I feel like it would be easier.
Similarly, I use [Python][] for more complex scripts, but that is rare.

## SYNOPSIS

Each script begins with a comment block describing its purpose and
functionality.  What follows are brief examples of each, assuming
they are installed in the manner described below.

```sh
# Update the `master` branch from the remote repository,
# temporarily stashing any changes I've made so far.
$ git update-master

# Show the description of the current branch, as written by
# the standard command `git branch --edit-description`.
$ git branch-show-description

# Checkout a specific commit via its subject line, narrowing
# the possibilities interactively.  Note that I alias `coc`
# to the script `git-checkout-fuzzy-commit`.
$ git coc

# List URIs to all of my GitHub repos.
$ git ls-github-repos "ejmr"

# Clone my public repos into a `/tmp/ejmr` directory.
$ cd /tmp && git clone-github-user "ejmr"

# Clone all public repos from the "emacs-php" GitHub
# organization into the directory `$HOME/Projects/emacs-php`.
$ cd $HOME/Projects && git clone-github-organization "emacs-php"

# Update the `master` branch of every Git repo that is as
# immediate sub-directory of the current directory.
$ cd ~/Projects/emacs-php && git update-subdir-repos
```

## REQUIREMENTS

Besides [the obvious][Git], some of my scripts use the following
programs:

- [curl][] to interact with sites like GitHub.
- [fzf][] as a fuzzy selection interface.
- [jq][] for processing [JSON][].
- [fd][] as an alternative to `find`.
- [xclip][] to manipulate the X11 clipboard.
- [GNU Parallel][] to execute commands on multiple repositories.

You do not need to install all of these programs, unless you intend
to use *every* script in this project.

## INSTALLATION

Clone this repository and create symlinks to the scripts you want to
use, being sure to create those links somewhere within your `$PATH`,
e.g. I use `/home/ejmr/.local/bin` on my system.  I recommend you
use such a location that is "local" to your user account and to *not*
symlink these scripts from somewhere like `/usr/local/bin`, because
who knows what conflict these scripts may cause with the countless
other Git tools out there.

## BUGS

Please report all bugs on [the GitHub project page](https://github.com/ejmr/My-Git-Scripts).

## AUTHOR

Eric James Michael Ritz, 2018.

## LICENSE

All code and data in this project belongs to the Public Domain.



[Git]: https://git-scm.org/
[Fish]: https://fishshell.com/
[Python]: https://python.org/
[curl]: https://curl.haxx.se/
[fzf]: https://github.com/junegunn/fzf/
[jq]: https://stedolan.github.io/jq/
[JSON]: http://json.org/
[fd]: https://github.com/sharkdp/fd
[xclip]: https://github.com/astrand/xclip
[GNU Parallel]: https://www.gnu.org/software/parallel/
