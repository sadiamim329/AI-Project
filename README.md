# ♟️ KROSH: Checkers Against Classical Search

Welcome to the **AI-Project** (formerly *AI-Lab-Slides*) repository! 

This repository contains the full source materials, presentation slides, and the official final lab report for **KROSH** — a complete English-draughts (American Checkers) system powered by classical adversarial-search engines, Monte Carlo Tree Search (MCTS), and a hybrid phase-switching engine.

---

## 👥 Course & Group Information

- **Course:** CSE 3811 - Artificial Intelligence Laboratory 
- **Institution:** Department of Computer Science and Engineering, United International University (UIU)
- **Instructor:** Kazi Fahim Tahmid (Lecturer, Department of CSE, UIU)
- **Group:** Group 10

### 👨‍💻 Group Members
1. **Adham Zarif** | ID: `0112330721`
2. **Saber Hassan** | ID: `0112330870`
3. **Sadia Islam** | ID: `0112330329`

---

## 📁 Repository Contents

| File Name | Description |
| :--- | :--- |
| 📕 **`AI_Lab_Report.pdf`** | Official Final Project Report detailing architecture, search algorithms, benchmarks, and system pipeline. |
| 📊 **`Project Update Presentation.pptx`** | Primary presentation slides covering project architecture, features, and engine benchmarks. |
| 📄 **`out.pptx`** | Exported presentation output and supplementary slides. |

---

## 🚀 Key Features & Project Overview

- **32-Slot Rules Core:** Pure Python implementation of full English-draughts rules, supporting in-place apply/undo, compulsory multi-jump captures, and promotions.
- **5 Search Engines:**
  1. **Greedy:** 1-ply baseline evaluation.
  2. **Minimax:** Negamax formulation with customizable depth.
  3. **Alpha-Beta Pruning:** Enhanced with Transposition Tables (Zobrist hashing), Killer Moves, Quiescence Search, Iterative Deepening, and Move Ordering.
  4. **Monte Carlo Tree Search (MCTS):** Bandit-based selection using UCB1 formula with random rollouts.
  5. **Hybrid Engine:** Adaptive phase-switching mechanism using Alpha-Beta during opening/mid-game and handing over to MCTS during the end-game based on board piece counts.
- **Full-Stack Web Interface:** Handcrafted HTML/CSS/JS frontend connected to a Flask HTTP API with live search telemetry (node counts, execution time, active engine phase, etc.).
- **Reproducible Benchmarks & Tests:** Over 131 passing Pytest cases with reproducible seeded benchmark scripts.

---

## 📊 Pipeline Overview

1. **Player Interaction:** The player interacts with the web board UI to initiate a move[cite: 6].
2. **Frontend Request:** The browser sends an HTTP JSON POST request to the Flask API endpoints[cite: 6, 10].
3. **Session Management:** `GameSession` validates turn order, game state history, and current move legality[cite: 6].
4. **Engine Routing:** The engine router directs the request to the active selected AI engine[cite: 6].
5. **Search Execution:** The AI engine queries the **Rules Core** for move validation and evaluates positions using the **Static Evaluator**[cite: 6].
6. **Telemetry & Response:** The engine returns a standardized `SearchResult` payload containing the optimal move along with real-time performance telemetry (expanded nodes, time taken, search depth, and current game phase) back to the client interface[cite: 6, 10].

---

## 🛠️ How to Get Started

### 1. Clone the Repository
```bash
git clone [https://github.com/sadiamim329/AI-Project.git](https://github.com/sadiamim329/AI-Project.git)
cd AI-Project
