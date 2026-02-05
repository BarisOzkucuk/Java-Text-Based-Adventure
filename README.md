# ⚔️ Java Text-Based Adventure Game

A comprehensive text-based RPG (Role Playing Game) developed in Java. This project demonstrates core **Object-Oriented Programming (OOP)** principles such as Inheritance, Polymorphism, and Abstraction through a modular game architecture.

## 🎮 Game Overview

In this survival adventure, the player creates a character, fights against various monsters to collect specific loot items, and aims to complete the game by gathering all rewards.

* **Objective:** Collect all unique awards (Food, Firewood, Water) from different battle zones and return safely to the Safe House.
* **Genre:** Text-Based RPG / Survival / Strategy
* **Tech Stack:** Java (JDK 8+)

## 🚀 Features

### 1. Character System (`Player` Class)
Players can choose from three distinct character classes with unique stats:
* **Samurai:** Balanced stats (Damage: 5, Health: 21, Money: 15)
* **Archer:** High agility/damage potential (Damage: 7, Health: 18, Money: 20)
* **Knight:** High durability (Damage: 8, Health: 24, Money: 5)

### 2. Robust Map System (`Location` Architecture)
The game world is built on an abstract `Location` architecture, divided into two main categories:
* **Safe Zones:**
    * 🏠 **Safe House:** Players regain full health. The game is won here if all items are collected.
    * 🏪 **Tool Store:** Players can purchase weapons (Gun, Sword, Rifle) and armor (Light, Medium, Heavy) using gold earned from battles.
* **Battle Zones:**
    * 🧟 **Cave:** Infested with Zombies (1-3 spawns). Reward: `Food`.
    * 🧛 **Forest:** Home to Vampires (1-3 spawns). Reward: `Firewood`.
    * 🐻 **River:** Territory of Bears (1-3 spawns). Reward: `Water`.

### 3. Dynamic Combat Mechanics (`BattleLoc` Class)
* **Turn-Based System:** A dynamic combat loop where player and monster exchange hits until one falls or the player retreats.
* **RNG (Random Number Generation):** Enemy spawn rates (1 to 3) are randomized for replayability.
* **Inventory & Loot:** Integrated inventory system tracks gathered awards (`isFood`, `isWater`, `isFirewood`) and equipment stats.

## 🛠️ Technical Architecture (OOP Concepts)

This project is a practical implementation of software engineering principles:

* **Abstraction:** `Location` and `BattleLoc` are abstract classes defining the blueprint for all game zones.
* **Inheritance:** `Cave`, `Forest`, and `River` extend `BattleLoc`, while `SafeHouse` and `ToolStrore` extend `NormalLoc`.
* **Polymorphism:** The `getLocation()` method is overridden in every subclass to handle unique events (Combat logic vs. Menu logic).
* **Encapsulation:** Player attributes (Health, Damage, Money) are `private` and accessed via encapsulated getter/setter methods to ensure data integrity.

## 💻 How to Run

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/BarisOzkucuk/Adventure-Game.git](https://github.com/BarisOzkucuk/Adventure-Game.git)
    ```
2.  **Navigate to the source folder:**
    ```bash
    cd Adventure-Game/src
    ```
3.  **Compile the source code:**
    ```bash
    javac Main.java
    ```
4.  **Run the game:**
    ```bash
    java Main
    ```

## 📂 Project Structure

The project follows a modular file structure separating logic, entities, and environment:

```text
src/
├── Main.java         # Application entry point
├── Game.java         # Main game loop and logic controller
├── Player.java       # User character stats and inventory link
├── Inventory.java    # Manages collected items and equipment
├── Location.java     # Abstract base class for all maps
├── NormalLoc.java    # Abstract class for non-combat zones
├── BattleLoc.java    # Abstract class for combat zones
├── SafeHouse.java    # Logic for healing and winning conditions
├── ToolStrore.java   # Shop system logic (Weapons & Armors)
├── Cave.java         # Battle zone implementation (Spawns Zombies)
├── Forest.java       # Battle zone implementation (Spawns Vampires)
├── River.java        # Battle zone implementation (Spawns Bears)
├── Obstacle.java     # Base class for all enemies
├── Zombie.java       # Enemy entity: Low damage, Low health
├── Vampire.java      # Enemy entity: Medium damage, Medium health
└── Bear.java         # Enemy entity: High damage, High health

ℹ️ Acknowledgements
This project is based on the comprehensive Java backend curriculum by Patika.dev and the "Kodlama Vakti" YouTube channel.
 It has been refactored and implemented by Barış Özküçük to demonstrate proficiency in Java Syntax, OOP Design Principles, and Game Logic Implementation.
