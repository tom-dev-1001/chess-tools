# Chess Tools

**Commercial chess analysis and training application**

<img width="1616" height="1079" alt="2d analysis" src="https://github.com/user-attachments/assets/f2576cbb-e85e-40ff-83a1-03f1b6610b10" />
<img width="1268" height="907" alt="3d image" src="https://github.com/user-attachments/assets/27049b15-70aa-4fdc-b7d8-6287fc58602d" />


Chess Tools is a commercial chess application focused on advanced board analysis, engine integration, rendering, and interactive training features.  
The project emphasizes performance-sensitive move generation, attack detection, AI search, rendering optimization, and complex UI state management across live and historical positions.

This repository provides a technical overview of the system design and engineering challenges involved.

---

## Key Technical Areas

### Board Analysis & Attack Detection
- Custom attack-map generation for all piece types (sliding and non-sliding)
- Separate internal board logic for analysis tools (arrows, highlights, overlays)
- Per position evaluation of attacked and defended pieces
- Value-aware attack analysis (e.g. minor vs major piece trades)
- Efficient detection of:
  - Checks
  - Attacked squares
  - Legal king moves under check and threat conditions

---

### Engine & AI
- Custom chess engine implementing **alpha–beta pruning**
- Heuristic evaluation combining material and tactical considerations
- Non-deterministic play via a **custom opening book system**
  - No Zobrist hashing
  - Custom position encoding
  - Manually constructed opening variations to avoid repetitive play

---

### Game Variants
- Standard chess
- **Duck Chess**
  - Full rule support
  - AI engine adapted to variant-specific mechanics
  - Move generation, legality checks, and evaluation extended beyond standard chess
- **Chess960**
  - Complete support for all 960 starting positions
  - Position selection via:
    - Index number
    - Piece-order pattern search
    - Random generation
   
---

### Analysis Board & Variations
- Full analysis board with:
  - Move history
  - Branching variations
  - Navigation across past positions
- Board tools function correctly on historical states
- Engine evaluations synchronized with variation state
- Integrated evaluation graphs and score display

---

### Rendering & Visualization
- Fully custom **2D and 3D board rendering systems**
- One-click runtime switching between 2D and 3D boards
- All visual assets created from scratch:
  - 2D pieces and analysis tools
  - 3D chess pieces modeled in **Blender**
- Three distinct 3D visual styles
- Dynamic shadow system with multiple quality modes:
  - Disabled (low-end)
  - Simple shadows
  - Full realistic shadows
- Shadow quality directly affects draw calls and rendering cost
- Designed to scale from low-end hardware to higher-performance systems

---

### Engine Integration & Concurrency
- Native engine support
- Integrated **Stockfish**
- External engine support via spawned processes
- Threaded console I/O for external engine communication
- Thread-safe synchronization between background analysis and UI rendering

---

### Training & User Systems
- Interactive tutorial system
- Interactive master game library (200+ games)
- Move-guessing challenges with contextual explanations
- Branching explanations covering:
  - Correct continuations
  - Alternative moves
  - Missed opportunities
- Persistent user data:
  - Completed challenges
  - Settings
  - Training progress

---

## Technical Focus
- Performance-oriented move generation
- Rendering optimization and draw-call reduction
- Complex state synchronization between UI, engine, and history
- Concurrency and external process management
- Non-trivial domain logic (chess rules, legality, evaluation)

---

## Source Code
This is a **commercial project**, and the source code is not publicly available.

This repository exists to document the architecture, technical challenges, and problem-solving involved in building a full-featured chess analysis, rendering, and training system.
