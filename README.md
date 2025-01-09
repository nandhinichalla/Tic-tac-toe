# Tic-tac-toe

# Overview
Tic-Tac-Toe is a classic two-player game played on a 3x3 grid. Players take turns marking spaces, aiming to align three of their marks horizontally, vertically, or diagonally.
This project implements Tic-Tac-Toe using the Finite State Machine (FSM) concept, modeled as a Moore FSM with four distinct states:
# FSM States
IDLE (00):
The starting or resting state of the game.
The system remains in this state while waiting for the player or computer to take their turn, or during a reset.
PLAYER (01):
The player makes their move, and their input is stored in the respective position on the grid.
COMPUTER (10):
The computer takes its turn, and its move is registered in the board's decoded position.
GAMEOVER (11):
This state is reached when a winner is determined, or no more moves are possible.

# Inputs to the FSM Controller
Reset:
If 0, the game begins.
If 1, the game ends or resets.

Play:
If 1, the FSM transitions to the PLAYER state, enabling the player to make a move.

PC (Computer Play):
If 1, the computer takes a turn and transitions to the IDLE state afterward.
If 0, it remains in the COMPUTER state.

Illegal_move:
If the player attempts an invalid move:
Illegal_move = 0: Switch to the COMPUTER state and allow the computer to play.
Illegal_move = 1: Return to the IDLE state.

No_space:
If 1, no further moves are possible, transitioning to the GAMEOVER state.

Win:
If 1, a winner is detected, and the system transitions to GAMEOVER.

# Modules in the Verilog Design
Position Register:
Tracks the positions played by the player or computer, enabled by the FSM controller.

Winner Detector:
Identifies a winner by checking for three consecutive marks (X or O) along rows, columns, or diagonals.

Position Decoder:
Converts the selected position (4-bit input) into a 16-bit output where the corresponding bit is set to 1.

Illegal Move Detector:
Detects invalid moves where a player attempts to play in an already occupied spot.

No Space Detector:
Checks if the board has any unoccupied spaces left for further moves.

FSM Controller:
Orchestrates the game flow, determining when the player or computer takes a turn and when the game ends.

# In conclusion,
the Tic-Tac-Toe game implemented using a Finite State Machine (FSM) in Verilog showcases the power of FSMs in controlling sequential logic for interactive systems. By utilizing a Moore FSM with distinct states for the player, computer, idle, and game-over conditions, the project demonstrates efficient game flow management. Key components such as position registers, winner detectors, and illegal move detectors highlight how modular Verilog code can be used to design and control complex systems. Through this project, valuable insights were gained into digital design, Verilog programming, and FSM-based system control. The project not only provided a practical application of FSM concepts but also offered a foundation for further expansion, such as adding AI difficulty levels or incorporating graphical interfaces, opening up numerous possibilities for future enhancements and real-world applications.
