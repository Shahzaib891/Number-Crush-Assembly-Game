\# Number Crush Assembly Game



Number Crush Assembly Game is a console-based number matching game developed in \*\*x86 Assembly Language\*\* using \*\*MASM\*\*, \*\*Irvine32\*\*, and \*\*Visual Studio\*\*.



The game is inspired by match-based puzzle games where the player swaps adjacent values on a grid to create combinations. It includes multiple levels, score tracking, bomb logic, blocked cells, colored console output, and player record saving using file handling.



\## Preview



\### Welcome Screen



!\[Welcome Screen](screenshots/welcome-screen.png)



\### Player Name Input



!\[Player Name Input](screenshots/player-name-input.png)



\### Level 1 Gameplay



!\[Level 1 Gameplay](screenshots/level-1-gameplay.png)



\### Level 2 Gameplay



!\[Level 2 Gameplay](screenshots/level-2-gameplay.png)



\### Level 3 Gameplay



!\[Level 3 Gameplay](screenshots/level-3-gameplay.png)



\## Project Overview



This project was created as a \*\*Computer Organization and Assembly Language\*\* project to demonstrate practical use of low-level programming concepts in a playable console game.



The game uses indexed board positions, random number generation, user input, conditional logic, procedures, macros, colored console output, and file handling. The main game logic is written in `main.asm`, and the project uses Irvine32 library support for console input/output, colors, cursor positioning, delays, and file operations. :contentReference\[oaicite:0]{index=0}



\## Features



\- Console-based interactive gameplay

\- Player name input

\- Three playable levels

\- Indexed number grid

\- Valid adjacent swapping

\- Row and column combo detection

\- Score tracking

\- Move tracking

\- Bomb cells

\- Blocked cells in advanced level

\- Colored console UI

\- Player score record saved in a text file

\- Visual Studio solution included

\- MASM and Irvine32-based implementation



\## Tech Stack



| Area | Technology |

|---|---|

| Language | x86 Assembly |

| Assembler | MASM |

| Library | Irvine32 |

| IDE | Visual Studio |

| Platform | Windows |

| Interface | Console |

| File Handling | Windows API / Irvine32 support |



\## Game Levels



\### Level 1



\- Uses a `10 x 10` board

\- Board indexes range from `0` to `99`

\- Contains normal number values and bombs

\- Player swaps adjacent indexes to create combinations



\### Level 2



\- Uses a `9 x 9` board

\- Board indexes range from `0` to `89`

\- Includes blank spaces where movement is not allowed

\- Uses separate Level 2 board generation and combo-checking logic



\### Level 3



\- Uses a `10 x 10` board

\- Includes bombs and blocked cells

\- Blocked cells are represented by `X`

\- Player cannot swap blocked cells



\## How to Play



\### 1. Start the Game



Open the project in Visual Studio and run it. The game starts with a welcome screen.



\### 2. Enter Player Name



The game asks for the player name:



```text

Input Name of Player :

```



Enter your name and press Enter.



\### 3. Understand the Board



The board is displayed with indexes.



For Level 1 and Level 3, the board is `10 x 10`.



Example index layout:



```text

0   1   2   3   4   5   6   7   8   9

10  11  12  13  14  15  16  17  18  19

20  21  22  23  24  25  26  27  28  29

...

90  91  92  93  94  95  96  97  98  99

```



For Level 2, the board is `9 x 9`.



\### 4. Swap Two Adjacent Values



The game asks:



```text

Input First Number Index  :

Input Second Number Index :

```



Enter two adjacent indexes.



Example:



```text

Input First Number Index  : 12

Input Second Number Index : 13

```



This attempts to swap the values at indexes `12` and `13`.



\### 5. Valid Move Rules



A move is valid only when both selected positions are adjacent.



For Level 1 and Level 3:



\- Left/right difference is `1`

\- Up/down difference is `10`



Examples:



```text

12 and 13  -> valid horizontal move

12 and 11  -> valid horizontal move

12 and 22  -> valid vertical move

12 and 2   -> valid vertical move

```



For Level 2:



\- Left/right difference is `1`

\- Up/down difference is `9`



\### 6. Combo Rule



A swap is accepted when it creates a combination of:



```text

3 or more same values in a row

```



or:



```text

3 or more same values in a column

```



When a combo is formed:



\- Matching values are crushed

\- Score increases

\- New random values are generated in their place



If no combo is formed, the swap is reversed.



\### 7. Bomb Rule



Some cells contain:



```text

B

```



`B` represents a bomb.



When a bomb is involved in a move, the bomb logic activates and replaces matching values on the board. This also affects the score.



\### 8. Blocked Cells



In Level 3, some cells contain:



```text

X

```



`X` represents a blocked cell.



Blocked cells cannot be swapped.



\### 9. Score and Moves



The game displays:



\- Player name

\- Current level

\- Moves

\- Score



Each level continues until the required number of successful moves is reached.



\### 10. Player Records



At the end of the game, player information and scores are saved in:



```text

PlayersRecord.txt

```



The record includes:



\- Player name

\- Level 1 score

\- Level 2 score

\- Level 3 score

\- Best score



\## Project Structure



