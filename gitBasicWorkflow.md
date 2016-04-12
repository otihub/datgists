# The Basic Git Workflow for adding Gists

## Intro
This gist explains how to add a gist to the `datgists` repo using github-shell or your computer's command line.  Note that it is a super basic overview and git has a lot more functionality then what is described here.
Further, this gist assumes you have setup git or github-desktop, linked your profile, and understand some of the basic git jargon.

## General Workflow

`git clone https://github.com/teamName/repoName.git > git add file.md > git commit -m 'some message' > git pull > git push`

## Steps
1. If you are using git-shell open github-desktop to load the tools for github-shell.
2. Once github-desktop is open and the tools are loaded, open github-shell.
3. If you have already *cloned* the repo to your computer skip to step `7.` otherwise, go on to step `4.`
4. In github-shell navigate where you want the repository to be located on your computer by typing: `cd path/to/location/on/desktop`  (instead of typing the filepath you can drag it in from the window)
5. Find the link to the *datgist* repo in github and copy it (note that it is not the actual url but the link next to the `HTTPS` box).
6. Next, in github-shell, type `git clone` and paste the repo link so it looks something like this: `git clone https:/https://github.com/teamName/repoName.git`
7. In github-shell navigate to the repo by typing: `cd path/to/your/git/repo` (or by typing: `cd ` and dragging the folder in)
8. Once in the repo, remember to `git pull` often! This way there will be no conflicts with the remote version (one on github and **ALWAYS PULL BEFORE YOU PUSH!**
9. Now that you pulled in any changes that have been made, add your file to the repo.  Simply copy the file into the repo folder as you would any other file.
10. Once the file is in the repo folder, go to github-shell and add all of the files you have added.  Do this with the command `git add file1.md, file2.txt` etc...
11. `git push` to sync the commit with github, this moves the commit from your local machine to the repo on github

