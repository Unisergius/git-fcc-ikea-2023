# Git and GitPod - freeCodeCamp Algarve 22 March 2023

Git:

* Free Version Control Tool
* Open Source
* Version Control System
* For TEAMS and SOLO too.

Think about it as a ever expanding and contracting Multiverse
where realities split and merge at precise points of time...
except in this case it's just code... and probably bugs.

In case of bugs, and luckily for you, git also allows you time
travel back in time to avoid these creeping insects.

Unfortunately git doesn't allow you to go into the future where
your work is already done and passed all tests.

So what does this all mean exactly?

Without the timeline mumbo jumbo, git allows you to swift through your project's progress, merging code from different sources, quickly rollback merge processes, check historical changes, swift through parallel stages (branches).

Before GIT, we had all these versioning control tools already like:

* Backup of folders:
  * Copy and paste the folder containing the app or document files
  * Using diff tools like 2 notepad windows open and check the changes visually
  * Naming conventions like Sudoku 0.3, Sudoku 1.0, Final_report.pdf, Final_report_1.01.pdf, Final_report_1.now_really_final.pdf
* Centralised version control:
  * SVN, CVS, Perforce.
  * Based on a single central repository where all the changes are merged
  * Each copy handed to a developer or stage with just the necessary stuff to make it work locally
* Distributed Version Control System
  * You clone a copy of a repository with all the historic changes in it.
  * You don't need to have a central repository, you can decided multiple "timelines" and give them a purpose. For example having a main repository for changes but also having released repository for stability and client ready usage. And it's easy, with creating branches of your repository with a single command, setting up parameters and running it online.
  * Git, Mercurial

The first version control systems:

* Source Code Control System (1973, Bell Labs) for tracking and retrieving changes of source code under UNIX.

* Revision Control System (1982, GNU Project) also under UNIX, allowed you to commit and merge changes of single files. Worked surprisingly well for text documents written in LaTeX and your auntie's recipes.

* Concurrent Versioning System (1990, CVS Team) extends the RCS by offering a project-wide interface. A hidden folder is used inside each repository with all the historic changes made to the project.

## Why Git?

* Simple command lines.
* Faster do commit code
* Large community
* Github, Gitlab, Gitea, Gitpod etc..

----

## Git for our group of developers - a team

Let's show the power of git.

We're going to discuss the app we want to do.

It's going to be a simple app, we're here to focus on how can we colaborate as a team. For simplicity we're going to start with a simple Node.js app with express and Typescript.

----

## Feature Based Development

Depending on the number of people present, each one will be in charge of a route for a one purpose form.

### Install git

* [Git install from git-scm](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

### Let's choose a platform for our repository

* [GitHub](github.com), [GitLabs](https://about.gitlab.com/), [Gitea docker image](https://hub.docker.com/r/gitea/gitea), [Bitbucket](https://bitbucket.org/product)

Forget I let you choose anything. We're probably using one of the first two anyway.

#### Create an account on said platform

We'll wait

Now I'm going to create a repository and add you people as my colaborators.

The idea is for each of us to create a page and add it to our common repository. Let's do it in a featured based development style.

We must also agree on a common identation language for us to develop. Or not. We can also see what is it like to check the diff of a js file with different identation rules. Let's lose our minds together. (not really).

For each person, I'm going to create an issue with the new feature label and assign them to it. I'll write the function I want in there and expect that you will work from there.

You'll need to clone our common repository into your local machine and create a new branch apart from the main branch called issue#referenceOfIssue.

The main branch is a branch that should be common to us all.
In a feature based development, everytime you need to do changes, you branch out of the main and start your task.

```sh
  git clone <repository-site.git>
  git branch issue#12Kittens
```

Useful Links:

1. [Getting a Git Repo](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)
2. [Git Branches](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)

You can also do all this without the git CLI if you have an IDE with git support. Visual Studio Code streamlines it very neatly and saves you some time.

1. [Git in VSCode](https://git-scm.com/book/en/v2/Appendix-A%3A-Git-in-Other-Environments-Git-in-Visual-Studio-Code)

Starting from there, you'll create your function in a separate file and the corresponding endpoint in the file responsible for the url routes.

After your task is done, add the new and changed files to a set of staged changes and commit this set with a proper message so I can see what the commit is about.

For example:

```sh
  git add new-file.js
  git add changed-file.js
  git commit -m "#12 - Added route and function for page of kittens"
```

Useful Links:

1. [Recording Changes to Repo](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)

Since you cloned the repository, you already have the remote link set.

Push your changes to the repository and ask for a pull request if needed.

```sh
  git push remote origin
```

You uploaded your new branch to our repository.

The merge magic needs to happen now for the code changes to get integrated in the main branch.

This is done with a pull request to a repository where you politely ask the owner of the repository that you'd like
to upload your changes with the owners.

----

## Trunk based Development

This way is largely adopted by smaller groups just because it's easier and with less formalities. 
With a team it goes like this.

* Clone the main to your local machine with a local branch.
* Make your changes in that branch.
* fetch the remote main and start merging locally analyzing what code is conflicting.
* When done, push your code. 

This is normally done with a CI/CD application on the side. This application would normally test your changes and deploy if the test list goes all green.
A CI/CD app is very important, but in this meetup, we'll might not have enough time to deploy it. We'll see.

For trunk based development to happen, the owner has to add colaborators proper privileges to commit directly to his/her repo. 

## GitPod

Here's where I pray I show you something new now.

Grab your repo link and prefix it with gitpod.io/# like this: 

> gitpod.io/#https://github.com/Unisergius/simple-math-api-exercise

Watch the magic.

Gitpod gives you a development stage for you to work and test your repo in a matter of seconds.

Perfect for new team members not wanting to install any stuff in their laptop.

You can choose the IDE and how much power do you want to use in your gitpod environment.
