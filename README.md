# CHESS-GAME-PART-1-HUMAN-VS-HUMAN
♟ Console chess in C++ — built from scratch! Full move validation, check/checkmate/stalemate detection, ASCII art pieces, mouse click support, move highlighting, undo/redo, save &amp; replay. Human vs Human. Phase 1 human vs human of a 1st-sem PF final project. 🏁
# ♟️ ConsoleMate — C++ Chess Engine

<div align="center">

```
██████╗ ██╗  ██╗███████╗███████╗███████╗
██╔════╝██║  ██║██╔════╝██╔════╝██╔════╝
██║     ███████║█████╗  ███████╗███████╗
██║     ██╔══██║██╔══╝  ╚════██║╚════██║
╚██████╗██║  ██║███████╗███████║███████║
 ╚═════╝╚═╝  ╚═╝╚══════╝╚══════╝╚══════╝
```

**A fully scratch-built, console-based Chess game written in C++**  
*1st Semester Final Project · Programming Fundamentals · BSAI 2025*

![C++](https://img.shields.io/badge/Language-C++-00599C?style=flat-square&logo=cplusplus)
![Platform](https://img.shields.io/badge/Platform-Windows-0078D6?style=flat-square&logo=windows)
![Mode](https://img.shields.io/badge/Mode-Human%20vs%20Human-green?style=flat-square)
![Phase](https://img.shields.io/badge/Phase-1%20-orange?style=flat-square)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square)

</div>

---

## 🎯 About The Project

**ConsoleMate** is a fully functional chess game built from the ground up in C++ — no libraries, no game engines, no shortcuts. Every piece movement rule, check/checkmate detection, move highlighting, and board rendering was hand-coded from scratch as part of a **Programming Fundamentals (PF) final project**.

This is **Phase 3 — Part 1** of the project, featuring a complete **Human vs Human** gameplay experience rendered directly in the Windows console with mouse click support, ASCII art pieces, and a polished UI.

---

## ✨ Features

### 🎮 Core Gameplay
| Feature | Description |
|---|---|
| ♟ All 6 Piece Types | Pawn, Rook, Knight, Bishop, Queen, King — fully implemented |
| ✅ Legal Move Validation | Every piece follows its exact real-world movement rules |
| 🚫 Self-Check Prevention | Prevents any move that puts your own King in check |
| 👑 Check Detection | Real-time check alerts displayed during gameplay |
| 🏁 Checkmate Detection | Game ends and announces winner on checkmate |
| 🤝 Stalemate Detection | Correctly identifies draw by stalemate |
| ⬛⬜ Turn Management | Alternates between WHITE and BLACK turns seamlessly |

### 🖱️ Mouse-Driven UI
| Feature | Description |
|---|---|
| 🖱 Click to Select | Click any piece to select it |
| 💡 Move Highlighting | All valid moves glow in **blue** highlight boxes |
| 🎯 Click to Move | Click any highlighted square to place your piece |
| ❌ Invalid Feedback | Instant on-screen error messages for bad moves |

### 🎨 Visual Design
| Feature | Description |
|---|---|
| 🖼 ASCII Art Pieces | Hand-crafted pixel art for all 6 piece types |
| 🟨🟩 Colored Board | Alternating Yellow/Green squares for classic chess look |
| 🔴 Border Accents | Red-bordered tiles for clean grid separation |
| 🖥 Console Rendering | Cursor-positioned rendering — no screen flicker |

### 💾 Save & Replay System
| Feature | Description |
|---|---|
| 💾 Auto Save | Game state saved to file after every move |
| 📂 Load Previous Game | Continue from last session on launch |
| ⏪ Undo (U key) | Step back to any previous board state |
| ⏩ Redo (R key) | Replay moves after undoing |
| 🎬 Game Replay | Watch the full match replay at any interval (every 5 moves) |

---

## 📸 Screenshots

```
┌──────────────────────────────────────────────────────────────┐
│                       CHESS BOARD                            │
│                                                              │
│   r  n  b  q  k  b  n  r    ← Black pieces (row 0)          │
│   p  p  p  p  p  p  p  p    ← Black pawns (row 1)           │
│   .  .  .  .  .  .  .  .                                     │
│   .  .  .  .  .  .  .  .                                     │
│   .  .  .  .  .  .  .  .                                     │
│   .  .  .  .  .  .  .  .                                     │
│   P  P  P  P  P  P  P  P    ← White pawns (row 6)           │
│   R  N  B  Q  K  B  N  R    ← White pieces (row 7)          │
│                                                              │
│  [WHITE turn]  Select source >  Select destination >         │
└──────────────────────────────────────────────────────────────┘
```

---

## 🏗️ Project Architecture

```
BSAI25033-CHESS-PHASE-3.cpp
│
├── 📦 Data Structures
│   ├── Piece      → sym, color, position, isLegalMove (fn pointer)
│   └── Player     → color, symbol
│
├── 🎨 Rendering Engine
│   ├── box()             → draws full 8x8 board
│   ├── print_box()       → renders single square + piece
│   ├── drawPiece()       → dispatches ASCII art by piece type
│   ├── pawn / R / Bishop / queen / king / Knight()
│   └── gotoRowCol()      → cursor positioning via WinAPI
│
├── ⚙️ Move Logic (Function Pointers)
│   ├── isLegalPawn()
│   ├── isLegalRook()
│   ├── isLegalKnight()
│   ├── isLegalBishop()
│   ├── isLegalQueen()
│   └── isLegalKing()
│
├── 🔍 Path Validation
│   ├── isHorizontalPathClear()
│   ├── isVerticalPathClear()
│   └── isDiagonalPathClear()
│
├── 🛡️ Game State Engine
│   ├── isCheck()
│   ├── isSelfCheck()
│   ├── isCheckmate()
│   └── isStalemate()
│
├── 💡 Highlighting System
│   ├── highlightBox()
│   ├── highlightPossibleMoves()
│   └── unHighlight()
│
├── 💾 Persistence Layer
│   ├── saveGame()  / loadGame()
│   ├── saveState() / loadState()
│   ├── saveReplay()
│   ├── replayGame()
│   ├── undo()
│   └── redo()
│
└── 🎮 Game Loop (main)
    ├── Menu: New Game / Load Previous
    ├── playerMove() → click source → click dest → validate → update
    └── Win/Draw detection after every turn
```

---

## 🕹️ How to Play

### Controls
| Action | Input |
|---|---|
| Select a piece | **Left Mouse Click** on your piece |
| Move to a square | **Left Mouse Click** on a highlighted square |
| Undo last move | Press **U** |
| Redo move | Press **R** |
| Continue after alert | Press **Enter** |
| Replay the game | Press **Y** when prompted (every 5 moves) |

### Game Flow

```
Launch → [1] New Game  OR  [2] Load Previous Game
           │
           ▼
        Board draws on screen
           │
           ▼
    WHITE picks source (click)
           │
           ▼
    Valid moves highlighted in BLUE
           │
           ▼
    WHITE picks destination (click)
           │
           ▼
    Move validated → Board updates
           │
           ▼
    Check / Checkmate / Stalemate detected?
       ├── YES → Game Over message
       └── NO  → BLACK's turn → repeat
```

---

## 🔧 Setup & Compilation

### Requirements
- **OS:** Windows (uses `windows.h`, `conio.h`, `WinAPI`)
- **Compiler:** MinGW g++ or MSVC (Visual Studio)
- **Terminal:** Windows Console (cmd / PowerShell — NOT Linux WSL terminal)

### Compile with g++
```bash
g++ -o chess BSAI25033-CHESS-PHASE-3.cpp
./chess
```

### Compile with Visual Studio
1. Create a new **Console Application** project
2. Add `BSAI25033-CHESS-PHASE-3.cpp` to the project
3. Set character set to **Multi-byte** (Project → Properties → Character Set)
4. Build and Run (`Ctrl+F5`)

### Console Settings (Important!)
Before running, right-click the console title bar → Properties and set:
- Font: **Consolas** or **Lucida Console**, size **5–6**
- Window size: **at least 180 columns × 80 rows**

---

## 📁 File Structure

```
📦 ConsoleMate-Chess/
├── 📄 BSAI25033-CHESS-PHASE-3.cpp   ← Main source file (all-in-one)
├── 💾 savegame.txt                   ← Auto-generated save file
└── 📖 README.md                      ← You are here
```

---

## 🧠 Concepts Demonstrated

This project demonstrates the following **Programming Fundamentals** concepts:

| Concept | Implementation |
|---|---|
| Structs | `Piece`, `Player` with multiple fields |
| Arrays | `board[8][8]`, `replayHistory[100][8][8]` |
| Pointers | `Piece*`, `int*`, function pointers |
| Function Pointers | `isLegalMove` stored inside each `Piece` struct |
| Dynamic Memory | `new` / `delete` for board and piece allocation |
| File I/O | `ofstream`/`ifstream` for save & load |
| Enums | `COLOR { BLACK, WHITE }` |
| Control Flow | Nested loops, conditionals, game loop |
| Windows API | Console cursor, color, mouse input |

---

## 🔮 Planned Features (Phase 3 — Part 2 & Beyond)

- [ ] 🤖 AI opponent (minimax algorithm)
- [ ] 🏰 Castling (King + Rook special move)
- [ ] ⬆️ Pawn Promotion (choose piece on reaching end)
- [ ] 🎯 En Passant capture
- [ ] ⏱ Chess Clock / Timer
- [ ] 📊 Move History Log (algebraic notation)
- [ ] 🎨 Improved board UI / color themes

---

## 👨‍💻 Developer

| Field | Info |
|---|---|
| **Student ID** | BSAI25033 |
| **Program** | BS Artificial Intelligence |
| **Semester** | 1st Semester |
| **Course** | Programming Fundamentals (PF) |
| **Project Phase** | Phase 3 — Part 1 (Human vs Human) |

---

## 📜 License

This project is submitted as an academic assignment. Feel free to use it as a reference for learning C++ console game development.

---

<div align="center">

**Built with ❤️ from scratch — no shortcuts, no libraries, just pure C++**

*"Every great chess player was once a beginner."*

</div>
