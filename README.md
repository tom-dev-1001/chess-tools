# Chess Tools

**Commercial chess analysis and training application**

Chess Tools is a commercial chess application focused on advanced board analysis, engine integration, and interactive training features.  
The project emphasizes performance-sensitive move generation, attack detection, AI search, and complex UI state management across live and historical positions.

This repository provides a technical overview of the system design and engineering challenges involved.

---

## Key Technical Areas

### Board Analysis & Attack Detection
- Custom attack-map generation for all piece types (sliding and non-sliding)
- Separate internal board logic for analysis tools (arrows, highlights, overlays)
- Real-time evaluation of attacked and defended pieces
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

### Analysis Board & Variations
- Full analysis board with:
  - Move history
  - Branching variations
  - Navigation across past positions
- Board tools function correctly on historical states
- Engine evaluations synchronized with variation state
- Integrated evaluation graphs and score display

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
- “Find the Move” training mode using master games
- Quest-based progression system
- Persistent user data:
  - Completed challenges
  - Settings
  - Training progress

---

## Technical Focus
- Performance-oriented move generation
- Complex state synchronization between UI, engine, and history
- Concurrency and external process management
- Non-trivial domain logic (chess rules, legality, evaluation)

---

## Source Code
This is a **commercial project**, and the source code is not publicly available.

This repository exists to document the architecture, technical challenges, and problem-solving involved in building a full-featured chess analysis and training system.
