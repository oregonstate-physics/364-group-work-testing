## Instructions for making your small group repo

1. Create Github account
2. Set up ssh -- this enables you to access Github from the your JupyterHub account
	1. In JH terminal, run: `ssh-keygen -t ed25519`
	2. Press "Enter" to accept default values
	3. This makes a key and puts it in: `~/.ssh/id_ed25519.pub`
		1. View the file and copy the entire line of text from inside
	4. On Github, go to Settings --> SSH and GPG Keys --> New SSH Key
		1. Title it based on where the key lives, for example "PH 364 JupyterHub"
		2. Paste the whole line into the Key textbox
3. For this step only, just one person in your group does this: Create a repo on your Github account, adding your group mates as collaborators
	1. (also adding Patti and Alex?)
4. Everyone now: Make a local repo directory in your JH
5. In that directory, create a file introducing yourself
6. Make your directory into a branch of the main repo:
	1. `git init`
	2. `git remote set-url origin git@github.com:repo_owner/repo_name.git`
		1. This setting will link your JH directory permanently as a branch of the github repo. You can return to this step if you ever want to do this again for another repo, or if you want to link another machine.
	3. `git remote` 
		1. Yes, you can confirm that you want to connect to repo remotely -- now you are connected!
	4. `git add your_file_name.md`
	5. `git commit -m "your message in quotes"`
		1. At this stage, JH might prompt you to enter some info about yourself
		2. Be aware, the username you enter here will be viewable by all your group members in Github to show them who made this commit.
	6. `git branch -M main`
	7. `git push`
		1. Should we have students `git pull` first here?
7. Go to the repo on Github -- see if your file showed up there!

