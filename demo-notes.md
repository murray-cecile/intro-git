## Demo

### Pre-requisites

- Assumes that the user has a GitHub account
- Assumes the user has GitHub Desktop installed 

### Cloning a repository

You can think of cloning as downloading a copy of the project files to your local machine, and we'll start by doing that with the files for today's workshop.

1. Navigate to https://github.com/census-bds/intro-git. This is the repository, or "repo," for today's demo. In this web interface, you can browse through code files and see how they have evolved over time. There is a way to edit files here, but generally people use their preferred text editor or software program on their local computer rather than this interface.

2. In order to add files and make changes to this repository, you need to "clone" the repository. We can do this using a URL we'll grab from the right-hand side of the screen. There's a blue button that says "clone," and when we click on it, we'll see a dropdown menu with a URL underneath the words "Clone with HTTPS." Copy that link.

3. Go to GitHub Desktop and click File > Clone repository. This will bring up a pop up menu where you can paste the link you got from the GitLab website. You will also need to specify where on your local computer you want to save the files you are downloading. This location will be where you will go to add or edit the project files - so, for example, it might be in your Documents drive on a laptop or on a network drive. 

We can use Windows Explorer to take a look at that location now, before we have hit "clone," and we can see there's no file folder called intro_git there.

Once you're ready, hit "clone." You will probably get prompted for some credentials: here, those will be your GitHub username and password. (If you use an internal GitLab, you might use the credentials for your organization, e.g. LDAP.)

4. If the clone was successful, you should be able to see it in two places:

- First, you can see the files in GitHub Desktop. 

- Second, you can see them in Windows explorer.

### Pull, make a change to an existing file, commit, push

Let's say we want to make a change to `print_stuff.py`. 

1. Since we just cloned this repo and no one else is working on it, we know we have the most updated version, but it's a best practice to **always pull first**.  "Pulling" means asking the GitLab remote server for the most recent version of the files that it knows about. In other words, pulling is like saying "go get me what's on the website."

In GitHub Desktop, you can pull by clicking the "fetch origin" button.  In this case, nothing in that remote version of the repo had changed, so nothing happens.

2. Now we can edit our code. To do that, we can open up the script in a text editor and start working. I am just adding one line of code, and then I can save.

3. I made that change locally, and Git noticed. You can see that in GitHub Desktop: the red shaded line with the minus sign shows what the old version looked like, and the green shaded lines with the plus shows what it looks like now. This way of visualizing changes to a file is called a "diff" because it shows this comparison in a structured way. Diffs don't show the whole file, which is why we don't see the header; they just show the changes that were made.

4. I made a change, Git saw it, and now I need to **commit** the change. Essentially, committing  asks Git to take a snapshot of the files it's tracking. We have modified the state of our repo, but we haven't told Git to store those changes. 

To do this in GitHub Desktop, we can go to the box in the lower left corner. We need to give our commit a message, and optionally a longer description. There are two boxes here: I typically only use the short one. A best practice here is to concisely describe the changes made with active verbs - it makes looking through history later much easier. 

Once I type this message, I can hit "commit to master," meaning that I am telling Git to take a snapshot of all the files it's tracking and save that snapshot in the master branch of this repository. 

5. Finally, we need to **push** the commit so the changes we made are accessible in the remote version of the repository online. This new screen popped up saying there are no local changes and we can push 1 commit. All we have to do is hit the "push origin" button. If we go back to the repository webpage, we can see that the changes we made have arrived. 

We can also look at the commit history of this repo: you can click on the "History" button on the right or on the "3 commits" link just underneath the project name. From that screen, we can see a listing of all the commits that have been made, and if we click on a commit, we can see the versions of the files in the repo at the time of that commit.

### Branches

Branching is a bit more advanced topic, but it's incredibly useful for collaboration, and even when you're working solo, it's a great way to try out something new without losing anything.

In the interest of time, I'm not going to demo the full process of creating a branch today. Instead, I'll show how to view different branches on GitHub and what it looks like to work on different branches on your local computer.

#### To view different branches on GitLab

1. On the project page, find the dropdown menu at on the upper center-left of the page, below the repo name but above the list of files. By default, when you come to this page, it will say "master" and show the most recent commit for the files in the master branch. In non Git-speak, it shows the most recent snapshot of files in the master version history. 

2. Click on the dropdown menu and select the "test" branch. Now the page will display the most recent commit for the test branch. If you open up each branch in different tabs, you can toggle back and forth and see the difference.

3. You can also look at the difference in commit histories. Click "commits" underneath the project name and it will take you to a page listing all the commits for that branch. The same branch dropdown menu is present here, so we can see how the commits differ between branches.

#### To view different branches on your local machine

1. Viewing and switching branches in GitHub Desktop is very similar to viewing them on the GitHub website. You can click on the dropdown menu in the middle of the top menu bar and select the branch you want to view.

2. There is a key difference in viewing files locally: the state of the files you see on your machine will actually change to match the latest commit in that branch. We can see that in the "diff" window in GitHub Desktop, and we could also see it by opening a file in a text editor and seeing the changes. 

3. An important caution: make sure you save and commit before switching branches. GitHub Desktop will prompt you to do this, but if you forget, you could lose work and/or complicate your nice clean version history. This is a good reason to commit often - so any changes you made will be relatively incremental - and know that Git has tools (e.g. squash, reset, rebase) to clean up messy version histories later. 