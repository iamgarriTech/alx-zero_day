My second readme

Concepts
For this project, students are expected to look at these concepts:

Right-engineering, right-documenting
Source code management
Git and Github cheat sheet - Everything in less than 30 seconds

## Right-engineering, right-documenting

You will often be told that software engineers have a tendency to under-document, and to over-engineer; but truth be told, you also find cases where engineers have over-documented, or under-engineered, and it’s equally damaging. While a lot about it is very subjective, and there is no single right level of documentation or engineering, there are key landmarks to keep in mind.

## Right-documenting

On my first week at Apple, I was appalled when I heard: “We don’t document our applications here, it is simply part of the Apple culture”. At first, I thought I was simply talking with a particularly lazy team who made up some excuse, but it was echoed a few weeks later with a post on Apple Web (the main internal portal) by Apple University (the team in charge of studying and evangelizing internally about Apple’s culture). It couldn’t get much more official than that. I was very intrigued, so I asked around, and I came to understand that it was a lot like most company culture items in every company: it was not entirely true, but more designed to prevent people from doing too much of the opposite. Since they had noticed that over-documentation could often be in the way of flexible innovation, and that they worry so much about innovation, they were willing to have more of the downsides of under-documenting (people doing duplicate work without knowing, application running and no one knows how they work), rather then the opposite.

## Items of documentation
You will often hear it said that a developer doesn’t write code for a computer, but primarily for another developer to read it. Assume that a developer who knows nothing about the decisions you made on your project, and what you were trying to do, will take it over and need to understand it. What can you do today to help them get up to speed efficiently? Here’s the killer motivation: more often than not, that developer is actually you, months from now, after working on many other projects and forgetting all about the decisions you had made. Just like every developer, you will reach that moment where you hate your past self for not having documented better. You can consider anything that helps that future developer understand your decisions and get into your code is an item of documentation, such as:

- The most obvious: **architectural documentation** , documenting the most high-level choices you made. It shouldn’t necessarily contain any code, but should simply explain in the most concise and digestible way possible some of the choices that will allow to understand how the code is organized.
- **Comments** are your best way to document what the code is doing at a narrower level:
  - Comments to describe your functions (even more so if your code is meant to be reused by other people): you may want to look into the syntaxes that are conventional in the language you’re using. There might be documentation generators using the comments if they’re input properly.
  - Comments inside functions: they should be short and descriptive enough that when a developer browses through the code reading only those comments, they understand what each step is, and the whole sequence of what happens.
- Names of functions and variables should represent what they’re about without ambiguity. If it would be too long to explain for the size of a variable name, add a comment before the line where you created it, to explain what it is (the next developer, not understanding what it is, will naturally try to find where it was created to try to figure out where it comes from).
- Indentation  of the code must be properly achieved, so that if the comment and name functions are not explicit enough for what the developer needs to know, they can dive into the code in the most readable way possible.
- The Git commit messages , so that a developer who is trying to figure out the chronology of events will at a glance.
- Always put a README.md file in your project. It’s even more relevant as you’ll push your projects on GitHub, since that’s what GitHub displays on your project’s homepage. A README.md file is like the about page of your project, introducing newcomers to what it’s about, how to set it up, its licence information, the process people must follow to contribute to it, … To be clear: you don’t have to have a full README file for every little project you work on, but you should definitely have one for longer projects.

Symptoms and risks of over-documenting
- Don’t document the tools you use. Rule of thumb: if some information that is in the documentation is findable online, it doesn’t belong in your documentation.
- Getting into the project is hard, because it takes more than 10 minutes to read the documentation to get started.
- It takes more than 30 seconds / 1 minute to search for the right specific information about anything, even when knowing where to look.
- Making a change is complex, because you have to ensure that the various places where things are documented are up to date. Resulting risks could be:

- people avoid making changes so that they don’t have to worry about finding what to update in the documentation (the thing that Apple feared);

because it’s too complex, people don’t bother updating the documentation, or fail to change something relevant in the documentation, which gradually turns outdated.

