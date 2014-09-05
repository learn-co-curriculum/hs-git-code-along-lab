---
  tags: git, kids 
  languages: git
  level: 1
  type: lab
---

## Git Workshop

The goals of this workshop is to get you comfortable with git. 

### So let's actually start a project.

* Create a directory for the project on your computer that will hold your code and `cd` into it:

`mkdir my_code`
`cd my_code`

* Now that we're in the project, we need to initialize a new git repository. 

`git init` 

* This creates a `.git` file in your new git project, which contains all the information git needs to sync the local version of your project (the one on your personal computer), with the version on github.com

* Now create a `README.md` file. A README is a considered best practices, and we should make one for every project we work on. It tells anyone that is looking at your project exactly what it is that they're looking at, and potentially how to use it. Notice all the instructions for this code-along are in a `README.md`. Let's make a `README.md`, open it, and include a few instructions.

`touch README.md`
`subl README.md` 

"Here is my personal repository of ruby code."

* Now let's see if git noticed that we made changes to our `README.md`. 

`git status` 

* Now that we've finished editing our README, we want our file to be staged for commit. 

`git add <file-name>` 

* And commit

`git commit -m "I added a readme"`.

The `-m` is saying "I'm going to include a commit message here". 

* Now let's go ahead and make a `strings.rb` document.

`touch strings.rb`
`subl strings.rb`

* Remember the string methods we learned last week? Let's write a few lines of code to `puts` some strings and string methods (maybe something like `puts "i love ruby".upcase`). Now add and commit this.

`git add <file-name>`
`git commit -m "created strings.rb"`

* `git log` is a powerful command that lets you see the history of all your commits. That's also part of why we like to include commit messages. Imagine you're working on a project with 5 other developers. Wouldn't you want them to be able to read a clear and concise message as to what you added to the code base and why? The 7 characters in front of your commit message is the SHA. The SHA is basically the unique identifier of that specific commit.

* So far, we've been working on what's considered the `master` branch. Master should always be the stable working version of your code. You never want to break master. So where do you do your work if you have to keep master stable? We create feature branches. First, let's confirm we're on master. `git branch` is the command to check your branch location. It's like `pwd` for git.

Now Let's create our new feature branch, and then switch to it. To do this, we type `git checkout -b <branch-name>`. Let's name this branch "numbers", because we're going to add some numbers to our doc. Now if we check the branch, it should tell us we're on the numbers branch.

* This branch split off from master after we created the readme and strings.rb, so both of those files will exist on my new branch. Now let's make some changes to strings.rb. Let's add some mathematical equations (maybe something like `puts 1+1`). Then we'll add and commit these changes.

`git add <file-name>`
`git commit -m "Added some maths"`

* Now let's go back to master `git checkout master` and open `strings.rb`. You'll notice your maths are gone! No worries. Those changes only exist on the `numbers` branch.

* Since our math additions are complete and looking good, let's merge those files in to the master branch. To do this, we need to make sure we're on the master branch. Any time you're merging a feature branch into master, you'll want to be on master. 

`git merge <branch-name>`

Now if we reload strings.rb in the browser, we should see the numbers and mathematical equations that we added. Do you see them?! Fantastic.

