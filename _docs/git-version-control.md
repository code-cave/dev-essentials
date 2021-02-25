## Git Version Control  
Learning to share code is about as important as learning how to write it.  
It's not useful to write a whole lot of code that can't be shared or managed.  
For that reason, learning how to use version or source control is necessary.  
Git is the top choice for version control today, so that's what will be used.  

Learn the basics:
- Initializing:  
  `$ git init` to create a Git repository under the current directory  
  It's more common to just create a repo in GitHub and clone it like below  
  than to do an init and set the remote repo url and push, though
- Cloning:  
  `$ git clone https://github.com/some-org/some-repo.git` to obtain a copy of some-repo
- Branching:  
  `$ git branch some-branch` to create a working branch to make code changes in
- Checkout:  
  `$ git checkout some-branch` to checkout (switch to) the specified branch to work on  
  `$ git checkout -b some-branch` to create a branch and check it out in one command
- Adding:  
  `$ git add some-file.txt ...` to stage specific changed files, or  
  `$ git add .` to stage all changed files
- Committing:  
  `$ git commit` (pops up text editor) to commit added files into a "saved" unit  
  in Git called a commit and provide a description message for the commit  
  `$ git commit -m "Some message"` to create a commit with a message without having  
  to go into the editor
- Merging:  
  `$ git merge some-branch` (while on master) to merge the commits of some-branch to  
  the master (main) branch
- Pushing:  
  `$ git push` to push the current branch to the remote repository (GitHub repo)
- Pulling:  
  `$ git pull` to pull in (merge) the changes in the remote repository branch to the  
  checked out local branch of the same name - to get the changes someone else pushed  

Of course, there are tons of other commands to do cool things in Git, but these are  
the main commands used for doing normal everyday work.