## Symptoms and risks of under-documenting
- Take some time to try and pretend wiping your brain and knowledge about the project, and having to learn everything from scratch about how it’s made. Write your documentation for the person you are when you do that.
- Even great code, when uncommented, looks like code spaghetti when you look at it first, and it’s very hard and time-consuming to take one’s first steps into it.
- If you make your code open-source, no one will take the time to understand your code if it’s not well-documented, and what could have been a great open-source project will stall before even existing.
- That one day of the year when you’re home with the flu, and your brain doesn’t work right, you’re going to be very happy that when your coworker contacts you with a blocking issue and asks you how the heck this gets fixed, you’re able to just reply “RTFM”, turn Netflix off, and doze off a bit.
- Also, in a larger company where it’s likely that several teams might need to build similar things, not documenting or communicating about what you’re building could mean that someone will redo it entirely from scratch while they could simply have used what you built. The opposite may happen: you suddenly realize that the thing you’ve been working on had already been done by someone else who never told anyone.

## Right-engineering

Gauging a level of engineering has a lot to do with planning for the future, avoiding to over-complicate things, and also sometimes with levels of abstraction.

Let’s take a step back with a nice physical-world allegory.

Let’s say that you are trying to accomplish a task, which is: sending 10 tennis balls into a basket. Here are two extreme possibilities to handle the issue:

1- either you’re doing it in the most naive way, grab a tennis ball, throw it in the basket, start over 9 times with the other balls.
2- or, you’re building a small catapult, smart enough that when you push a button, it will grab the first ball by itself, throw it exactly right, grab the second one, etc, with no need for you to intervene. The next day, you’re being told that you have to throw 10 golf balls. If you took the first path, that’s simple enough: grab the first golf ball, throw it, repeat. But if you used the catapult, you’re at a loss: your catapult was built for balls that weigh the same as a tennis ball, not a golf ball. You must reconstruct a new catapult from scratch. By abstracting how an object is thrown as much as you could, without consideration with things that were likely to need to be done in the future, you’ve over-engineered your system with your smart catapult, and now it’s unusable.
The next day, you’re being told that you now have to throw 100 tennis balls, and 100 golf balls. If you’ve been a catapult builder, you’re happy: give all of those to both your catapults, and they’ll manage everything for you. If you’ve been a thrower, you must be freaking out: because you haven’t tried to abstract how an object gets thrown, and therefore have under engineered your system, you now have to do everything in a way that is impractical.

Once you are very familiar with a technology, you will tend to over engineer things more, because one feels smart doing that, and throwing 10 tennis balls sounds annoying. Advanced developers tend to come up with systems that are so elegant for their use case, that it will be very hard to change it for the future use cases. To make the right decision about level of engineering, there is a tradeoff to find about keeping things simple so that they keep flexible, and making things engineered enough that are well-maintainable.

### Here are a few nice links about over engineering:

- http://www.codesimplicity.com/post/what-is-overengineering/
- https://coderoom.wordpress.com/2010/06/23/criminal-overengineering/ (has a technical bit around the beginning)

## Source code management
### What is source code management?

It allows a developer to organize code iterations chronologically, and version it for an application. The most powerful features of source code management systems are in how they allow teams of very diverse sizes to work together on the same application simultaneously.

Some terms that are common to all of them:

- A project will be called repository, it’s representing the index/the filesystem root of your project.
- Developers might create branches of the codebase, that they will iterate on separately to other developers. For instance, a branch can be meant to be used for a given feature, or a given bug fix. One can create however many branches they need.
- Once a branch is ready for it (it’s been tested, peer-reviewed, etc.), it can be merged back to the main branch. The main branch may be called differently: in Git it’s called master , in SVN it’s called trunk.
- While coding on their branch, developers are meant to work in small, atomic iterations, called commits. All commits have a commit message describing in one sentence what’s in there.
- All commits together are called the history , and it’s a big deal to write meaningful commits and commit messages in order to keep the project’s history clean at a glance, to understand what has been going on and who did what.
- Some people might be modifying the same pieces on the codebase on different branches, and this could create conflicts when one merges those branches together. Some of those conflicts can obviously only be fixed by a human, and each system has a different way to manage merge conflicts.

