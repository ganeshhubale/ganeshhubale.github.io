Title: git add
Date: 2017-10-06 13:02
Category: git
Tags: commands
Slug: git-add
Authors: Ganesh Hubale
Summary: 
> git add

*   It will add the files to staging area
*   To tell Git to start tracking changes made to file, we first need to add it to the STAGING AREA

> git add -A .

The dot stands for the current directory, so everything in and beneath it is added. The -A ensures even file deletions are included.

> git reset<filename></filename>

It is used to remove file or files from staging area.

> git add .

Adds all modified and new (untracked) files in the current directory. Any file matching the patterns in the .gitignore file will be ignored by git.

What to do?

*   Enter command to add files

    > git add<file_name></file_name>

Thank you,

