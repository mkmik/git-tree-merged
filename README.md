# git-tree-merged

Is my work already on `origin/main`, even after a squash or rebase rewrote the SHAs?
Compares tree hashes instead of commit SHAs, so it answers that directly.

```sh
git tree-merged            # HEAD vs origin/main
```

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
