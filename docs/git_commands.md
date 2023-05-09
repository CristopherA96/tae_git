# Git Commands 

## Glossary
***

!!! info
    - **HEAD** is the pointer of the current branch reference.
    - **origin** is a short name for the remote repository. It references the original repository url.
    - **main** is the name of the default branch.
    - **unstaged** means changes that are not tracked by the git.
    - **staged** means that you have marked a modified file, it is like a tmp place, where you have added files.
    - **stash** stores temporaly changes locally. It helps when you want to update a repo but have made changes that haven't been published to the remote branch.


## Getting started
***

### Create repository locally
---

```yaml
    $ mkdir <dir>                   ; # Create local repo
    $ cd <dir>                      ; # Change dir
    $ git init .                    ; # Initialize current dir as repo with default branch
```

!!! info
    The default branch if you do not specify nothing and depending on your git version is `master`. Future git version will have default branch `main`. You can change this setting in your `git config`.
    ```yaml
        $ git config --global init.defaultBranch main
    ```
    or by initializing with
    ```yaml
        $ git init -b main
    ```

### Add files
---

```yaml
    $ git add .                             ; # Add all files in the current directory
    $ git add <file>                        ; # Add single file
    $ git add <file1> <file2> <...>         ; # Add multiple files
    $ git add *.<extension>                 ; # Add all files with same pattern (extension)
```

### View status
---

```yaml
    $ git status                            ; # View full status
    $ git status -s                         ; # View short status
```

### Commit changes
---

```yaml
    $ git commit -m "MESSAGE"               ; # Commit changes with specific message
    $ git commit                            ; # Opens default editor and type a long message
```

### Change commit message
---

```yaml
    $ git commit --amend -m "NEW_MESSAGE"   ; # Commit changes with new specific message. Only for the last one
```

### Remove files
---

```yaml
    $ git rm <file>                         ; # Remove a file
    $ git rm *                              ; # Remove all file in current directory
    $ git rm --cached <file>                ; # Remove file from staging area only
```

### Rename/Move files
---

```yaml
    $ git mv <file> <rename-file>           ; # Rename file
    $ git mv <file-path> <new-path>         ; # Move files to a new path
```

### View staged/unstaged changes
---

```yaml
    $ git diff                              ; # Shows unstaged changes 
    $ git diff --staged                     ; # Shows staged changes
```

### View history log
---

```yaml
    $ git log                               ; # View full log history
    $ git log --oneline                     ; # View log summary
    $ git log --reverse                     ; # View commits from oldest to newest
```

### View commitS
---

```yaml
    $ git commit <id-commit>                ; # View giving commit
    $ git commit HEAD                       ; # View last commit
```

### Unstaging files
---

```yaml
    $ git restore --staged <file>           ; # Undo an added file
```

!!! info
    To undo an added file is very useful this command.

### Discard local changes
---

```yaml
    $ git restore <file>                    ; # Restore a giving file
    $ git restore <file> <...>              ; # Restore multiple files
    $ git restore .                         ; # Restore all files in the current path
```

### Check out commit/branch
---

```yaml
    $ git checkout <id-commit>              ; # Checks out the given commit
    $ git checkout <branch-name>            ; # Switch to branch-name
    $ git checkout -b <branch-name>         ; # Create a branch and switch to it
```
!!! info
    `git switch` and `git checkout` are equivalent.

### Create branch
---

```yaml
    $ git branch <branch-name>              ; # Create a new branch
```

!!! info
    To remove a branch use `git branch -d <branch-name>`.


### Stash
---

```yaml
    $ git stash push -m "Msg for tmp save"  ; # Save and publish temporaly saving
```

### Merge
---

```yaml
    $ git merge <origin> <branch>           ; # Merge branch into current branch
```

!!! info
    To abort merge changes, use `git merge --abort`.


### Rebase
---

```yaml
    $ git rebase <branch>                    ; # Changes the base of the current branch
```

### Clone repository
---

```yaml
    $ git clone <url-repo>                   ; # Clone a remote repository
```

### Sync with remote
---

```yaml
    $ git fetch origin <branch-name>         ; # Search branch from origin
```


### Update local repo with remote
---

```yaml
    $ git pull origin <branch>               ; # Gets the changes from remote branch into local repo
```

!!! info
    `git pull` is a combination of `git fetch + git merge`. For divergent branches issues, use:
    ```yaml
        $ git fetch origin <branch>
        $ git merge origin/<branch>
    ```

### Manage remote repos
---

```yaml
    $ git remote                             ; # Shows remote repos
    $ git remote add <remote>                ; # Add new remote path named whatever you like
```

### Undoing commits 
---

```yaml
    $ git reset --soft HEAD^                 ; # Remove the last commit, keeps changed staged
    $ git reset --mixed HEAD^                ; # Unstage the changes as well
    $ git reset --hard HEAD^                 ; # Discard local changes
```

!!! warning
    Be very careful, using `git reset` because those changes are not irreversible and you can lose everything.

### Publish local repo with remote
---

```yaml
    $ git push origin <branch>                 ; # Publish your local changes into your remote origin path
```

## Additional commands
***

### View contributors
---

```yaml
    $ git shortlog                          ; # Shows contributors of a repo
```

### Find author
---

```yaml
    $ git blame <file>                      ; # Shows the authorof each line in file
```

### Revert commits
---

```yaml
    $ git revert <id-commit>                ; # Revert the given commit
    $ git revert HEAD~2..                   ; # Revert last two commits
```

### Recover lost commits
---

```yaml
    $ git reflog                            ; # Shows the history of HEAD
```