## Which systems exist?
I’ll put each specific wording between quotes. The same words may be used for differing notions across the various products.

- **SourceSafe** was an early source code management system from Microsoft, which didn’t handle branches, merges, or conflicts. You could “check out” a file, which meant no one else was allowed to “check it out” and modify it at the same time. When you were done with it, you could “check in” the file, making it editable again to the others. Not very suitable for large teams that may work on the same file, and longer iterations in a given file. SourceSafe is discontinued today.

- **CVS** was among the first open-source source code management systems in the industry, and used to be wildly popular, but is barely seen anymore. It didn’t handle branches, but two people could modify the same file at the same time. People would “update” their whole directory to get everybody else’s work before starting, and “commit” their code to the server when they’re done. When they would “commit” a file that had been “committed” by someone else since last time they “updated”, the system was not able to merge, so it would consider it a conflict every time, that you would have to manually fix (even if the changes were not on the same lines, for instance).

- **SVN** was built upon CVS to handle branches, so a lot of terminology is the same. At some point, it was the most used system, and it is still seen in the industry, even though people are walking away from it. When you’d create a branch, it would actually copy-paste the whole codebase into another directory in the code repository; then, you’d try to merge, and it would massively compare each file one by one. Merging algorithms were smarter than the CVS ones, but you still had conflicts on most merges, even those that shouldn’t necessarily require a human. When you’d create a “tag” (which is a set version of your code, like “1.2.0”), then the whole codebase would simply be massively copy-pasted into another directory too, but without the intention to merge it back later.

- **Git** doesn’t copy-paste the whole codebase when branching and tagging, but stores each commit as a code iteration, in an organized structure that resembles a tree. This allows it to have a much smarter merging algorithm, and it almost never bothers you with conflicts, except for those that really need a human decision. As a result, the cost of branching/merging is very low, and people typically branch/merge a lot, therefore one should never directly work on the “master” branch, if they’re not the only developer on the project. Also: unlike its predecessors, Git allows to work and commit without needing to talk with a server, which allows to work on planes, for instance; and it also can work as a decentralized (peer-to-peer) system, although it’s very rarely done that way.

- **Mercurial** is very similar to Git in its concepts (although the syntax of its command-line tool is often different). It is more rarely seen in the industry than Git, but is still very relevant. It is the one used by Facebook, for instance, for its main application.

## The lowdown on Git


A particularity about Git, is that it’s designed to be useable without a central repository (you can pull code from your friend’s computer, and push you work back there, for instance), but not many people use it that way. There is usually a central Git server that the whole team pushes code to and pulls code from; however, that explains why it is often referred as a “decentralized” system.

So that you can work without a server, the commit operation is local, no one other than your computer knows you committed something. You can make several commits however you want, but when you want the server to know about it, you must push them there.
You want to be pulling from the repository often if other people may be working on the same branch as you, because each pull performs a merge operation between the code you didn’t have, and the code you recently committed locally. Therefore, in order to let you push , Git will sometimes demand that you pull first, so that the merge can be done on your computer, and you take care of potential conflicts.

Sometimes, you may have modified 3 files, but there are only two that you wish to include in the commit you’re about the make. Therefore, Git has a notion of “ index”, in which you add your modified files so that they’re included in the next commit you register.

How to configure the remote servers your local repository is talking to? They’re called remotes , and you can configure however many you need. The main one is typically named origin (that’s the name that is setup by default when you clone a project from a remote location in the first place). You can also configure however many branches you need, and name them as you please, and the default one is usually called master.

Some UI tools for Git exist, but Git is able to do so many things, that they don’t represent the magnitude of cases for which you need Git. You really want to learn to use it with the command line. Here are some commands:

$ git clone url_of_your_remote_repository   # Clone a repository from a remote repository  

