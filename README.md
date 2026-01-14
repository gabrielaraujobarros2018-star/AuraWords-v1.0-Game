# Aura Words

**Aura Words** is a minimal, system-native C++ game designed to run as a first-class application on **PalisadeOS**.  
The game focuses on emotional balance mechanics using positive and negative words interacting with a player entity.

This project intentionally uses a **small directory tree**, no external assets, and local persistence to stay lightweight, auditable, and OS-friendly.

---

## Game Concept

- White background
- A **circle player** positioned on the ground
- Words slide from the right side of the screen toward the player
- Words are either **Positive** or **Negative**

### Core Rules

- Positive words:
  - Enter the player on contact
  - Grant **+20 Positive Aura**
- Negative words:
  - Must be touched **twice** to be destroyed
  - If they touch the player first, they grant **+20 Negative Aura**
- Winning condition:
  - Total Aura ≥ **100**
