Title: git status
Date: 2017-10-05 18:02
Category: git
Tags: commands
Slug: git-status
Authors: Ganesh Hubale
> git status

*   It is healthy to run git status often
*   Sometimes things change and you don’t notice it
*   It gives the status of files like untracked, unmodified, staged and unstaged

> staged:

Files are ready to be committed.

> unstaged:

Files with changes that have not been prepared to be committed.

> untracked:

Files aren't tracked by Git yet. This usually indicates a newly created file.

> deleted:

File has been deleted and is waiting to be removed from Git.

*   The git status command DISPLAYS THE STATE OF THE WORKING DIRECTORY AND THE STAGING AREA

What to do?

*   Enter command

    > git status

*   Read the output

    > On branch master

It means now you are working on default branch ‘master’.

> Initial commit

It show the commit message you have entered while committing any file. By deafult it shows initial commit because you have not commited any file yet.

> nothing to commit (create/copy files and use "git add" to track)

This is the message which clearly showing you that there is no file to commit in folder. So now you must have to create files or copy files from other sources whichever file you are going to commit.

What to do?

*   Create simple file

    > gedit README.md

*   Enter Sample information into it

    > My first file

*   See this File

    > ls

*   Or you can see the content of file

    > cat README.md

*   Create file

    > touch .gitingore

It is simple text file where we can add files that we want git to ignore.

Thank you,