$ git add file1 file2    # will add those two files to the index if they were modified  

$ git commit -m "Meaningful commit message"   # will commit those two files (locally)  

$ git add .   # will add all of the modified files to the index at once  

$ git commit -m "Other meaningful commit message"   # will commit all of those files together  

$ git push origin master   # send all commit to the remote server

Now, let’d do this again, but by on a branch:

$ git branch my_feature   # Creating the branch  

$ git checkout my_feature   # Changing the codebase so that we're on that branch now  

$ git checkout -b my_feature   # This does the two previous operations in one ;)  

$ git add file1 file2  

$ git commit -m "Meaningful commit message"   # We didn't just commit this on the master branch like last time, but on the my_feature one  

$ git add .  

$ git commit -m "Other meaningful commit message"  

$ git push origin my_feature   # Notice: we're not pushing master anymore, you just create a new remote branch

Next time you want to work on that branch, you should probably do this first:

$ git checkout my_feature   # Just making sure you're currently on the right branch!  

$ git pull origin my_feature   # Pulling what your coworkers have done so far.  

And when you’re done with the whole feature and want to merge it to master:

$ git checkout master  

$ git merge my_feature  

One other pretty neat thing: if you have a non-Git directory in your computer, and you want to turn it into a Git repository, it’s that easy:

$ git init   # You're done!  

$ git remote add origin url_of_your_git_server   # So that you can push your code somewhere.  

When you’re in a Git repository, and want to know which files are modified but not in the index, and those that are modified and are in the index, you can run:

$ git status  

Git provides many more abilities, such as rewriting pieces of the history of the project if you feel the commits were not meaningful enough, displaying the history in visually meaningful ways, …

For instance, you should run this right now, and see how a complex history can be viewed really nicely:

$ git clone [https://github.com/loverajoel/jstips.git](https://github.com/loverajoel/jstips.git)   # You will need a GitHub account for this to work  

$ cd jstips   # changing your directory into the one you just downloaded  

$ git log --graph --pretty=tformat:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%an %cr)%Creset' --abbrev-commit --date=relative  

Cool, right?

## What is the difference between Git and GitHub?

Git is everything we’ve covered so far: a source code management tool, that comes with a command-line tool for its users.

GitHub is one of many services that provide at the same time:

- a Git repository server to push your code to
- a web UI to that view your repositories, with their files and commits
- a number of extra features (managing your team and accesses, …) Two GitHub features you have to get familiarized with are:

- **Forks** : you can **fork** any repository on GitHub, and it will duplicate the repository’s codebase into repository that you own. For instance, if you fork twbs/bootstrap, and your GitHub username is “my_username”, then it will create the my_username/bootstrap repository, and it will remember where it was forked from. Usually, you aren’t allowed to **push** on other people’s repositories, so that will give you a repository that you can push to, since you own it.

- **Pull requests:** once you’ve pushed your code to your repository (or sometimes to a branch of the main repository, if you’re allowed), then you can create a **pull request** towards the main repository’s **master branch**. Somebody in charge of the main repository will review your pull request (potentially asking you to change a couple of things), and **merge** it if it’s suitable to be in the main product.

GitHub has many competitors, two of the main ones being GitLab and BitBucket (which provide very similar services). We chose to make you use GitHub because that’s where most of the industry is (that way, you’ll be able to interact with them on their open-source projects), and it’s also where tech recruiters typically go check out to see what you’ve been up to.

Some interesting links about Git

- https://try.github.io: an interactive tutorial for beginners.
- https://help.github.com/articles/good-resources-for-learning-git-and-github/: a list of resources about Git, curated by GitHub.
- http://nvie.com/posts/a-successful-git-branching-model/: once you master the technical tool, you have many ways to organize your branches according to your project. This very notorious article from 2010 introduces git-flow , a detailed proposal for organizing collective work with Git that is still the most common today. You should talk about that each time you start a collaborative project using Git.
- http://semver.org: now that you can give version numbers to your code iterations, how should you number them? Semantic versioning is the most used versioning scheme.
- Git from the inside out
- Learn git branching

