# Introduction to Repositories
## What is a Repository?

> [!NOTE] Aside: Git and Github are two different things!
> Git is a version control system created by Linus Torvalds (the creator of Linux) that tracks changes in files through a data storage system called a *directed acyclic graph*. 
> Git is extremely useful when a group of people are making changes to the same files at the same time. 
> It is also useful for a single person to track changes to a project where parts of the file might be overwritten and the work may need to be recovered at some future point.
>
> Github is a public storage unit for git projects, kind of like how Steam is a hub for video games.
> Github is not the only public storage of this kind! There are other ones with different pros and cons -- for example, Github is now owned by Microsoft, and they use its ubiquity to their advantage by data scraping the repositories hosted there with their AI copilot. 
> Other platforms include public sites like Gitlab and Codeberg, or you can host your own using something like Gogs or Gitea.
> There are several things you can do via Github that cannot be accomplished using git alone, such as kanban boards, web hosting, wikis, and more. 
> That doesn't mean that github replaces git! It is just another tool to make collaboration among groups of people easier.

## Creating Github Account
The first thing you will need to do is set up an account with [github](https://github.com). Github is the "industry standard" public repository for code, and allows both users and public viewers to download, execute, and run projects. 
It is a good idea to set this account up with your private email first, and add your university email as a secondary email later, that way you can manage your github account after you leave. 
Adding your university email allows you to sign up for github pro, which allows you to make use of more storage and better collaboration tools.
The first thing you are going to want to do is be able to **push** and **pull** code from git to your personal machine or via JupyterHub.

### Setting up ssh
	1. In a terminal, type: `ssh-keygen -t ed25519`
	2. Press `Enter` to accept default values
	3. This makes a key and puts it in: `~/.ssh/id_ed25519.pub`
		1. View the file and copy the entire line of text from inside. It should look something like this:
        ```
        ssh-ed25519 <string of characters> <email>
        ```
	4. On Github, go to Settings --> SSH and GPG Keys --> New SSH Key
		1. Title it based on where the key lives, for example "PH 364 JupyterHub" or "Personal Laptop"
		2. Paste the whole line into the Key textbox

To prepare for the next step, you should now create a new Github project. At the top of the page on github, click the plus icon and then "New Repository". Create a short but memorable name. For now, ignore the configuration options section. 

>[!IMPORTANT]
> By default, Github makes repositories **public**. Do not put any information in a public repository that you do not want other people to see, including private keys, personal emails, or anything you do not want linked to yourself.

Remember the name you have created in this step, you will need it later.

### Make a local git repository in your JupyterHub
To test that everything works, we will push a text file to a git repository. For this exercise, try to only use terminal commands.
Create a new directory. In that directory, create a file introducing yourself. The file should be a plaintext file or markup file, such as markdown or org.

Once you have finished, you can initialize your repository.
```
git init
```
This creates a new hidden subdirectory named `.git` that contains all of the necessary files to maintain a Git repository skeleton. At this point, nothing in your project is tracked. See [Git Internals](https://git-scm.com/book/en/v2/Git-Internals-Plumbing-and-Porcelain#ch10-git-internals) for more information about exactly what files are contained in the .git directory.

We should now be able to see what is going on in our newly created project.

> [!IMPORTANT]
> Some of the most important commands you should memorize to see what is going on in your repository are `git status` and `git log`.
> `git status` will tell you what branch you are on, the current state of every file in the project, including whether it has been added or deleted, and whether or not the changes are different from the remote repository.
> `git log` will show every commit that has been made and the local branch that it has been made on, as well as the commit hash and remote bbranch. 
> It shows the author, the date, and a portion of the commit that has been written.

Since we have already created a file, we now want to begin tracking said file and **commit** it to the worktree.
```
git add <filename>
git commit -m "Add <file>"
```
You always want to leave at least a short, descriptive message explaining what the commit is for. The `-m` stands for "message", which allows you to write a short and simple line straight from the terminal. If you omit that, git will automatically open a text editor for you to write a longer commit message.

At this stage, git may prompt you to enter a username and email. The username you set here **will be public**, so be cognizant of what you choose if you ever start committing to public projects on github. I would suggest putting something like the first letter of your first name and your last name, or just your last name. 

The `user.email` field will also be public. Your github account by default creates a separate noreply email for you, which is a good security practice so that your email is not scraped by bots and put on a phishing list. You can find this email by going to Settings --> Access --> Emails and copy-pasting the email shown atop your primary email. It will be in the format of 
```
00000001+<username>@users.noreply@github.com
```

So that you only have to do this once, run 
```
git config --global user.email "you@example.com"
  git config --global user.name "Your Name"
```
To set your account's default identity. This will set your credentials for every future repository you create.

Now we can link our local repository to github by adding a remote repository. This is where you will link your local git to the repository you created earlier.
```
git remote add origin git@github.com:<user>/<repository>.git
```
This will add a remote to the git repository, which you can now send changes to (push) and receive changes from (pull).
You can add several remotes to a project, when you might want to mirror your changes to several different repositories.

You can return to this step if you ever want to do this again for another repo, or if you want to link another machine.
Each remote has to have a unique name, so once `origin` is in use, it will be taken until deletion.

We can now push to our Github repository!
To do this, you should run
```
git push
```
Git will then yell at you. That's ok. It says what you should do: set your *upstream* to the remote you just linked. Let's try again:

```
git push --set-upstream origin main
```

You will only need to do this once, so that git knows where to send your changes when you type `push` without a remote specified.

Now go to Github. You should see your file there. Congrats! You have set up your first remote repository.

## Setting up Small Group Repositories
3. For this step only, just one person in your group does this: Create a repo on your Github account, adding your group mates as collaborators
	1. (also adding Patti and Alex?)
