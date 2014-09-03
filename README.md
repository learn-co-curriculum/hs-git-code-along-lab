---
  tags: git, kids 
  languages: git
  level: 1
  type: lab
---

## Git Workshop

The goals of this workshop is to get you comfortable with git. Git is a distributed version control and source code management system. 

So what does that mean? Version control is a way to save the history of your work. At every point while writing your code that something works successfully, you'll want to make sure to save that point. Git keeps track of all of those moments that you save. Imagine you keep working, and suddenly EVERYTHING is broken. What would you do? If you used git and saved your work along the way, you could essentially rewind your code history to a working version.

### So let's actually start a project.

1. First things first, we need to create directory for our project on our computers that will hold our code. It's considered best practice to hold single projects in their own directories. You wouldn't want to just have everything floating separately on your desktop. Let's make a directory for our project and `cd` into it:

`mkdir my_code`
`cd my_code`

2. Now that we're in the project, we need to initialize a new git repository. A repository is the git version of our project directory. We have to initialize it on our own computer so that git can start tracking our work. We're basically saying "Hey computer, this is a new git project." Let's do that:

`git init` 

`git init` creates a `.git` file in your new git project, which contains all the information git needs to sync the local version of your project (the one on your personal computer), with the version on github.com

3. Now we're going to create a `README.md` file. A README is a considered best practices, and we should make one for every project we work on. It tells anyone that is looking at your project exactly what it is that they're looking at, and potentially how to use it. Notice all the instructions for this code-along are in a `README.md`. Let's make a `README.md`, open it, and include a few instructions...

`touch README.md`
`subl README.md` 

"This is my personal portfolio. This site will include contact information, a personal bio, and links to all of my work"

4. Now let's see if git noticed that we made changes to our `README.md`. `git status` tells us what files we have changed. It keeps track of files in two different ways, files that are not staged for commit, and files that are staged for committing.

5. Now that we've finished editing our README, we want our file to be staged for commit. `git add <file-name>` is how we stage a file. Staging a file for commit is sort of like getting the actors for a play ready behind the curtain. They have to hang out for just a few more minutes before they're all set to go. But what if we did `git add <file-name>` but we actually realize we want to make some changes? That's ok. Just go ahead a make your changes. And after you make those changes, enter `git status` you'll notice the file is no longer staged for commit. It's like that actor suddenly had a wardrobe malfunction and had to run back to his dressing room to get it fixed. Just enter `git add <file-name>` one last time. 

6. So this time you're actually ready to save that version of your file. Type `git commit -m "the reason I'm saving this goes here"`. We're actually committing the file now. A commit is just like saving your file. It's like taking a snapshot of your code at that exact moment in time. Git keeps track of all the commits you make, sort of like Microsoft word track-changes does. When you edit a Word file with track-changes, you always enter a comment of why you're changing that line. We do the same thing with commits. The `-m` is saying "I'm going to include a commit message here". 
`git commit -m "I added a readme"`.

7. Now let's go ahead and make the `strings.rb` document.

`touch strings.rb`
`subl strings.rb`

11. Remember the string methods we learned last week? Let's write a few lines of code to puts some strings and string methods (maybe something like `puts "hi".upcase`). Now add, commit, and push this file up.

`git add <file-name>`
`git commit -m "created strings.rb"`
`git push`

12. `git log` is a powerful command that lets you see the history of all your commits. That's also part of why we like to include commit messages. Imagine you're working on a project with 5 other developers. Wouldn't you want them to be able to read a clear and concise message as to what you added to the code base and why? The 7 characters in front of your commit message is the SHA. The SHA is basically the unique identifier of that specific commit.

13. So far, we've been working on what's considered the `master` branch. Master should always be the stable working version of your code. You never want to break master. This is considered a standard workflow, and is especially important to remember if you are working on a project with more than one developer. So where do you do your work then if you have to keep master stable? We create feature branches. 

First, let's confirm we're on master. `git branch` is the command to check your branch location. It's like `pwd` for git.

So now let's create our new feature branch, and then switch to it. To do this, we type `git checkout -b <branch-name>`. Let's name this branch "numbers", because we're going to add some numbers to our doc. Now if we check the branch, it should tell us we're on the numbers branch.

14. This branch split off from master after we created the readme and strings.rb, so both of those files will exist on my new branch. Now let's make some changes to strings.rb. Let's add some mathematical equations (maybe something like `puts 1+1`). Then we'll go ahead and add and commit these changes.

`git add <file-name>`
`git commit -m "Added some maths"`

15. Now let's go back to master `git checkout master` and open `strings.rb`. You'll notice your maths are gone! No worries. Those changes only exist on the `numbers` branch.

16. Since our math additions are complete and looking good, let's merge those files in to the master branch. To do this, we need to make sure we're on the master branch. Any time you're merging a feature branch into master, you'll want to be on master. 

`git merge <branch-name>`

Now if we reload strings.rb in the browser, we should see the numbers and mathematical equations that we added. Do you see them?! Fantastic.

