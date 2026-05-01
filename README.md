# CatchUp Game — Min-Max AI | Python 🎮🤖

An interactive AI-powered implementation of the Catch-Up number game where a user 
plays against an AI opponent powered by the Min-Max algorithm. Players take turns 
picking numbers from {1…n} to maximize their final sum.

---

## 🧩 Problem Statement

Two players take turns choosing numbers from the set `{1, 2, 3, …, n}`. The AI 
opponent uses the Min-Max algorithm to always make the most optimal move. The player 
with the highest sum at the end wins.

---

## 📜 Rules of Play

1. Two players alternate choosing numbers from `{1, 2, …, n}` — once chosen, a number is removed.
2. Player 1 (User) goes first and picks any single number.
3. Each player must keep picking numbers until their running sum **equals or exceeds** the opponent's previous sum — then the turn passes.
4. Goal: finish with a **higher total sum** than the opponent. If not achievable, minimize the loss.
5. Game ends when all numbers are exhausted — higher sum wins, equal sums result in a tie.

---

## 🧠 Algorithm — Min-Max

The AI uses the **Min-Max algorithm** to evaluate all possible subsets of remaining 
numbers and pick the optimal move.

### How it works
- **Maximizing player (AI):** selects the subset that maximizes `AI score − User score`
- **Minimizing player (User):** opponent's moves are assumed to minimize this difference
- **Static Evaluation Function:** `heuristic = max_score − min_score`
- **Move generation:** all valid subsets of remaining numbers whose sum meets or exceeds the opponent's current score, generated via recursive backtracking

### PEAS Description

| Component | Description |
|-----------|-------------|
| **Performance** | Win (higher sum), Tie (equal sums), minimize loss margin |
| **Environment** | Set `{1…n}`, fully observable, shrinks each turn |
| **Actuators** | Select one or more numbers from the remaining set |
| **Sensors** | Available numbers, both players' running sums, opponent's last total |

---

## 🖥️ Sample Game (n = 10)

```
User's Turn
Available Numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
Enter choice: 10 → User Score: 10

AI's Turn
AI selected: 1, 2, 3, 6 → AI Score: 12

User's Turn
Available Numbers: [4, 5, 7, 8, 9]
Enter choice: 5 → User Score: 15

AI's Turn
AI selected: 7 → AI Score: 19

User's Turn
Available Numbers: [4, 8, 9]
Enter choice: 8 → User Score: 23

AI's Turn
AI selected: 9 → AI Score: 28

User's Turn
Available Numbers: [4]
Enter choice: 4 → User Score: 27

Final Scores → User: 27 | AI: 28
🏆 AI Won!
```

---

## 🛠️ Setup & Usage

### Prerequisites
- Python 3.8+
- Jupyter Notebook or Google Colab

### Run Locally

```bash
git clone https://github.com/PriyankaMenghare/CatchUp-Game-MinMax-Python.git
cd CatchUp-Game-MinMax-Python
jupyter notebook CatchUp-MinMax-AI.ipynb
```

Run all cells. When prompted, enter `n` (the highest natural number) and play 
turn-by-turn against the AI.

---

## 📁 File Structure

```
CatchUp-Game-MinMax-Python/
├── CatchUp-MinMax-AI.ipynb   # Main game notebook
└── README.md
```

---

## 📝 License

MIT License — for academic use.
