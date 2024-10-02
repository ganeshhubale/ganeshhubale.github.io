Title: How to push files on GitHub!
Date: 2017-10-10 06:30
Category: Tech
Tags: Git
Slug: how-to-push-files-on-github
Authors: Ganesh Hubale
I have created files on my local machine. It includes assignments, projects, documents, sample programs in C, C++, Java etc. Now I don't have any single file with me as a proof of my work. Why does it happened? It all happened because of not storing my files anywhere. Also I don't have sufficient storage too. I always want to access them from any where. I don't want to bring pendrive, hard disk or pc etc. in class for assessment. Then I came to know about GitHub, I heard about it when I was in third year. I have created account on [GitHub](https://github.com) but don't know how to use it. Also don't know about Git. Since one month I have been working on Git. I have pushed each and every file on my GitHub repostory. Now I have proof of my work.

Let's push files on GitHub repository:

*   Create a file

    > cat >> Myfile.md

*   Initialise the git

    > git init

*   Add file

    > git add Myfile.md

*   Check Status

    > git status

*   Commit file with message

    > git commit -m "Myfile added"

*   Add remote origin

    > git remote add origin github.com/username/repo_name

*   Push file

    > git push -u origin master

Thank you,

