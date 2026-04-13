---
title: "Java Game Hub"
translationKey: "java-games"
date: 2026-03-20
featured_image: "/images/projects/java-games/hero.gif"
summary: "Design of a retro games library (Pac-Man, Chess, Tic-Tac-Toe) built entirely in Java, featuring an extensible architecture and custom rendering via AWT/Swing."
excludeFromHome: true
---

This project is a gaming platform developed entirely in **Java**. The objective was to build a modular system capable of hosting various types of game logic within a single unified interface.

{{< figure src="/images/gif/menu.gif" width="45%" alt="Menu Demo" class="text-center" >}}

---

## 🏗️ Modular Architecture

The core of the project relies on a dynamic menu system. Through the use of interfaces and abstract classes, adding a new game requires no modification to existing code (respecting the **Open/Closed** principle of SOLID).

- **Custom GUI:** The menu and game interfaces do not rely on standard prefabricated components. I used `Graphics2D` to manually draw and position the elements (signs, logos, sprites).
- **Menu Engine:** Centralized management of the games' lifecycles (initialization, launching, returning via KeyBinding).
- **`GameModule` Interface:** The contract. Each game implements a common structure (Wrapper), isolating game-specific logic and facilitating the integration of new modules.

---

## 🎮 The Games

### 1. Pacman
*Real-time management and collision logic.*
{{< figure src="/images/gif/pacman.gif" width="25%" alt="Pacman Demo" class="text-center" >}}
- **Technical challenges:** Implementation of a custom "Game Loop" to ensure 60 FPS, multithreading management for fluid and autonomous ghost movement.
- **Algorithms:** Continuous spatial collision detection and pathfinding management on a grid matrix.

### 2. Chess
*Business logic and complex state validation.*
{{< figure src="/images/gif/chess.gif" width="30%" alt="Chess Demo" class="text-center" >}}
- **Technical challenges:** Design of an exhaustive rules engine (check detection, legal moves per piece type).
- **Data structures:** Representation of the board using a matrix of typed objects, with virtual graph traversal to simulate future states before validating a move.

### 3. Tic Tac Toe
*Foundations and user interface.*
{{< figure src="/images/gif/tictactoe.gif" width="30%" alt="Tic Tac Toe Demo" class="text-center" >}}
- **Focus:** Native event handling (MouseListener) on 2D coordinates and design of pattern detection algorithms (rows, columns, diagonals) within a 3x3 matrix.

---

## 🧠 AI Perspectives

Although the current games rely on deterministic rules, it would be possible to integrate Artificial Intelligence modules:
- **Chess:** Possibility of integrating a *Minimax* algorithm with *Alpha-Beta* pruning.
- **Pacman:** Introduction of a reinforcement learning agent capable of playing the game.

---

## 🛠️ Technical Stack

- **Language:** Java (JDK 17+)
- **GUI:** Swing, AWT, Java2D
- **IDE:** Apache NetBeans
- **Build System:** Ant

[View source code on GitHub ↗](https://github.com/Poportee/java_games_library)