```text

Number-Crush-Assembly-Game/

├── main.asm

├── Irvine32.inc

├── Irvine32.lib

├── Kernel32.Lib

├── Macros.inc

├── SmallWin.inc

├── User32.Lib

├── VirtualKeys.inc

├── PlayersRecord.txt

├── NumberCrushGame.sln

├── NumberCrushGame.vcxproj

├── NumberCrushGame.vcxproj.filters

├── screenshots/

│   ├── welcome-screen.png

│   ├── player-name-input.png

│   ├── level-1-gameplay.png

│   ├── level-2-gameplay.png

│   └── level-3-gameplay.png

├── README.md

└── .gitignore

```



\## Important Files



| File | Purpose |

|---|---|

| `main.asm` | Main Assembly source code containing the complete game logic |

| `Irvine32.inc` | Irvine32 include file required for Assembly procedures |

| `Irvine32.lib` | Irvine32 library file |

| `Kernel32.Lib` | Windows kernel library used by the project |

| `User32.Lib` | Windows user interface library |

| `Macros.inc` | Macro support file |

| `SmallWin.inc` | Windows-related include file |

| `VirtualKeys.inc` | Keyboard key constants include file |

| `PlayersRecord.txt` | Stores player records and scores |

| `NumberCrushGame.sln` | Visual Studio solution file |

| `NumberCrushGame.vcxproj` | Visual Studio project configuration |

| `NumberCrushGame.vcxproj.filters` | Visual Studio file organization filters |



\## Assembly Concepts Used



This project demonstrates several Assembly and COAL concepts:



\- Registers and memory access

\- Procedures

\- Macros

\- Conditional jumps

\- Loops

\- Arrays

\- Index-based board traversal

\- Random number generation

\- Console cursor positioning

\- Text color manipulation

\- File handling

\- Windows API calls

\- Stack usage with `push` and `pop`

\- Parameterized procedures

\- Input/output handling



\## Core Game Logic



\### Board Initialization



The board is filled with random values. Different levels use different board sizes and rules.



\- Level 1 and Level 3 use a `10 x 10` array

\- Level 2 uses a `9 x 9` array

\- Level 3 introduces blocked cells



\### Move Validation



The game checks whether the selected indexes are:



\- Within board range

\- Not the same position

\- Adjacent horizontally or vertically

\- Not blocked

\- Not invalid spaces



\### Swap Logic



If the selected positions are valid, the values are swapped. The game then checks if the swap creates a valid combo.



\### Combo Detection



The game checks both:



\- Row combinations

\- Column combinations



If three or more same values are found together, they are crushed and replaced.



\### Bomb Logic



Bomb cells trigger special logic that replaces matching values and increases the score.



\### File Handling



The game writes player records to `PlayersRecord.txt` using file handling logic.



\## How to Run



\### Requirements



Make sure you have:



\- Windows OS

\- Visual Studio

\- MASM support enabled

\- Irvine32 library files included in the project folder



\### Steps



1\. Clone or download the repository.

2\. Open the solution file:



```text

NumberCrushGame.sln

```



3\. In Visual Studio, select the correct build configuration.



Recommended:



```text

Debug | x86

```



4\. Build the project.

5\. Run the project using:



```text

Ctrl + F5

```



or:



```text

Debug > Start Without Debugging

```



\## Notes



\- The project is designed for Windows because it uses Visual Studio, MASM, and Irvine32.

\- Keep Irvine32-related files in the project folder unless you update Visual Studio include and library paths manually.

\- The `.vs/`, `Debug/`, and user-specific Visual Studio files should not be committed to GitHub.

\- `PlayersRecord.txt` is included so the file handling feature can work and store player scores.



\## Screenshots



| Welcome Screen | Player Name Input |

|---|---|

| !\[Welcome Screen](screenshots/welcome-screen.png) | !\[Player Name Input](screenshots/player-name-input.png) |



| Level 1 | Level 2 | Level 3 |

|---|---|---|

| !\[Level 1](screenshots/level-1-gameplay.png) | !\[Level 2](screenshots/level-2-gameplay.png) | !\[Level 3](screenshots/level-3-gameplay.png) |



\## Current Status



| Module | Status |

|---|---|

| Welcome screen | Working |

| Player input | Working |

| Level 1 board | Working |

| Level 2 board | Working |

| Level 3 board | Working |

| Swap validation | Working |

| Combo detection | Working |

| Bomb logic | Working |

| Score tracking | Working |

| File handling | Working |



\## Future Improvements



\- Add more moves per level

\- Add difficulty selection

\- Add better game-over summary

\- Add leaderboard display inside the game

\- Add separate menu screen

\- Improve score conversion and formatting

\- Add more special tiles

\- Improve comments and procedure organization

\- Add detailed project documentation in a `docs/` folder



\## Author



\*\*Shahzaib Safdar\*\*  

BS Computer Science | Air University, Islamabad  

Assembly Language | MASM | Irvine32 | Visual Studio



\## Repository Purpose



This repository presents a console-based Number Crush game developed in x86 Assembly Language. It demonstrates practical use of Assembly programming concepts, Irvine32 library functions, board-based game logic, score tracking, user interaction, and file handling.