**All of your school projects must make proper use of Git, and must be pushed to your GitHub account.**

## Resources

Resources to learn Git
About READMEs
How to write a Git commit message
Resources for advanced tasks (Read only after finishing the mandatory tasks):

Learning branching
Effective pull requests and other good practices for teams using GitHub
Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

## General
- What is source code management
- What is Git
- What is GitHub
- What is the difference between Git and GitHub
- How to create a repository
- What is a README
- How to write good READMEs
- How to commit
- How to write helpful commit messages
- How to push code
- How to pull updates
- How to create a branch
- How to merge branches
- How to work as collaborators on a project

Which files should and which files should not appear in your repo

## Copyright - Plagiarism

- You are tasked to come up with solutions for the tasks below yourself to meet with the above learning objectives.
- You will not be able to meet the objectives of this or any following project by copying and pasting someone else’s work.
- You are not allowed to publish any content of this project.
- Any form of plagiarism is strictly forbidden and will result in removal from the program.
## Requirements
## General

A README.md file at the root of the alx-zero_day repo, containing a description of the repository

A README.md file, at the root of the folder of this project (i.e. 0x03-git), describing what this project is about

Do not use GitHub’s web UI, but the command line to perform the exercise (except for operations that can not possibly be done any other way than 
through the web UI). You won’t be able to perform many of the task requirements on the web UI, and you should start getting used to the command line for simple tasks because many complex tasks can only be done via the command line.
Your answer files should only contain the command, and nothing else

## More Info
#### Basic usage

At the end of this project you should be able to reproduce and understand these command lines:

- $ git clone <repo>
- $ touch test
- $ git add test
- $ git commit -m "Initial commit"
- $ git push origin main
  
  
## Quiz questions

Great! You've completed the quiz successfully! Keep going! (Show quiz)
  
Tasks

  ## 0. Create and setup your Git and GitHub account

**Step 0 - Create an account on GitHub [if you do not have one already]**

You will need a GitHub account for all your projects at ALX. If you do not already have a github.com account, you can create an account for free here

Step 1 - Create a Personal Access Token on Github
To have access to your repositories and authenticate yourself, you need to create a Personal Access Token on Github.

You can follow this tutorial to create a token.

Once it’s created, you should have a token that looks like this:



Step 2 - Update your profile on the Intranet
Update your Intranet profile by adding your Github username here

If it’s not done the Checker won’t be able to correct your work



Step 3 - Create your first repository
Using the graphic interface on the github website, create your first repository.

- Name: alx-zero_day
- Description: I'm now a ALX Student, this is my first repository as a full-stack engineer
- Public repo
- No README, .gitignore, or license


Step 4 - Open the sandbox

On the intranet, just under the task, click on the button  and run to start the machine.

Once the container is started, click on  to open a shell where you can start work from.

Step 5 - Clone your repository

On the webterm of the sandbox, do the following:

- Clone your repository
- root@896cf839cf9a:/# git clone https://{YOUR_PERSONAL_TOKEN}@github.com/{YOUR_USERNAME}/alx-zero_day.git                  
- Cloning into 'alx-zero_day'...
- warning: You appear to have cloned an empty repository.       
- Replace {YOUR_PERSONAL_TOKEN} with your token from step 1

Replace {YOUR_USERNAME} with your username from step 0 and 1

Step 6 - Create the README.md and push the modifications

