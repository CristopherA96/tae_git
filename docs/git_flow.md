# Git Flow 

## Basic flow
***

### Option 1: By creating repo
!!! info
    With this option you create the repository locally and then you connect it to a created remote repository. It supposses that you already have a remote repository created.

```yaml
    $ mkdir -p <dir>                            ; # Create the directory
    $ cd <dir>                                  ; # Change to directory
    $ git init -b main                          ; # Initialize directory by setting a main branch
    $ vi <file>                                 ; # Create files, if you do not have them. i.e: README.md file
    $ git status                                ; # Check repo's status. See repo changes
    $ git add <file>                            ; # Add files locally.
    $ git commit -m "MESSAGE"                   ; # Commit added files.
    $ git status                                ; # Check repo's status. See clean repo
    $ git log                                   ; # See log history of your commits
    $ git remote add origin <url-repo>          ; # Create the remote connection between local and remote
    $ git remote -v                             ; # Check remote status
    $ git push origin main                      ; # Publish changes from local to remote repo
```

### Option 2: By cloning repo

!!! info
    Using this option assumes that you have created a remote repository on GitHub. If you do not know how to create it, visit <a href="../github"  target="_blank" rel="noopener">GitHub section</a>.

```yaml
    ## Move to a path where you want to save this repo, and then follow:

    $ git clone <url-repo>                      ; # Clone remote repo in your local path
    $ vi <file>                                 ; # Create/Edit files
    $ git status                                ; # Check repo's status. See repo changes
    $ git add <file>                            ; # Add files locally.
    $ git commit -m "MESSAGE"                   ; # Commit added files.
    $ git status                                ; # Check repo's status. See clean repo
    $ git log                                   ; # See log history of your commits
    $ git push origin main                      ; # Publish changes from local changes to remote repo
```

!!! note
    By cloning a repo, you have the remote connection automatically.