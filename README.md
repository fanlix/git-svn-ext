## git-svn-ext

Put git-svn-ext in your path and run it from the top-level tree checked out with git-svn.
git-svn-ext will detect and git-svn clone the externals using the following method:

1. git svn clone each external into a `.git_externals/` directory.
2. symlink the cloned repository in `.git_externals/` to the proper directory
  name.
3. add the symlink and `.git_externals/` to the `.git/info/excludes/` file, so that
  you're not pestered about it when performing a git status.

### Usage

Usage: `./git-svn-ext <sub command> [sub command args]`

Sub commmands:
* `clone`   clone all svn externals into .git_externals
* `update`  updates all svn externals (git svn fetch[ --revision]/rebase --local)
* `check`   check if local git-svn checkout has unpushed commits and uncommitted changes
* `execute` run a command against all externals (ie: `git svn-ext execute 'git grep "whatever"'`)

*Note: externals may be ignored if listed in `.git_external_excludes`*

### Authors

This script is based on git-svn-ext / git-svn-clone-externals from the following repositories:
- [andrep/git-svn-clone-externals](https://github.com/andrep/git-svn-clone-externals)
- [markvl/git-svn-clone-externals](https://github.com/markvl/git-svn-clone-externals)
- [svetlyak40wt/git-svn-clone-externals](https://github.com/svetlyak40wt/git-svn-clone-externals)
- [wberrier/git-svn-ext](https://github.com/wberrier/git-svn-ext)

