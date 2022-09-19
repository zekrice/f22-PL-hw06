# Setup Your Individual Homework #6 Repository

## Viewing your class repo(s) on GitHub

At the following page, you should see an *instructor* repo for each
homework and the project. You will need to create an empty *individual/team* repo for each assignment,
where you can submit your work. All of these repos are private,
so you'll need to log in to Github first.

[https://github.com/mines-csci400](https://github.com/mines-csci400)

## Setup: creating your user/team repository

*First*, make sure you have ssh keys set up (see initial setup instructions on Canvas) and your global configuration set with your name, email, and "main" as the default initial branch (that's important!).

1. create a new, private, empty repo on GitHub in the mines-csci400 organization for your work named f22-user-MinesEmail-hw06 where MinesEmail is your Mines email without the @mines.edu part. If your email were `smith@mines.edu` you'd have a private repo in mines-csci400 named `f22-user-smith-hw06`.
2. On your local machine, where you want your repo to be located (this will be the parent folder of your repo folder), do these commands (if you alter the first line, you can use cut-paste for this):

```
    EMAIL=MinesEmail
    git clone git@github.com:mines-csci400/f22-assignment-hw06.git
    mv f22-assignment-hw06/ f22-user-${EMAIL}-hw06
    cd f22-user-${EMAIL}-hw06
    git remote add upstream git@github.com:mines-csci400/f22-assignment-hw06.git
    git remote remove origin
    git remote add origin git@github.com:mines-csci400/f22-user-${EMAIL}-hw06.git
    git push -u origin main
```

This series of commands copies the lab repo onto your local machine, has you rename the folder to match your repo's name, then has you switch the remote so that now your local repo will see your own repo on GitHub as its origin, with the original lab repo viewed as an upstream repo. This way when you push, it goes to your individual repo on GitHub, not the original hw06 template repo.

Note, if you mess up, you do not have permission to write to the hw06 template repo so it will simply be rejected when you push. You can recover from that! Simply perform the three `git remote add` commands in the order they are listed above, in your local repo, and you will fix it and be able to push to your GitHub repo.

Double-check that:
1. You have created the repo in the course organization and not
   under your own github account or under another organization.
2. Your github repo is correctly named (f22-user-MinesEmail-hw06, where MinesEmail is your Mines email without the @mines.edu part).
3. Only you (and the instructor/TA) can access your github repo: your repo is in the course organization, private, and you are the only collaborator.
4. The remote named `origin` points to your user repo and the remote named `upstream` points to the assignment template repo. `git remote -v` will show you what your remotes point to.

## Add Name Information

Next, edit the plain text file AUTHOR to hold your name and CWID on 1 line, just name and CWID, comma separated, like so:
```
Jyn Jones, 12312123
```
## Info about Git remotes

Git *remotes* allow you to push/pull to/from other repositories.
To look at your current remotes:
```
git remote -v
```
The default remote is called `origin`, and it should point to your
repository:
```
git@github.com:mines-csci400/f22-user-MinesEmail-hw06.git
```

## Obtaining assignment skeleton code

If you have not yet brought in the instructor's skeleton code
for this assignment, you should create a remote that points to the
corresponding assignment repository:
```
git remote remove upstream
git remote add upstream git@github.com:mines-csci400/f22-assignment-hw06.git
git pull upstream main --allow-unrelated-histories --no-edit
```

Any time after this, if for some reason you need to bring in
the instructor's version of the assignment again (e.g., due to
bug fixes, hints, clarifications, etc.):
```
git pull upstream main --no-edit
```
(no need for `--allow-unrelated-histories` after the initial pull).

## Working on the assignment

Please add a .gitignore file so that only the base files and the requested files are included
in your repository.

You can then edit the files as
needed to complete the assignment, and make as many local
commits as needed, using
```
git commit -a -m "put your commit message here"
```

Note that commits are *local*. You will need to *push* the commits
to GitHub in order to make them available to others.

At any time, you can look at the status of your local repo
by doing
```
git status .
```
This will tell you whether you have modified files that need to be
committed, and whether you have local commits which haven't yet
been pushed.

## Submitting the assignment

To make your commits available on GitHub, you should
do the following to push to your user repo:
```
git push 
```

If you get an error about a *rejected* push, that probably means
you pushed code from a different machine/source repo, and you'll need to bring in those changes before you can push:
```
git pull
```

## Checking that the assignment has been properly submitted

Please check (and double-check) that your assignment has been
pushed properly to GitHub. You can do this easily by going
to your repo's page on GitHub, and confirming that you see
the list of your commits, and that the submitted files
look as expected.

[https://github.com/mines-csci400](https://github.com/mines-csci400)

