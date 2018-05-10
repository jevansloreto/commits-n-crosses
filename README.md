Commits N Crosses
=================

 Game Board:

	|---|---|---|
	|   |   |   |
	|---|---|---|
	|   |   |   |
	|---|---|---|
	|   |   |   |
	|---|---|---|

-------------

 Player X: ________
 
 Player O: ________

-------------

Instructions:



1. To begin, one player must make a fork of the repository (repo), using the "Fork" button on the top right. This creates a copy of the repository in the user's own account, so they have full control over it, and their changes will not affect the main repository.
2. The player who owns the forked repository (player 1) should invite the other player (player 2) to edit their fork. To do this
    1. Click "Settings" at the top of the repository
    2. Choose "Collaborators" on the left
    3. Enter player 2's username in the search box and click "Add collaborator"
3. Player 2 will receive an email with an invitation - they should click the link to accept the invite.
4. Both players should clone a copy of the repository. To do that:
    1. Create a new folder in your N drive to store a copy of the repository
    2. Right click on the folder and choose "Git Bash Here". This will open a Bash command window where you can execute Git commands
    3. In the bash window enter the command `git clone https://github.com/<username>/commits-n-crosses` - replace <username> with player 1's username. Once you hit enter this should create a new folder called `commits-n-crosses` which will contain the repository and the code.
5. Change the active working directory to the one containing the repo by entering the command `cd commits-n-crosses` (TIP: Bash will automatically complete the folder name for you if you hit tab after entring a few characters)
6. So that Git can identify you, set your email address and username by:
    1. Enter the command `git config user.email "your email address"`
    2. Enter the command `git config user.name "your name"`  
7. Enter `git config credential.helper 'cache --timeout 7200'` - this tells Git to remember your password to save you having to type it every time.
8. To keep the changes in each game separate from its original state, player 1 should create a new branch for this round of the game:
    1. `git branch game1` - this creates the new branch
    2. `git checkout game1` - this activates the new branch, so that any changes we make apply only in this branch
    3. `git push -u origin game1` - this shares the branch with the Github copy of the repo, allowing player 2 to see it. Player 1 should enter their username and password when prompted. The `-u` flag tells Git to "track" the branch with the same name on Github, and create it if it doesn't exist.
9. Player 2 can now take a copy of the new branch and switch to it by:
    1. `git fetch` - to synchronise player 2's copy of the repo with the changes that are on Github
    2. `git checkout game1` - to create a new branch in player 2's repository, and have it keep track of changes in the Github version of the game1 branch
10. Player 1 can now make the first move. To do this:
    1. Open the folder that was created when cloning the repo and find the README.md file (this one!)
    2. Edit the README.md file using a text editor such as Notepad++
    3. Edit the game board at the top by placing an X in the grid and save the file
    4. In the Bash window, tell Git that you want to store the changes to all files in this folder - `git add .`
    5. Store the changes with a message explaining what the changes are `git commit -m "a message explaining the changes"`
    6. Synchronise the repo on Github with the changes `git push`
11. Player 2 can now update their local copy of the repo with player 1's move and then make their own move:
    1. In the Bash window, enter `git pull` - this will update Player 2's version of the README.md file with Player 1's move
    2. Player 2 should update the README.md file with their own move, and save the file
    3. To share the move with Player 1, Player 2 should enter `git add .` 
    4. `git commit -m "a message to explain the change"`
    5. `git push` - Player 2 should enter their username and password when prompted
12. Both players can now take it in turns to make a move, following the instructions in step 11 until someone wins the game.
13. To start a new game, player 2 should check out the master branch, and create a new branch for the new game:
    1. `git checkout master` - this reverts Player 2's copy of the README.md file to its original state
    2. `git branch game2` 
    3. `git checkout game2`
    4. `git push -u origin game2` 
14. Play can now continue as before.