Navigate to this new directory. Tips

  root@896cf839cf9a:/# cd alx-zero_day/

  root@896cf839cf9a:/alx-zero_day#

  Create the file README.md with the content My first readme. Tips

  root@896cf839cf9a:/alx-zero_day# echo 'My first readme' > README.md                                                                 

  root@896cf839cf9a:/alx-zero_day# cat README.md                                                                                      

  My first readme                                                                                                                       

  Update your git identity

  root@896cf839cf9a:/alx-pre_course# git config --global user.email "you@example.com"

  root@896cf839cf9a:/alx-pre_course# git config --global user.name "Your Name"

  Add this new file to git, commit the change with this message “My first commit” and push to the remote server / origin

  root@896cf839cf9a:/alx-zero_day# git add .

  root@896cf839cf9a:/alx-zero_day# git commit -m 'My first commit'

 - [master (root-commit) 98eef93] My first commit
 - 1 file changed, 1 insertion(+)
 - create mode 100644 README.md

  root@896cf839cf9a:/alx-zero_day# git push                                                                                           

  Enumerating objects: 3, done.                                                                                                         

  Counting objects: 100% (3/3), done.                                                                                                   

  Writing objects: 100% (3/3), 212 bytes | 212.00 KiB/s, done.                                                                          

  Total 3 (delta 0), reused 0 (delta 0)                                                                                                 

  To https://github.com/{YOUR_USERNAME}/alx-zero_day.git                                                                                       
 
  * [new branch]      master -> master              

  Good job!

You pushed your first file in your first repository of the first task of your first ALX School project.

You can now check your repository on GitHub to see if everything is good.

Repo:

- GitHub repository: alx-zero_day
- File: README.md
    
## 1. Repo-session

Create a new directory called 0x03-git in your alx-zero_day repo.

Make sure you include a not empty README.md in your directory:

  at the root of your repository alx-zero_day

  AND in the directory 0x03-git

  And important part: Make sure your commit and push your code to Github - otherwise the Checker will always fail.

Repo:

- GitHub repository: alx-zero_day
    
2. Coding fury road

  For the moment we have an empty project directory containing only a README.md. It’s time to code!

  Create these directories at the root of your project: bash, c, js

  Create these empty files:

  - c/c_is_fun.c
  - js/main.js
  - js/index.js

  Create a file bash/alx with these two lines inside: #!/bin/bash and echo "ALX"

  Create a file bash/school with these two lines inside: #!/bin/bash and echo "School"

  Add all these new files to git

  Commit your changes (message: “Starting to code today, so cool”) and push to the remote server

  Repo:

- GitHub repository: alx-zero_day
- Directory: 0x03-git
- File: bash/alx, bash/school, c/c_is_fun.c, js/main.js, js/index.js
    
## 3. Collaboration is the base of a company

A branch is like a copy of your project. It’s used mainly for:

  adding a feature in development

  collaborating on the same project with other developers

  not breaking your entire repository

  not upsetting your co-workers

  The purpose of a branch is to isolate your work from the main code base of your project and/or from your co-workers’ work.

  For this project, create a branch update_script and in this branch:

  Create an empty file named bash/98

  Update bash/alx by replacing echo "ALX" with echo "ALX School"

  Update bash/school by replacing echo "School" with echo "The school is open!"

  Add and commit these changes (message: “My personal work”)

  Push this new branch Tips

  Perfect! You did an amazing update in your project and it’s isolated correctly from the main branch.


  Ho wait, your manager needs a quick fix in your project and it needs to be deployed now:

  Change branch to main

  Update the file bash/alx by replacing echo "ALX" with echo "ALX School is so cool!"

  Delete the directory js

  Commit your changes (message: “Hot fix”) and push to the origin

  Ouf, hot fix is done!

Repo:

- GitHub repository: alx-zero_day
- Directory: 0x03-git
- File: bash/alx, bash/school, bash/98
    
## 4. Collaboration: be up to date

  
  Of course, you can also work on the same branch as your co-workers and it’s best if you keep up to date with their changes.

  For this task – and only for this task – please update your file README.md in the main branch from GitHub.com. It’s the only time you are allowed to 
  update and commit from GitHub interface.

  After you have done that, in your terminal:

  Get all changes of the main branch locally (i.e. your README.md file will be updated)

  Create a new file up_to_date at the root of your directory and in it, write the git command line used

  Add up_to_date to git, commit (message: “How to be up to date in git”), and push to the origin

  Repo:

- GitHub repository: alx-zero_day
- Directory: 0x03-git
- File: README.md, up_to_date
