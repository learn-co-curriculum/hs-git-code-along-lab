---
  tags: git, kids 
  languages: git
  level: 1
  type: lab
---

## Git Workshop

The goals of this workshop is to get you comfortable with git. 

### So let's actually start a project.

* Create a directory for the project on your computer that will hold your code and `cd` into it with the following commands in the terminal:

`mkdir my_code`
`cd my_code`

* Create a `README.md` file to tell anyone who is looking at your project exactly what it is that they're looking at.

`touch README.md`
`subl README.md` 

* Now that we've created a new project, we need to initialize a new git repository to track our changes with:

`git init` 

* Now let's type something into our README. Maybe something like, "Here is my personal repository of ruby code."

* Now let's see if git noticed that we made changes to our `README.md` with:

`git status` 

* We've finished editing our README, now we want our file to be staged for commit. Type:

`git add <file-name>` 

* Then commit with:

`git commit -m "Added a readme"`.

The `-m` is saying "I'm going to include a commit message here". 

* Now let's go ahead and make a `strings.rb` document.

`touch strings.rb`
`subl strings.rb`

* Remember the string methods we learned last week? Write a few lines of code in the doc to `puts` some strings and string methods. Now add and commit this.

`git add strings.rb`
`git commit -m "Added strings.rb"`

* Let's take a look at our git commit history:

`git log` 

* You should see your two commit messages and their unique SHA numbers.

* We've been working in master branch. Actually let's confirm that.

`git branch`

* On master? Good. But now we want to add a new feature. Let's create a new branch called `numbers`. You can create a new branch and move to that branch like this:

`git branch numbers`
`git checkout numbers`

* Now let's see which branch we are on.

`git branch`

* It should tell us we're on the numbers branch.

* Now let's make some changes to strings.rb. Go ahead and add some math equations to your file. Now check the status of your file with 

`git status`

* Then add and commit these changes.

`git add strings.rb`
`git commit -m "Added some math"`

* Now let's go back to the master branch `git checkout master` and open `strings.rb`. You'll notice your math is gone! No worries. Right now those changes only exist on the `numbers` branch, but we can pull them into your master branch.

* Since our math additions are complete and looking good, let's merge those files in to the master branch. First check to see if you are on the master branch (remember that command?). Then merge in the numbers branch with this command:

`git merge numbers`

Now we should see the numbers and mathematical equations that we added. Do you see them?! Fantastic.

