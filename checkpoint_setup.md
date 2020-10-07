
# Checkpoint Setup

At the end of this guide, you should have two separate folders, `intro-tutorials` and `mdst_tutorials`. `intro-tutorials` is a clone (copy) of this repo (owned by MDST) and will have all the files you need for the tutorials. `mdst_tutorials` is your own public repo where you will be uploading your completed checkpoints for us to review.
 

### 1. Clone the MDST tutorial repository
1.1 Pick a place on your computer to put this repo (Desktop, Documents, etc.)\
1.2 Navigate there in your terminal (WSL/Ubuntu for Windows users)\
1.3 Run `git clone https://github.com/MichiganDataScienceTeam/intro-tutorials`

Cloning the repo downloads all of the files from [online](https://github.com/MichiganDataScienceTeam/intro-tutorials) to your computer. They will be in a new directory called `intro-tutorials`, located in the folder from which you ran git clone.
> Be careful to not make edits in this repository! We will have you pull to get updates we make, and you will get errors if you have made changes locally (on your computer).

### 2. Make a new local repository
The way you will be turning in the checkpoints is by uploading your work to your own github repo and linking that repo to us. This repo is _separate_ from the MDST repo, so to submit the files we provide (e.g. `tutorial1/python_exercises.py`), copy them from the `intro-tutorials` folder to the new folder you create in this step.


2.1 Make and change into a new folder `mdst_tutorials` where you want to work on your checkpoint (use `mkdir`)\
2.2 Run `git init`

This creates a new git repository in the `mdst_tutorials` folder. You can always tell when you're in a git repo because there will be a hidden `.git/` folder (verify with `ls -a`)

The git repository you made here is saved only to your computer. Next we want to connect it to a remote (online) repo.

### 3. Make a remote repo
You should already have a github account. If not, make one!

3.1 On github.com, find the button to make a new repository. Click on it.\
3.2 Give the repo a name and description and make it public. **Do not** initialize the repo with a README or .gitignore (we will be importing an existing repository)\
3.3 Finish creating the repository


You should be able to see your new repository on your github profile, but there's nothing there! We need to link the local repo we created in step 2 to this repo.

### 4. Link repos
4.1 Open your repo from step 3 and copy the link (should have format https://<i></i>github.<i></i>com/<username\>/<repo name\>.git)\
4.1 Navigate back to the first folder, where you ran `git init`\
4.2 Run `git remote add origin LINKFROMABOVE`

Now your repositories are linked! You can now commit and push freely to your repo.


### 5. Git refresher
Since we're already here, let's review how to commit and push to git. Recall that a commit is like a checkpoint -- it saves the state of your files at a given instance. Pushing uploads your local changes/commits to your online repository.

In your own git repo, run `git status` to check your status. There will be 2-3 categories:
* _Changes not staged for commit_ -- these are files which have been changed and not committed
* _Changes to be committed_ -- these are also files which have been changed and not committed, _but_ you have marked them as 'to-be-committed'
* _Untracked files_ -- these are files which have never been commited
> If there are files in the _untracked files_ section which you know you will never commit, you can have them stop showing up with a `.gitignore` file. Create this file inside your repo (using any editor) and include each pattern to ignore on its own line. For example, to ignore all `.txt` files, your gitignore would include the line `*.txt` (the `*` symbol matches anything that comes before a .txt)

To mark files as 'to-be-committed', run `git add FILENAME` to add them to the _staging area_. This tracks which file(s) are being updated with a single commit. These files you add will move from _changes not staged for commit_ to _changes to be committed_.

Once you have added all the files you want to save at once, run `git commit`. This will open a terminal text editor, where you will write a commit message (should be a short description of changes made).
>Vim: hit `i`, type your message, hit `esc`, then hit `:x`\
>Nano: type your message, hit `CTRL-O`, hit `ENTER`, then hit `CTRL-X`

After committing, if you run `git status again`, the _changes to be committed_ section will disappear (those files have now been committed). The rest will look the same.

Finally, to push your changes, run `git push -u origin master`. After providing your login information, you will be able to refresh the github page and see your changes!

> If you have authentication errors, you may need to create an SSH key. See [this guide](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) for help.
