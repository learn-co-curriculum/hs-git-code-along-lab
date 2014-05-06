---
  tags: git, kids 
  languages: git
---

##Git Workshop

The goals of the workshop are to get you comfortable with git. Git is a distributed version control and source code management system. 

So what does that mean? Version control is a way to save the history of your work. At every point while writing your code that something works successfully, you'll want to make sure to save that point. Git keeps track of all of those moments that you save. Imagine you keep working, and suddenly EVERYTHING is broken. What would you do? If you used git and saved your work along the way, you could essentially rewind your code history to a working version.

We use [Github](https://github.com/) for all of our changes. Github is a web-based software for hosting your code, as well as version control, through git. We're going to be using the accounts we made during environment setup for all of our lab work, as well as any projects we may be working on.

###So let's actually start a project.

1. First things first, we need to create a project directory on our computers that will hold our code. It's considered best practice to hold single projects in their own directories. You wouldn't want to just hold everything floating separately on your desktop. 
`mkdir my_website`
`cd my_website`

2. Now that we're in the project, we need to initialize a new git repository. A repository is the git version of our project directory. We have to initialize it on our own computer so that git can start tracking. We're basically saying "Hey computer, this is a new git project." `git init` also creates a `.git` file in your new git project, which contains all the information git needs to sync the local version of your project (the one on your personal computer), with the version on github.com
`git init`

3. Now we're going to create a `README.md` file. A README is a considered best practice for every practice. It tells anyone that is looking at your project exactly what it is that they're looking at, and potentially how to use it. Notice all the instructions for this code-along are in a `README.md`. We'll also open this `README.md` and include a few instructions...
`touch README.md`
`subl README.md`

"This is my personal portfolio. This site will include contact information, a personal bio, and links to all of my work"

4. Now let's see if git noticed that we made changes to our `README.md`. `git status` tells us what files we have changed. It keeps track of files in two different ways, files that are not staged for commit, and files that are staged for committing. All git commands are prefaced with the word `git`. It's how our computer knows exactly what program we're talking to.

5. We have finished editing our read me, so we want our file to be staged for commit. `git add <file-name>` is how we stage a file. Staging a file for commit is sort of like getting the actors for a play ready behind the curtain. They have to hang out for just a few more minutes before they're all set to go. But what if we did `git add <file-name>` but we actually realize we want to make some changes? That's ok. Just go ahead a make your changes. If after you make those changes, you enter `git status` you'll notice the file is no longer staged for commit. It's like that actor suddenly had a wardrobe malfunction and had to run back to his dressing room to get it fixed. Just enter `git add <file-name>` one last time. 

6. So this time you're actually ready to save that version of your file. `git commit -m "the reason I'm saving this goes here"`. We're actually committing the file now. A commit is just like saving your file. It's like taking a snapshot of your code at that exact moment in time. Git keeps track of all the commits you make, sort of like Microsoft word track-changes does. When you edit word file with track-changes, you always enter a comment of why you're changing that line. We do the same thing with commits. The `-m` is saying "I'm going to include a commit message here". 
`git commit -m "I added my personal site readme"`

7. Because this is a new project, we'll need to set up our remote repository, the version located on github.com. We need to go https://github.com, and click the `+` located in the top right corner. We'll select to create a new repository. We'll be directed to a page that let's us fill out information about our new repository. I like to keep my repository name consistent with what I named my directory on my computer. In this case I'd name it "personal_site". The description is optional, but I'll go ahead and fill out "This is my online portfolio". You can now either chose to make your repositories public or private. I typically make all of my repositories public. Open source contributions are incredibly valuable in the tech community. It allows other developers to learn from your work. It also creates a nice history of your work, so potentially down the line when you're looking for internships or jobs, employers can get a good look at all the code you've written. You also have to pay for private repositories, so we'll go ahead and keep it public. And now we'll click `Create Repository`

8. At the top, next to "Set up in Desktop", you'll see a line that starts with git@github.com....That's the remote location for our project. Let's copy that. We need to set our local version of our project to point to that. In terminal in the directory for our project, we'll enter
`git remote add origin git@github.com:vicfriedman/my_site.git`
`remote` tells our computer "we're adding the remote location"
`origin` is the orginal remote repository, and we're telling it to be `git@github.com:vicfriedman/my_site.git`

9. Our `README.md` is still only located on our computer. Let's go ahead and put it up on the remote version. 
`git push -u origin master`
This is the only time we'll enter this exact command, becuase it's the first time we're pushing our code to the server for this particular project. `push` is saying, go one code, get on up there. The `-u` means "upstream", which is just saying to go up to the github repository. 

10. Let's go ahead and make the `index.html` page of my site.
`touch index.html`
`subl index.html`

11. Now that I added some basic HTML and added a picture of a cat to the page, let's add, commit, and push this file up.
`git add <file-name>`
`git commit -m "created index.html"`
`git push`

12. `git log` is a powerful command that lets you see the history of all your commits. That's also part of why we like to include commit messages. Imagine you're working on a project with 5 other developers. Wouldn't you want them to be able to read a clear and concise message as to what you added to the code base and why? The 7 characters in front of your commit message is the SHA. The SHA is basically the unique identifier of that specific commit.

13. So far, we've been working on what's considered the `master` branch. Master should always be the stable working version of your code. You never want to break master. This is considered a standard workflow, and is especially important to remember if you are working on a project with more than one developer. So where do you do your work then if you have to keep master stable? We create feature branches. First, let's confirm we're on master.
`git branch` Is the command to check your branch location. It's like `pwd` for git.
So now let's create our new feature branch, and then switch to it. 
`git checkout -b <branch-name>` I'm going to name my branch "header", becuase I'm going to work on a header feature for my site `git checkout -b header`. Now if we check the branch, it should tell us we're on the header branch.

14. This branch split off from master after I had already created my readme and my index.html, so both of those files will exist on my branch. Now let's add some things to my index.html. If we open it in the browser, we can see my name appears. Now, let's say I want to add a sub-header and a description, but I don't have enough time right now. I want to save my place though, so we'll go ahead and add, commit, and push these changes to a remote version of my branch.
`git add <file-name>`
`git commit -m "started working on header"`
`git push origin header`
My header branch didn't previously exist on github, so we have to explicitly tell git to push to the remote location, and the branch header. 

15. So let's go back to master `git checkout master` and open `index.html`. You'll notice my name no longer appears in the browser. Those changes only exist on my `header` branch.

16. So now I decide I don't want to make any more changes to my header for the time being. We'll consider that feature complete. We need to merge those files in to master. To do this, we need to make sure we're on the master branch. Any time you're merging a feature branch into master, you'll want to be on master. 
`git merge <branch-name>`
Now if we reload index.html in the browser, we should see my name.

17. So now that we've learned how to start and work on our own projects, let's learn how to work on someone else's. Let's go to https://github.com/flatiron-school-curriculum/find-missing-pet. There are two options for working on a project with someone else: Forking and cloning. Cloning means your going to make an exact replica of the project on your computer, and it's going to point to that specific remote location. If you committed a change on master, it would show on master in their repository. Forking creates an exact replica of the project in your github account.

18. Let's fork this lab https://github.com/flatiron-school-curriculum/find-missing-pet by clicking the `Fork` button in the top right corner. When we do that, we notice the location of the new forked repository is vicfriedman/find-missing-pet. So now that it exists on my github account, we have to clone the project to get it on my computer.
`git clone git@github.com:vicfriedman/find-missing-pet.git`

19. Now that we have it up locally, we can cd into the project `cd find-missing-pet` and begin working on the lab! 

<!-- After they complete the lab... -->

20. Now that you completed your lab, make sure it's all pushed up to your version of the repository on github. And now we need to create a pull request. A pull request is the best practice for submitting contribution of work to an open source project. To create a pull request, go to your version of the repository on your github account. We'll click the green button in the top left corner. On the next page, we'll want to enter a comment for the pull request, "completed lab, all tests pass" and click submit. This is how I'll be able to review your work and give you feedback on your code. 



