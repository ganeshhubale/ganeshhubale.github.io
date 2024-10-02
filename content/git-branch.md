Title: git branch
Date: 2017-10-09 09:02
Category: git
Tags: commands
Slug: git-branch
Authors: Ganesh Hubale
> git branch

*   Branch is pointer to changes commited by you

What to do?

*   To check on which branch you are woking now

    > git brach

*   To create new branch

    > git branch<branch_name></branch_name>

*   Change the working to branch to what you want

    > git checkout<branch_name_you_want></branch_name_you_want>

*   Now just change one file

    > git status

*   Add this file

    > git add<file_name></file_name>

*   Commit the changes with msg

    > git commit -m "new file added"

*   Push to remote repository

    > git push -u origin<branch_name></branch_name>

*   Now lets merge the brach with master

    > git checkout master

It is switching to master branch

> git pull origin master

It is checking is there any modifications done by any one in remote repository

> git branch --merged

It checks branches are meged or not

> git merge<branch_name></branch_name>

It merges to master

> git push -u origin master

It is pushing repo to remote directory in branch master

*   Now we can sent changes to master branch then we dont require <branch_name>(i.e. we have created) so we are going to delete it</branch_name>

*   To delete the branch locally

    > git branch -d<branch_name></branch_name>

*   To delete the branch remotely

    > git push origin --delete<branch_name></branch_name>

Thank you,

