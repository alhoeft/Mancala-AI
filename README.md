# Mancala-AI
CSCI 3202
Project Report
Addie Hoeft and Cole Spencer

Project outline
1. (HW 6) Implement an interface that allows you to play Mancala
Prints the current state of the game
Prompts player to enter a move
Determines whether a move is legal or not
Applies captures and the continuation rule
Determines if someone has won and ends the game ✅
2. (HW 6) Build a random player--a player that makes random (legal) moves ✅
3. Play random vs. random player for 100 games and report statistics for each random player separately (Player 1 vs. Player 2)
Games won, % Player 1: 50 Player 2: 41
Games lost, % Player 1: 41 Player 2: 50
Games tied, % Player 1: 9 Player 2: 9
Compare your results with the table above. Are they within the expected
ranges? If not, explain why. They are in the expected ranges. ✅
4. Build an AI player that uses minimax to choose the best move with a variable
number of plies and the utility function described above ✅
5. Play 100 games with the random player against the minimax AI player at a
depth of 2 and 5 plies
What percentage of games does each player (AI or random) win?  
On average, how many moves does it take to win?
2 piles: AI wins 95%, random wins 4%, and tie happens 1%. When AI wins 29.02 total moves per game, 17.16 of them by AI. When Random wins 23.75 total moves per game, 8.50 of them by Random.
5 piles: AI wins 100%, random wins 0%, and tie happens 0%. When AI wins 26.12 total moves per game, 16.39 of them by AI.
Is your AI player better than random chance? Write a paragraph or two
describing why or why not
Does your AI player have a better win rate as the number of plies increases?
Why or why not?
7. Build an AI player that uses Alpha-Beta to choose the best move
8. Play 100 games with the random player against the Alpha-Beta AI player at a
depth of 5 plies
How long does it take for a single game to run to completion?
What percentage of games does each player (AI or random) win?
On average, how many moves does it take to win?
Are your results for this part different from those for your minimax AI player?
Write a paragraph or two describing why or why not
9. Play 100 games with the random player against the Alpha-Beta AI player at a
depth of 10 plies
NOTE: It may take between 15 minutes and 2 hours or more to run 100
games at 10 plies depending on how you have coded your project
How long does it take for a single game to run to completion?
What percentage of games does each player (AI or random) win?On average, how many moves does it take to win?
How much does the Alpha Beta algorithm speed up the game? Compare your
run time for 5 ply minimax against 5 ply Alpha Beta. Project how long
Minimax would take to run 10 plies.
Plot a curve showing the win percentage for a player looking ahead 2 plies, 5
plies and 10 plies
As you increase the number of plies, does the AI player win more games?
Explain why or why not.
10. Continuation rule check (20 points). Include a section in your notebook that
shows your game and your AI players handle the continuation rule correctly:
Rule tests (8 points): copy the HW 6 Part 3 test cell into your project
notebook and run it against your final game code. All 8 tests should pass (1
point each).
Extra-turn statistic (3 points): report the average number of extra turns per
game from your random-vs-random games (item 3), and say whether you
counted moves that end the game. Full credit for an average between 4.5
and 6.5 with 100 games, or between 5.3 and 6.0 with 1,000 games.
AI test positions (9 points): for each position below, it is Player 1's turn.
Run both your minimax and your Alpha-Beta players at the given depth d
(counted as AIMA does; see "How we count plies") with the utility function
above, and report the pit each one chooses (1.5 points for each correct
choice, 6 choices). Board lists are in the HW 6 layout:n every position, the correct pit earns an extra turn, and the correct answer
is the same one ply deeper, so it does not depend on a small difference in
how you count depth. AIMA's unmodified alpha_beta_cutoff_search ,
which always alternates MAX and MIN, undervalues the extra turn and picks
pit 3, 1 and 3 instead. A wrong answer here usually means your search does
not account for the continuation rule. In your writeup, explain what you changed in the search to handle it.
11. (Extra Credit, 20 points, Option 2 only). Make your Alpha-Beta AI player fast: run
100 games with the random player against the Alpha-Beta AI player at a depth
of 10 plies (d = 10, as AIMA counts it, so 11 moves ahead) in under 20 minutes
total, with correct results. For reference, a straightforward, efficient Python
Alpha-Beta took about 17 minutes for 100 games in our tests. Code that, for
example, deep-copies the whole game object at every node will be much
slower, so plan to measure and speed up your code. To earn the extra credit:
Measure the total time for all 100 games with time.perf_counter() and
report it along with the computer you used (processor and memory)
Your game must pass all of the continuation rule checks in item 9
Your AI player must win at least 95% of the 100 games
Explain what you did to make your code fast (for example, how you represent
the board, how you copy states, how you order moves)
Be prepared to run a shorter version of this test (for example, 10 games)
during your interview