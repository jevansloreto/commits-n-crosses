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

 Player X: _Jevans_
 
 Player O: ________

-------------

 Both players should clone the repository:

    git clone https://github.com/LoretoCS/commits-n-crosses
    cd <reponame>
   
 Once in the repository directory, both players should set their config file to identify themselves to Git:

    git config user.email "<user@email.com>"
    git config user.name "<user name>"	

 And to save typing the password with every push, both players should tell Git to remember it for a couple of hours:

    git config credential.helper 'cache --timeout 7200'

 Player 1 should create a new local branch, and check it out

    git branch <player1 user name>/game1
    git checkout <player1 user name>/game1

 Player 1 then makes a move.


 To make the first move Player 1 should open README.md in a text editor, add the player names, make the first move, and save. Once the change is saved, Player 1 should stage it for committing, commit it, and push to the remote:	

    git add .
    git commit -m "some witty comment"
    git push -u origin <player1 user name>/game1

 Enter password when prompted.
    
 After the first move, Player 2 should fetch the changes, and check out the game branch.

    git fetch
    git checkout <player1 user name>/game1

 Player 2 can see the commit message using:

    git show

 If there is no command prompt after viewing git show, pressing "q" will exit the viewer.

 Player 2 should then open the README.md in a text editor to see their opponent's first move. They should then make a move in the same way Player 1 did, committing and pushing to the remote. 

 After the initial move, once both players have checked out the game branch, they can see their opponents move after they have committed and pushed by pulling changes:

    git pull

 And using show to view the commit message

    git show
    
 Reopen README.md and view their opponent's move, make their own move and save. Then the players should share the move by staging, comitting and pushing:

    git add .
    git commit -m "another comment"
    git push origin <player1 user name>/game1

 Each player should repeat the pull, change, stage, commit and push steps until someone wins the game.

-------------

 To start a new game Player 2 checks out master branch, creates a new branch, checks it out and continues as Player 1 did with the first move:

    git checkout master
    git branch <player2 user name>/game2
    git checkout <player2 user name>/game2

 Begin again!
