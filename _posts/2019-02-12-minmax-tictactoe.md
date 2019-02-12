---
layout: post
title:  "TicTacToe AI to Illustrate Min-Max Algorithm"
date:   2019-02-12
categories: 
---

An old [github project](https://github.com/spolsley/TicTacToeAI) I decided to update recently is a web-based TicTacToe AI.  I'd originally written it to learn about the min-max (more commonly called minimax) algorithm for game AI, but I thought it'd be fun to add visualizations of all the possible games the AI evaluates at different depths.  It is now available [online](http://projects.spolsley.com/tictactoe.html).

In a nutshell, the algorithm plays out every possible version of the game from the current board state.  In TicTacToe, it can evaluate until endgame, but in something more complex like chess or checkers, there's so many possibilities branching out with each move, it's faster to play only a certain number of moves into the future.

Whatever the case, after generating all the game states, the system then evaluates which branches are most likely to lead to a win.  For endgame states, determining the winner is easy, but for games like chess and checkers, the computer will typically use rank and value of pieces to decide if a state is good or not.  By propagating these future board states up the tree (or back through earlier theoretical moves), the AI can select the next move most likely to lead to a win state.

Wikipedia has a very nice article with pseudocode and visuals, so it's a great resource to check out for details: [https://en.wikipedia.org/wiki/Minimax](https://en.wikipedia.org/wiki/Minimax)

The latest version of the simple TicTacToe AI from my github can be found online below.

<font size="+3">Link: <a href="http://projects.spolsley.com/tictactoe.html" target="_blank">TicTacToe with Probabilities and States</a></font>

Simply click a cell in the 3x3 grid to start a game, or press "Computer Play First" to let the AI begin.  There's no difficulty level, so the AI will always choose the optimal next move, meaning it is only possible to draw at best.  Remember that the AI evaluates the board until endgame; thus, it knows all the ways it can lose and will never select such a path.

Checking "Show Probabilities" will color-code the cells with likelihood from gray (low) to green (high) that it is a good next move for the AI.

Checking "Show Visited States" displays all the boards the computer evaluates in choosing its next move.  This is the main "new" feature added.  Note that the states are not organized into an actual min-max tree with the various probabilities.  They are organized instead by depth / number of moves into the future.  It's not a perfect way to visualize the data, but in conjunction with some other resources about game AI algorithms, it's a fun feature to try out.

For example, in the game below, the human player has put an "X" in the upper right, and the computer chose the center to play "O".  Although the difference is minor, color coding shows that the center and edges are empirically better cells than in-between cells.

![Sample TicTacToe Game](../../../res/images/posts/minmax-tictactoe/samplegame.png)