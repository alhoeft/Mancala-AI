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
depth of 2 and 5 plies. What percentage of games does each player (AI or random) win?  On average, how many moves does it take to win?

2 piles: AI wins 95%, random wins 4%, and tie happens 1%. When AI wins 29.02 total moves per game, 17.16 of them by AI. When Random wins 23.75 total moves per game, 8.50 of them by Random.

5 piles: AI wins 100%, random wins 0%, and tie happens 0%. When AI wins 26.12 total moves per game, 16.39 of them by AI.

Is your AI player better than random chance? Write a paragraph or two
describing why or why not?

Our AI player is better than random chance. This claim is supported by our AI’s 95% and 100% win probabilities. To achieve this win probability the AI first copies the board so it can test moves without affecting the actual game board. It then tries every legal move and looks ahead a set number of plies, assuming the opponent will always pick the move that is worst for the AI. At the end of the look-ahead, it scores each board using the utility function, which is the number of stones in the AI’s mancala minus the number of stones in the opponent’s mancala. The AI then picks the move that leads to the highest score. The random player does not do any of this. It picks any legal pit with no thought about captures, extra turns, or what the opponent might do next. Because of this, the random player often gives the AI chances to capture stones or set up extra turns, and the AI takes them. This is why the AI wins almost every game. 

Does your AI player have a better win rate as the number of plies increases?
Why or why not?

Yes, our AI player has a better win rate as the number of plies increases. At 2 plies the AI won 95% of games, and at 5 plies it won 100% of games. With 2 plies, the AI only looks at its own move and the opponent’s reply, so it can miss moves that look good now but cause problems a few turns later. With 5 plies, the AI can see further ahead, which lets it plan extra turns, set up captures, and avoid giving the random player easy captures. The games also ended faster at 5 plies (26.12 total moves compared to 29.02 at 2 plies), which shows the AI was winning more efficiently. Looking deeper also has a cost. The number of boards the AI has to check grows very quickly with each extra ply, so 5 plies takes much longer to run than 2 plies.

7. Build an AI player that uses Alpha-Beta to choose the best move ✅
8. Play 100 games with the random player against the Alpha-Beta AI player at a
depth of 5 plies
How long does it take for a single game to run to completion?
What percentage of games does each player (AI or random) win?
On average, how many moves does it take to win?
Are your results for this part different from those for your minimax AI player?
Write a paragraph or two describing why or why not

After playing 100 games with the random player against the Alpha-Beta AI player at a depth of 5 piles, which took 13.0 seconds, we found that it took around 0.13 seconds per game on average, with a fastest time of 0.055s and a slowest time of 0.42s. The Alpha-Beta AI won 100% of the games and averaged 16.53 turns, compared to an average of 26.12 moves per game. The 5-ply Alpha-Beta results are identical to the 5-ply min-max results: both won 100% of the games, with an average of 26.12 moves per game and an average win at 16.53 AI moves. They did, however, differ in runtimes. The Alpha-Beta AI averaged 0.13s per game, while the minmax averaged 0.8s per game. These results are expected, as Alpha-Beta doesn’t differ in strategy, as it's just min-max with pruning. It computes the same values for each move; however, unlike Min-Max, it stops searching a branch once it can prove that the branch can’t change the final decision. Since both algorithms even use the same tie rule, they both pick the same pits at every turn. They both saw exactly the same random moves and played the exact same 100 games, so the only discrepancies between the two methods were the time it took to run. 

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


After playing 100 games with the random player against the Alpha-Beta AI player at a depth of 10 plies, which took around 34 minutes (before implementing our extra credit strategy), we found an average of 20.5 seconds per game, with a fastest time of 9.6 and a slowest time of 42.3. Similar to the Alpha-Beat AI at 5-ply, the 10-ply yielded a 100% win rate, this time with an average of 14.04 moves in a 22.7-move game. We timed and measured the minmax at 3, 4, 5, and 6 plies across 20 games each. With each additional ply, it got around 4.6x slower on average. Going from 5 plies to 10 plies adds five plies, meaning its projected time is around 27 minutes slower per game. In comparison, the 10-ply Alpha-Beta took 20.4 seconds per game, which is a projected speed-up of around 79x. We found that as the number of plies increases, the win rate only increases slightly. This, however, is because the AI was already winning almost every game, so the win rate went from 99% at 2 plies to 100% at 5 plies. Since the other player moves randomly, they are easy to beat, and you don't need many layers to win. Interestingly, however, the speed at which the AI wins the game does increase. With each additional ply, the AI player becomes more efficient, with the average game length (100% of the games they won) dropping from 28.6 moves at 2 plies to 26.1 at 5 plies to 22.7 at 10 plies. Furthermore, the AI’s own moves dropped from 17.0 to 16.5 to 14.0, respectively.  The further ahead the AI could look, the more it could set up chains of extra turns and captures, collect stones faster, and end the game sooner. 



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


We copied the HW 6 part 3 test cell into this notebook, and ran it against our final game code, with all 8 of 8 tests passing. In our 100 random-vs-random games, there were 6.11 extra turns per game on average, which is within the expected range of 4.5 to 6.5. In this, we did not count moves that ended the game, since we only count continuations when the last stone lands within the player’s mancala and the game is not over. For the AI test positions, both our minimax and Alpha-Beta players correctly chose pit 5 for position A, and pit 6 for positions B and C. To handle the continuation rule, searches don't assume that the players always alternate. Instead, at each node, it checks whose turn it actually is on the board, so a MAX node can have MAX children. This enables the AI to correctly value an extra turn as another move, whereas another search that always alternates would undervalue this and pick incorrect pits 



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
during your interview✅
Alpha-beta can only prune a branch once it has already found a good move to compare against, so the order the moves get checked in matters a lot. Originally, we had just a set of legal_moves. To speed up our code, we added ordered_moves which plays each move once first, then sorts them(moes that give an extra turn come first and after that the ones that put the most stones in the mover’s mancala). In mancala these are usually the best moves, so the AI finds a strong value early and alpha and beta tighten fast, which means more of the later branches get cut off with the break. It still gives the same answer as plain minimax since it only skips branches that couldn’t change the result, it just gets there way faster (about 10x at 10 plies).
