# Tic-Tac-Toe


Requires python to be installed to work


To activate the server you open up a terminal and enter: python server.py [Server port]

Once the server is up you activate the client by opening another terminal and enter: python client.py localhost [Server port]


The client will then ask you to input a name. Once you do that and the client is properly connected to the server, the server sends the client the board. Every time a new name is inputed, the server creates a fresh board and sends it to the appropriate client to make the first move. The board is simply an array, where empty spaces are represented by a 0, a player move 1, and a computer move 2.
To make a move you enter an integer from 1-9 based on the following pattern:
1 | 2 | 3
4 | 5 | 6
7 | 8 | 9
The integer you enter gets sent to the server which puts it on the board. The server checks the board to see if anyone has won, or it's a tie, if not then the server takes it's turn. The server uses a random number generator to pick a number from 1-9. If the number picked is already taken, the server simply runs the number generator again until an empty spot is chosen. The server checks the board again for a game over, then sends the updated board back to the client. This process is repeated until a game over is reached.

The server can handle multiple clients by separating each game into "instances". Everytime a new game is started, an instance is created. When a game over is reached, the server deletes that instance.
