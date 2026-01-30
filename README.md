# Microcosm
![image.png]

A simple p2p simultaneous strategy game made in like 3 hours with Gemini (took about 4 or 5 prompts)

# Setup
First player sets up the board size and chooses their team, then sends a game link for the enemy team(s) to their friend

# Movement
1. Each turn, players allocate their moves towards available spaces by left clicking on a cell. Players are able to allocate as many moves as they wish for any cell.
2. A player has as many moves as the number of cells they currently own.
3. Available spaces are either cells owned by the player or cells adjacent to owned cells.
4. Players may retract moves by right clicking on a cell.

# Exchange
1. When each player is finished with their moves, they *Lock* in these moves. This creates a commitment hash and JSON move data.
2. Players trade their commitment hashes (I assume through discord) and these hashes are recorded by the other players
3. Once every hash is traded, players reveal their JSON move data.
4. Once every JSON move data is entered, players press "Resolve Combat"

# Resolution
1. For every cell, the player with the highest number of moves allocated towards this cell now owns that cell.
2. If no player has the highest number of moves on a cell (a tie), that cell's owner remains unchanged.
3. After moves are counted, if a player has multiple separate clusters of cells, the cluster(s) that do not have the most cells become neutral. If a player has exactly 2 clusters each with 5 cells (totaling 10), then both clusters remain alive for this turn.
4. If the game has not ended, repeat movement phase for the next turn

# Conclusion
The game ends when one player is left alive.
