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

* Create a `README.md` file to tell anyone who is looking at your project exactly what it is that they're looking at.

`touch README.md`
`subl README.md` 

* Type something into it. Maybe: "Here is my personal repository of ruby code."

* Now let's see if git noticed that we made changes to our `README.md`. 

`git status` 

* We've finished editing our README, now we want our file to be staged for commit. 

`git add <file-name>` 

* Then commit.

`git commit -m "I added a readme"`.

The `-m` is saying "I'm going to include a commit message here". 

* Now let's go ahead and make a `strings.rb` document.

`touch strings.rb`
`subl strings.rb`

* Remember the string methods we learned last week? Write a few lines of code in the doc to `puts` some strings and string methods (maybe something like `puts "i love ruby".upcase`). Now add and commit this.

`git add strings.rb`
`git commit -m "created strings.rb"`

* Let's take a look at our git commit history

`git log` 

* See those 7 characters in front of your commit message? That is the SHA. The SHA is basically the unique identifier of that specific commit. Kind of like an address that you would use to find that specific snapshot of your code.

* We've been working in master branch. Actually let's confirm that.

`git branch`

* On master? Good. But now we want to add a new feature. Create a feature branch. You can create a new branch and move to that branch all in one command like this:

`git checkout -b <branch-name>`

* Let's name this branch "numbers", because we're going to add some numbers to our doc. First confirm which branch you are on.

`git branch`

* It should tell us we're on the numbers branch.

* Now let's make some changes to strings.rb. Add some mathematical equations (maybe something like `puts 1+1`). Then add and commit these changes.

`git add strings.rb`
`git commit -m "Added some maths"`

* Now let's go back to master `git checkout master` and open `strings.rb`. You'll notice your maths are gone! No worries. Those changes only exist on the `numbers` branch.

* Since our math additions are complete and looking good, let's merge those files in to the master branch. To do this, we need to make sure we're on the master branch. You know how to do that, right? Then merge in the numbers branch.

`git merge numbers`

Now we should see the numbers and mathematical equations that we added. Do you see them?! Fantastic.

