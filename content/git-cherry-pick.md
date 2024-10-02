Title: Fear of cherry-pick
Date: 2018-02-07 01:11
Category: Tech
Tags: Git
Slug: git-cherry-pick
Authors: Ganesh Hubale

I was very happy for doing a lot of essential changes and making it's one PR in reference with more than one issues. I asked one of my friend [@bhavin192](https://github.com/bhavin192) to review these changes because I want to merge this PR as early as possible. I was expecting to get positive reply but he replied me to perform those things which I didn't do earlier. He wants me to make only one PR for each issue.

> Making an individual PR for every issue is essential because it helps novice reviewer to understand and review particular changes regarding that issue.

This was the first mistake; I need to fix. There are various ways to do it like we can reset that branch. Then by creating new branch from master; we can be able make changes manually or can copy-paste old code. But there was something waiting for me.

Yes, It's **cherry-pick**.

> **git cherry-pick**. It is something like moving commits from one branch to another.

I was surprised but I knew it must be command. He wants me to use this command to fix this problem. My reaction was like please let me merge this PR. I will take care of it for next PRs. I searched about it. I understood somehow then we decided to do it. 

First time I thought it would be very complicated but because of doing it on my own with his support. I found it very simple and best way to fix such problems. I did silly mistakes too which helped me to understand new things. Also he introduced me to new git commands. I got one more thing from this experience is 

> Solving particular problem introduces us to various aspects other problems too. 

Now I have very simple way in my mind to perform it. I performed it for remaining changes in morning. I will introduce you to the process of git cherry-pick in a very simple way.

You just have to know basic things like

    How to reset a branch!
    Creating a new branch and switching to it.
    Familiar with making PRs.
    Something about --force and --force-with-lease


> **Note: Do not perform any changes or --force on  master branch.**

* Create a new branch from master. Let's say, **new** branch
* Switch to branch from where you had done PR. Let's say, **old** branch
* We have to see commits and it's hashcodes. So that we can cherry-pick selected commits on **new** branch from **old** branch.
    -  To get commit list with it's hashcodes.
 
        > **git log  --oneline**

          Pick hashcodes one by one you want to cherry-pick on **new** branch.
 
 * Switch to **new** branch.
 
    > git cherry-pick commit_hashcode

* There are two cases, you may find conflicts or you may not.

    - Case First: found conflicts, resolved and saved changes.

        - **git add** this file 
        - just make command : **git cherry-pick --continue** then **git commit** 
    * Case Second: No conflicts.
 
        - **git status**

          - There will be nothing to add or commit.

* Now switch to **old** branch.
 
    > **git reset --hard commit_hashcode**

      Hashcode is must of commit where you want to point your HEAD.

* Now switch to **new** branch
 
    > **git push**

      Make new PR with changes done.

* Switch to **old** branch. 

    - **--force-with-lease**

    > **git --force-with-lease**
     
      Will be useful; if you were not gone through any conflicts.

    - **--force**

    > **git --force**
    
      Will be useful in any condition.
    
Thank you,

