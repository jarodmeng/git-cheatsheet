* `git init` creates a new subdirectory named `.git` that contains all
repository files.

* `git clone`

* `git status` tells which files are in which state.

    ![git states]
    (https://git-scm.com/book/en/v2/book/02-git-basics/images/lifecycle.png)

    * `git status -s` or `git status --short` prints a simplified status
summary.

* `git add` adds file(s) into staging area, ready to be committed.

    * If you `git add` a file and then modify the file with out re-running `git
add`, when you commit, only the file at the point of the first `git add` is
committed.

    * `git add <directory name>` would add all files in the directory
__recursively__.

* `git diff` tells what you've changed but not yet staged. It basically compares
what's in your working directory and what's in your staging area.

    * `git diff --staged` or `git diff --cached` tells what you've staged that
will go into the next commit.

* `git commit` launches your editor for you to enter a commit message.

    * `git commit -v` puts the diff of your change in the editor.

    * `git commit -m` skips the editor and accepts an inline commit message.

    * `git commit -a` adds all changed files before committing.

    * `git commit --amend` takes your staging area and last commit to make a new
commit.

* `git rm` removes a file and stages the removal for commit.

    * `git rm -f` forces a removal when you have modified the file and added it
the index.

    * `git rm --cached` keeps the file in the working directory, but removes it
from the staging area.

* `git mv` moves or renames a file.

* `git log` lists the commits made in the repository in reverse chronological
order.

    * `git log -p` also shows the diff introduced in each commit. `git log -p
-(n)` limits the output to only the last `n` entries.

    * `git log --stat` shows some abbreviated stats for each commit.

    * `git log --pretty` allows you to customize the output format. `git log
--pretty=oneline` prints each commit in only one line.

    * `git log --graph` displays commits history in a graph. It can be used with
`--pretty`.

* `git reset`

    * `git reset HEAD <file>` resets the index entry of `<file>` to its state at
`HEAD`. This means un-staging a staged file, or opposite of `git add <file>`.

* `git checkout` switches branches or restore working tree files.

    * `git checkout -- <file>` discards un-staged changes in `<file>` in the
working directory.

* `git merge`

* `git remote` manages tracked repositories.

    * `git remote -v` or `git remote --verbose` shows the URLs stored for the
shortnames of the remotes.

    * `git remote add <remote shortname> <remote URL>` adds a new remote Git
repository as a shortname. The shortname serves as an alias for the repository
URL.

    * `git remote show <remote name>` shows information about a particular
remote.

    * `git remote rename <old remote name> <new remote name>` renamed the `<old
remote name>` to `<new remote name>`.

    * `git remote rm <remote name>` removes a particular remote.

* `git fetch` downloads objects and refs from another repository.

    * `git fetch <remote name>` goes out to the remote repostiory and pulls down
all the data from the remote project that you don't have yet. Note that the
command only downloads the data to a local repository, but doesn't attempt to
merge them.

* `git push` updates remote refs with associated objects.

    * `git push <remote name> <branch name>` push `<branch name` to your
`<remote name>` server.

* `git tag` manages tag objects.

    * `git tag <tag name>` creates a lightweight tag.

    * `git tag -a <tag name>` creates a tag associated with HEAD. You can also
supply an inline tag message using `-m <message>`. If you wish to associate
another commit other than HEAD, you can supply the `<commit>` at the end of the
command call.
