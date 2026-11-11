# PlatformGame - A 2D Platformer Game

PlatformGame is a 2D side-scrolling platformer written in plain Java (Swing/AWT, no external libraries). You run, jump and fight through several levels, defeat enemies, avoid traps and collect potions to finish each level.

## Table of Contents

1. [Features](#features)
2. [Controls](#controls)
3. [Tech Stack](#tech-stack)
4. [Project Structure](#project-structure)
5. [Build and Run](#build-and-run)
6. [Contributing](#contributing)
7. [License](#license)

## Features

- **Multiple levels** – levels are built from the images in `res/lvls/` (`1.png` – `5.png`); finishing one level loads the next, and a "game completed" screen is shown at the end.
- **Enemies** – Crabby, Pinkstar and Shark enemies.
- **Hazards and objects** – spikes, cannons that fire cannonballs, barrels and boxes that can be broken, and decorative trees and grass.
- **Potions** – red potions restore health and blue potions restore power.
- **Combat** – normal attack and a power attack that uses the power bar; health and power bars are shown on screen.
- **Game states** – main menu, playing, options (audio settings), credits, pause overlay, game over, level completed and game completed screens.
- **Audio** – background music for the menu and levels plus sound effects (jump, attacks, death, game over, level completed), with volume and mute controls.
- **Effects** – rain particles and enemy dialogue (question / exclamation) indicators.

## Controls

| Input             | Action        |
| ----------------- | ------------- |
| `A`               | Move left     |
| `D`               | Move right    |
| `Space`           | Jump          |
| Left mouse click  | Attack        |
| Right mouse click | Power attack  |
| `Esc`             | Pause / resume |

Menus and overlays are navigated with the mouse.

## Tech Stack

- Java (uses switch arrow syntax, so JDK 14 or newer is required)
- Java Swing / AWT for the window, rendering and input
- `javax.sound.sampled` for audio

## Project Structure

```
src/
├── audio/       # AudioPlayer: background music and sound effects
├── effects/     # Rain particles, dialogue effects
├── entities/    # Player, Enemy base class, Crabby, Pinkstar, Shark, EnemyManager
├── gamestates/  # Menu, Playing, GameOptions, Credits, Gamestate enum
├── inputs/      # Keyboard and mouse input handlers
├── levels/      # Level and LevelManager
├── main/        # MainClass (entry point), Game (game loop), GamePanel, GameWindow
├── objects/     # Cannon, Projectile, Potion, Spike, GameContainer, trees, grass, ObjectManager
├── ui/          # Buttons and overlays (pause, game over, level completed, audio options)
└── utilz/       # Constants, HelpMethods, LoadSave (resource loading)
res/
├── audio/       # .wav music and sound effects
├── lvls/        # Level layout images
└── *.png, *.gif # Sprite sheets, backgrounds and UI images
```

## Build and Run

There is no build tool configuration (Maven/Gradle) in the repository. Assets are loaded from the classpath root (for example `/lvls` and `/player_sprites.png`), so the `res` folder must be on the classpath when running.

### From the command line

From the repository root (on Windows, use `;` instead of `:` as the classpath separator):

```bash
mkdir -p out
javac -d out $(find src -name "*.java")
java -cp out:res main.MainClass
```

### From an IDE

Import the project into your IDE (e.g. Eclipse or IntelliJ IDEA), mark `src` as a source folder and `res` as a resource folder (or add it to the build path), then run `main.MainClass`.

## Contributing

Contributions to the PlatformGame project are welcome:

1. Fork the repository on GitHub.
2. Create a new branch for your feature or bug fix.
3. Implement your changes and improvements.
4. Submit a pull request.

## License

No license file is included in the repository (needs confirmation).
