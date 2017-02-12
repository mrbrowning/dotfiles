Dotfiles
========

This is a slim set of dotfiles targetted at getting a fully-featured command-line development environment running on a new machine. It is Linux/OS X-agnostic, but will probably have some issues on a BSD system since platform checks that use BSD utility syntax where necessary (e.g. `ls -G`) rely on the output of `uname` being `Darwin`. I will fix this as soon as it becomes remotely relevant to my daily life.

Installation
------------

The install script is meant to be maximally convenient and minimally invasive. Rather than copy files, it creates symlinks in your home directory that point to the files in this repository. To see a full list of options, run:

    ./install -h

You can install a subset of all the dotfiles available by specifying which ones in particular you want with flags, e.g. for just git (which requires that you supply author name and email for your commits):

    ./install -g -a "Lauren Olamina" -e lolamina@earthseed.org

If you're worried about messing up your home directory, do a dry run with the `-n` flag and `install` will merely print out what commands it would run instead of actually running them. Without the `-n` flag, `install` will by default create backups of any file in your home directory that it might overwrite and save them as `${EXISTING_FILE}.old`. To disable this behavior, use the `-f` flag.

Lastly, if you'd prefer to have these choices presented to you in a series of interactive dialogs, just run `./install` without any dotfiles options. The `-n` and `-f` flags will still work, but for each utility you'll be prompted as to whether you want to install the relevant dotfiles that configure it.

Bash
----

Bash setup includes a `.bash_profile` that Does the Right Thing by only setting variables of global interest such as `PATH`, and then sourcing `.bashrc` in the case that stdin is a tty, a few (platform-dependent) aliases, a pretty standard `.bashrc` with prompt that includes `$PWD`, git branch if relevant, and status code output by the last-run command.

Emacs
-----

Emacs setup is just Spacemacs config as a subtree.

Git
---

Git setup includes useful aliases in `.gitconfig` (and the disabling of git's pager-by-default behavior: not your job, Git) and hooks for refreshing ctags in a repo on commit, checkout, merge, etc.

Haskell
-------

Haskell setup includes config for GHCi that imports useful packages on startup.

Vim
---

Vim setup includes reasonable defaults for editor settings in `.vimrc` along with some personal key mappings. The following plugins come preinstalled as subtrees:
 - [ctrlp](https://github.com/ctrlpvim/ctrlp.vim), for fuzzy file search
 - [delimitMate](https://github.com/Raimondi/delimitMate), for smart bracket, paren, etc. autocompletion
 - [fugitive](https://github.com/tpope/vim-fugitive), for git interaction and commit browsing
 - [neocomplete.vim](https://github.com/Shougo/neocomplete.vim), for smarter autocompletion
 - [nerdtree](https://github.com/scrooloose/nerdtree), for hierarchical file browsing
 - [rust.vim](https://github.com/rust-lang/rust.vim), for Rust conveniences
 - [slimv](https://github.com/kovisoft/slimv), for paredit, mostly
 - [tagbar](https://github.com/majutsushi/tagbar), for navigating ctags in-file
 - [thrift.vim](https://github.com/solarnz/thrift.vim), for Thrift file syntax highlighting
 - [viewdoc](https://github.com/powerman/vim-plugin-viewdoc), for pulling in multiple documentation sources
 - [vim-airline](https://github.com/vim-airline/vim-airline), for a more fully-featured status bar
 - [vim-fireplace](https://github.com/tpope/vim-fireplace), for convenient Clojure REPL interaction and doc viewing
 - [vim-go](https://github.com/fatih/vim-go), because sometimes you have to write Go, unfortunately
 - [vim-indent-object](https://github.com/michaeljsmith/vim-indent-object), for representing indent levels as Vim text objects
 - [vim-puppet](https://github.com/rodjek/vim-puppet), for Puppet syntax highlighting
 - [vimux](https://github.com/benmills/vimux), for tmux interaction

tmux
----

tmux setup includes vim-like keys for switching panes and some color settings for borders and status bar.
