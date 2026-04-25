# ⚡ Wumpus Logic Agent

A **Knowledge-Based AI Agent** that navigates a Wumpus World grid using **Propositional Logic** and **Resolution Refutation**.

🌐 **Live Demo:** [your-vercel-url-here.vercel.app]

---

## 🧠 How It Works

### Knowledge Base (KB)
- When the agent visits a cell, it **TELLs** the KB new propositional facts in CNF
- No breeze → unit clause `¬Pit` for all neighbors
- No stench → unit clause `¬Wumpus` for all neighbors

### Resolution Refutation
- Before moving to any unvisited cell, the agent **ASKs** the KB: *"Is this cell safe?"*
- It negates the goal (`¬P` → try to prove `P` leads to contradiction)
- Pairwise resolution is applied until an **empty clause** (contradiction) is found
- If proven → cell is **safe** ✅

### Agent Strategy
1. Check all unvisited neighbors via KB resolution
2. Move to first **KB-proven safe** neighbor
3. Fallback: revisit a visited neighbor closer to gold

---

## 🚀 Features
- Dynamic grid sizing (3×3 up to 8×8)
- Configurable pit count
- Real-time inference step counter
- Active percept display (Breeze / Stench)
- KB inference log
- Auto-run mode
- Color-coded grid (Safe / Visited / Unknown / Pit / Wumpus)

---

## 📁 Project Structure
```
wumpus-agent/
├── index.html      ← Entire app (HTML + CSS + JS, no backend)
└── README.md
```

No frameworks. No dependencies. Pure HTML/CSS/JavaScript.

---

## 🛠 Run Locally
Just open `index.html` in any browser. That's it.

---

## 🌐 Deploy on Vercel
1. Push this repo to GitHub
2. Go to [vercel.com](https://vercel.com) → Import repo
3. Click Deploy — done!

---

## 📚 AI Concepts Implemented
| Concept | Implementation |
|---|---|
| Knowledge Base | Array of CNF clauses |
| TELL | `addPerceptRules()` converts percepts to CNF |
| ASK | `askSafe()` via Resolution Refutation |
| CNF Conversion | Biconditional expansion of breeze/stench rules |
| Resolution | Pairwise literal cancellation loop |

---

*Built for NUCES AI Assignment 6 — Dynamic Wumpus Logic Agent*
