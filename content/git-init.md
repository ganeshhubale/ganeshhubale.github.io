Title: git init
Date: 2017-10-05 18:0
Category: Tech
Tags: Git
Slug: git-init
Authors: Ganesh Hubale

> git init

*   init stands for initialization
*   Directory is a folder used for storing multiple files. It may be text or doc
*   Repository is a directory where Git has been initialised to start version controlling your files

What to do?

*   Create one directory/folder

    > mkdir Documents/MyFolder

*   Go into that folder

    > cd Documents/MyFolder

*   Enter the command

    > git init

*   Hidden folder ‘.git ’ will be created

    > ls -la

*   You can enter into this folder to see various files created automatically

    > cd .git

*   You will see files and folders

    > branches, config, description, HEAD, hooks, info, objects, refs

*   You can see the files inside these folders and then return to MyFolder

    > cd ..

*   If you retype the git init command in same folder then it will reinitialise the .git repository for version controlling This is how git init works.

Thank you,
