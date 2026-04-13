---
title: "Bibliothèque de jeux Java"
translationKey: "java-games"
date: 2026-03-20
featured_image: "/images/projects/java-games/hero.gif"
summary: "Conception d’une bibliothèque de jeux rétro (Pac-Man, échecs, morpion) entièrement en Java, avec une architecture extensible et une gestion du rendu via AWT/Swing."
---


Ce projet consiste en une plateforme de jeux développée entièrement en **Java**. L'objectif était de construire un système modulaire capable d'héberger différents types de logiques de jeux au sein d'une interface unique.


{{< figure src="/images/gif/menu.gif" width="45%" alt="Démo Pacman" class="text-center" >}}

---

## 🏗️ Architecture modulaire

Le cœur du projet repose sur un système de menu dynamique. Grâce à l'utilisation d'interfaces et de classes abstraites, l'ajout d'un nouveau jeu se fait sans modifier le code existant (respect du principe **Open/Closed** de SOLID).

- **Custom GUI :** L'interface du menu et des jeux ne s'appuie pas sur des composants standards préfabriqués. J'ai utilisé `Graphics2D` pour dessiner et positionner manuellement les éléments (pancartes, logos, sprites).
- **Moteur de menu :** Gestion centralisée du cycle de vie des jeux (initialisation, lancement, retour via KeyBinding).
- **Interface `GameModule` :** Le contrat. Chaque jeu implémente une structure commune (Wrapper), isolant la logique spécifique du jeu et facilitant l'intégration de nouveaux modules .

---

## 🎮 Les Jeux

### 1. Pacman
*Gestion du temps réel et de la logique de collision.*
{{< figure src="/images/gif/pacman.gif" width="25%" alt="Démo Pacman" class="text-center" >}}
- **Défis techniques :** Implémentation d'une "Game Loop" personnalisée pour garantir 60 FPS, gestion du multithreading pour le mouvement fluide et autonome des fantômes.
- **Algorithmique :** Détection de collision spatiale continue et gestion du pathfinding sur une grille matricielle.

### 2. Échecs
*Logique métier et validation d'états complexes.*
{{< figure src="/images/gif/chess.gif" width="30%" alt="Démo Pacman" class="text-center" >}}
- **Défis techniques :** Conception d'un moteur de règles exhaustif (détection d'échec, mouvements légaux par type de pièce).
- **Structures de données :** Représentation du plateau par une matrice d'objets typés, avec parcours de graphe virtuel pour simuler les états futurs avant validation d'un coup.

### 3. Tic Tac Toe
*Fondations et interface utilisateur.*
{{< figure src="/images/gif/tictactoe.gif" width="30%" alt="Démo Pacman" class="text-center" >}}
- **Focus :** Gestion native des événements (MouseListener) sur des coordonnées 2D et conception d'algorithmes de détection de motifs (lignes, colonnes, diagonales) dans une matrice $3 \times 3$.

---

## 🧠 Perspectives IA

Bien que les jeux actuels reposent sur des règles déterministes, il serait possible d'intégrer des modules d'Intelligence Artificielle :
- **Échecs :** Possibilité d'intégrer un algorithme *Minimax* avec élagage *Alpha-Bêta*.
- **Pacman :** Introduction d'un agent d'apprentissage par renforcement capable de jouer au jeu.

---

## 🛠️ Stack Technique

- **Langage :** Java (JDK 17+)
- **GUI :** Swing, AWT, Java2D
- **IDE :** Apache NetBeans
- **Build System :** Ant

[Voir le code source sur GitHub ↗](https://github.com/Poportee/java_games_library)