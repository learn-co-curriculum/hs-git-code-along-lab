

## Git Workshop

The goal of this workshop is to get you comfortable with git. 

### So let's actually start a project.

* Create a new directory for this project called `git_practice` and `cd` into it. 


* Are you in your new `git_practice` directory? Great! Now that we've created a new project, we need to initialize a git repository to track our changes. To do this type:

`git init` 

* Now let's add a `README.md` file to tell anyone who is looking at the project exactly what it is that they're looking at:

`touch README.md` 

* Open up your README in an editor and add this description: "This is my first time using git!".

* Now let's see if git noticed that we made changes to our `README.md` with:

`git status` 

* We've finished editing our README, now we want our file to be staged for commit. Type:

`git add README.md` 

* Then commit with:

`git commit -m "Added a readme"`.

The `-m` flag is short for message. We need to add it before the commit message.

* Now let's go ahead and make a `git_practice.rb` document and open it up.

`touch git_practice.rb`

* Before we even add any code let's just go ahead and add and commit these files:

`git add git_practice.rb` 
`git commit -m "Added git_practice.rb"`.

* Now let's add some code to our git_practice.rb. Write some code that asks a user for their name and then tells them hello. Once you've finished adding this code `add` and `commit` these changes.

* Let's check our `git status`. It should tell you that you are up to date and there is nothing new to commit. Now let's take a look at our git commit history with:

`git log` 

* You should see your two commit messages and their unique SHA numbers.

* Ok, we've just received a request for a new feature in our program that asks users for their age. Before we add this feature let's create a new branch where we will do our work and track our changes.

* We've been working in master branch. Actually let's just confirm that we are on the master branch with this command:

`git branch`

* On master? Good. Now let's add a new age branch with these commands:

`git branch age`
`git checkout age`

* Now let's see which branch we are on.

`git branch`

* It should tell you you are on the age branch.

* Now add a feature in `git_practice.rb` that takes in your user's age and tells them how old they are in dog years. (Not sure how to calculate dog years? Ask your neighbor.) 

* Check the status of your file. Then add and commit these changes.

* Now let's go back to the master branch `git checkout master` and take a look at `git_practice.rb`. 

* Your new feature is gone! No worries. Right now those changes only exist on the age branch, but we since we are done with that feature for now (And we know it works, right? Did you test it?) you can merge those changes into the master branch.

* First make sure you are on your master branch (remember the command to check which branch you are on?). Then merge in the changes on your age branch with this command:

`git merge age`

Now you should see all the code that you added asking a user for their name AND their age. Do you see both?! Fantastic.


<p data-visibility='hidden'>View <a href='https://learn.co/lessons/hs-git-code-along-lab' title='Git Workshop'>Git Workshop</a> on Learn.co and start learning to code for free.</p>
