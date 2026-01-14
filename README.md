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
Total Aura = Positive Aura − Negative Aura

---

## Word Sets

### Positive Words (12)
Hope, Joy, Peace, Trust, Love, Focus  
Calm, Strength, Growth, Light, Faith, Clarity

### Negative Words (12)
Fear, Anger, Doubt, Stress, Hate, Chaos  
Guilt, Pain, Noise, Loss, Shadow, Rage

---

- Core game logic: C++
- No assets folder
- No external libraries
- Fully deterministic behavior

---

## PalisadeOS Compatibility

Aura Words includes native compatibility layers for PalisadeOS:

### PalisadeManifest
- Registers the app as a trusted **adminApp**
- Declares permissions and install path
- Provides OS-level identity

### PalisadeRuntime
- Hooks into PalisadeOS lifecycle
- Supports init, run, pause, resume, shutdown
- Prevents unsafe execution states

### PalisadeStorage
- Sandboxed persistent storage
- Safe local save handling
- Survives OS restarts

---

## Local Persistence

Player aura values are saved locally using binary storage.

Saved data includes:
- Positive Aura
- Negative Aura

Persistence is handled safely under PalisadeOS-approved directories.

---

## Build Instructions

Compile into a single `.img` binary:

```bash
g++ *.cpp -O2 -static -o AuraWords.img
```

---

## installation path (PalisadeOS)

```
/palisade/os/framework/framework.Apps/
programIMPORTS.Custom/adminApps/
```

Once placed, the OS will recognize Aura Words as a valid native application.

---

## Design Philosophy
- Minimalism over complexity
- System-level clarity
- Emotion-driven mechanics
- No unnecessary abstractions
- Built to be extended without refactoring
- Aura Words is not a demo — it is a **complete, native PalisadeOS** game designed for clarity, stability, and expansion.