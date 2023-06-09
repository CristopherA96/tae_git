# TAE 2023
***

## Description
---
In this webpage relevant information about control version `Git` will be shown to you. This information will be helpful because you should upload your RTL to GDSII flow laboratories using `OpenLane` as EDA suite tools, in this repository <a href="https://github.com/CristopherA96/tae_2023_rtl2gds" target="_blank" rel="noopener">RTL2GDS repository</a>.

## Instructions
---
```yaml

$ git clone https://github.com/CristopherA96/tae_2023_rtl2gds           ; # 1. Clone repository using Personal Token
$ git clone git@github.com:CristopherA96/tae_2023_rtl2gds.git           ; # 1. Clone repository using SSH, if you add SSH key

$ cd tae_2023_rtl2gds                                                   ; # 2. Change to repo directory
$ git checkout -b st_<id>                                               ; # 3. Create a branch following st_id structure and switch to it
$ mkdir <full-name-dir>                                                 ; # 4. Create a folder named like your full name
$ cd <full-name-dir>                                                    ; # 5. Change your directory
$ gedit <file.extension>                                                ; # 6. Create a file for test and save changes
$ git add <file.extension>                                              ; # 7. Add your directory with lab1.pdf inside
$ git status
$ git commit -m "[ST_YOUR_ID] <file> added"                             ; # 8. Commit your added file
$ git status
$ git log
$ git push origin <st_your_id>                                          ; # 9. Publish your changes withing your branch to remote repo
```

!!! info
    You can add a file that you want not neccesary lab1.pdf. This file was for example, but you can add a test.txt file only to add something to the directory that you can publish.

!!! failure
    You will be working on your branch, <u>please do not modify files from other branches if it is not yours</u>.

!!! info
    Once you have created your branch and within it the folder with your full name. Inside the folder of your name add or create the files to report the results of the laboratories.
## Git Flow example
---
!!! example
    ```yaml

    $ git clone https://github.com/CristopherA96/tae_2023_rtl2gds           ; # 1. Clone repository using HTTPS, if you set Personal Token
    $ git clone git@github.com:CristopherA96/tae_2023_rtl2gds.git           ; # 1. Clone repository using SSH, if you add SSH key
    
    $ cd tae_2023_rtl2gds                                                   ; # 2. Change to repo directory
    $ git checkout -b st_1                                                  ; # 3. Create a branch following st_id structure and switch to it
    $ mkdir juan_perez                                                      ; # 4. Create a folder named like your full name.
    $ cd juan_perez                                                         ; # 5. Change to your directory
    $ cp ~/tae_reports/lab1.pdf .                                           ; # 6. Copy external files to your repo. In this case just one file added.
    $ git add lab1.pdf                                                      ; # 7. Add files to the git repo.
    $ git status                                                            ; # Optional: Check status to see changes to be commited
    $ git commit -m "[ST_1_LAB1] lab1.pdf was added"                        ; # 8. Commit staged file
    $ git status                                                            
    $ git log                                                               ; # 9. See log history. The commit you made should appear
    $ git push origin st_1                                                  ; # 10. Publish changes to your branch into remote repo
    ```

You can also visit <a href="./git_flow"  target="_blank" rel="noopener">Git Flow section</a>.

!!! Warning
    If you set your key, use SSH url instead HTTPS.

