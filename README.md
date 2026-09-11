# git-tree-merged

Is it safe to delete this branch? Its content may have been squashed, rebased and
landed on a `main` that moved on since — none of which `git branch --merged` or a
tree-hash comparison can see.

```sh
git tree-merged            # HEAD vs origin/main
```

Exit 0 means `origin/main` already holds every change the branch carries, so
deleting it loses nothing. It works by merging the branch in memory and checking
that the result changes nothing, which survives any amount of SHA rewriting.

Full docs are in the man page:

```sh
man ./git-tree-merged.1
```

Install: put `git-tree-merged` on your `PATH` (that's what makes `git tree-merged`
work) and `git-tree-merged.1` in a `man1` directory, e.g.

```sh
install -m755 git-tree-merged ~/.local/bin/
install -m644 git-tree-merged.1 ~/.local/share/man/man1/
```

Needs git 2.38+.
