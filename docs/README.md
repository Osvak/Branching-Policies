![](images/branch1.png)

**Branching** is the term used to describe the idea of **deviating** from the default branch.
In computer science  means you diverge from the main line of development and continue to do work without messing with that main line. 
In many version control software this is an expensive process, often requiring you to create a new copy of your source code directory, which can take a long time for large projects.

But in Git this process is incredibly lightweight, making branching operations nearly instantaneous, giving the ability to switch between branches just as fast.
This way people that use Git branch and merge more often, even more than once a day.

Specificaly I'll to focus on project branching with [**GitHub**](https://github.com/).

Here I will explain *why* is useful, *when* you should implement it, and *how* you can do it using GitHub.

I'm also going to introduce you to some Branching models and compare them. 

# Why ?

When starting using VCS people usually starts by commiting all the changes in main, and using only this branch. This can look like a good idea, but as you develop bigger and bigger projects, you will face some conflicts, usually when working with other people. I'm not saying that you shoudn't use Single Branch Flow, it has it's own public, and sometimes even it's used in small group projects, I will explain more about the most used models below.

What I mean is that, understanding and mastering this feature gives you a powerful and unique tool and can entirely change the way that you develop, and you should lean as soon as possible, so in the future you can know when it's necessary or not. 

### Pros

- Branching allows you to isolate the work from the main branch, so in case of a problem only one branch is affected.
- When a change is commited is guaranteed that it works correctly, this makes easier to manage the repository.
- Simplifies the QA and bug fix process
- Limits who can contribute to each branch
- Ensures that a change to a branch must be reviewed, even selecting how many people must review it before the commit gets implemented
- In Git branches don't generate additional copies of the files when they are created, so they are cheap to create.
- Ability to share branches without having to merge the changes into the main project

### Cons

- For very small projects it makes the process more complicated

# When ?

It is always **recommended** to use a branch strategy even if the project is very small, due to all the advantages it has compared to the small amount of cons.

Referring to the specific moment to implement it on a project, is suggested to do it **as soon as possible**, but having in mind already what model are you going to use.

The process of selecting the model of branching must be chosen by the management and production teams, that have the ability to tell the magnitude of the project and how it's going to affect the development.

If you are not sure if you need a new branch, create one anyway, because it's easier to create a branch and then merge it, than move a commit from one branch to another.

So, to sum up, **create a branch when you are going to work in something new.**


# How ?

Branches don't generate copies of the files from the source, they use commit history information to recreate the files of a branch when you work on it, this concept makes it easier to switch between branches at any moment.

## Step By Step Process

**1. Open the branch selector**

GitHub Desktop has a Dropdown button that allow you to see and change what branch do you want to work in.

![Step1](images/git1.png)

**2. Select the "*New branch*" option**

If the branch is already created, just select the specific branch you want to work in.

![Step2](images/git2.png)

**3. Give an appropriate name to the branch**

Use a consistent naming convention for your feature branches to identify the work done in the branch. You can also include other information in the branch name, such as who created the branch:

```
feature/feature-name
hotfix/description
users/username/workitem
```


![Step3](images/git3.png)

**4. Switch the branch you want to work in, here you can also bring the changes to the new branch**

If you already done the changes but forgot to create a branch you can import the changes to the new branch with any problems.

![Step4](images/git4.png)

**5. Publish the new branch to the repository**

Publishing a branch makes it public to the contributors of the project, so now the branch is officialy made.

![Step5](images/git5.png)

**6. Create a Pull Request**

When all the changes are done the branch can be merged, but before doing it you first have to create a pull request, this works as a safety measure, the request must be accepted before it can be merged to the father branch.

![Step6](images/git6.png)

**7. Open the Pull Request**

When opening a pull request you can write some description about the request and select the type of request, between pull request and draft pull request.

Pull request it's a request that can be merged with or without a revision. While a draft pull request it's not ready to review yet. Can only be merged after they are marked as ready for review. This is useful because pull requests are often used as conversations, often prior to the work being ready to merge.

Also, before opening the request you can also specify who has to review it, who is assigned to this pull request, give it some labels, projects, milestiones or linked issues to simplify the work of reviewing.

To clarify, assignees are the ones who work on specific issues and pull requests. They are sometimes confused as reviewers. They are actually meant to be used with issues rather than pull request so that when we receive a issue we can assign someone to fix it. They are in charge of merging that pull request after getting comments and change requests from other maintainers.

![Step7](images/git7.png)

**8. Merge the Pull Request to the Branch**

In the Pull Request tab you will find all the information abot the request, first you have the Conversation tab where all the communication between reviewers and assignees is found. In the commits tab there are all the Commits that where added to that branch. You can see everything that has been checked in the Checks tab. Finally, in the Files Changed tab there is a log of how each file has changed during the review.

![Step8](images/git8.png)

# Most used Branching Models

## Single Branch
![Single](images/model1.png)

- Develpment and Production all it's in the Master branch
- Teams need to trust each other, if not, this model I wouldn't recommend this model
- All the commits are based on the use of Feature Flags*

`* Feature Flags that allow you to enable or disable a new feature, often used to avoid conflicts when merging.`

## GitHub Flow (Feature Branching)

![GitHub](images/model2.png)

- Development, Production and Pre-Production environment are found in the Feature branch
- Everything is done in the Feature branch, even deployment, in case of a bug the Master branch can be used.
- Production is also done in the Master branch.
- Master is allways deployable and acts like a safety measure
- Works very well with Continuous Deployement*
- Clean Commit History

`* Continuous Deployement`

## Git Flow
![Git](images/model3.png)


## Release Flow
![Release](images/model4.png)


## GitLab Flow
![GitLab](images/model5.png)

## Trunk-Based Development
![Trunk](images/model6.png)

Go [Up](https://osvak.github.io/Branching-Policies/)
