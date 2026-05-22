# First Game 🗡️
## Godot 4 — 2D Platformer

A classic **2D side-scrolling platformer** built in Godot 4 (GDScript). Play as a knight navigating tile-based platforms, jumping over enemies and collecting coins — complete with sound effects and background music.

---

## Gameplay

- Run and jump across tile-based platforms
- Avoid slime enemies (green & purple)
- Collect coins and fruit pickups
- Background music + full sound effects (jump, hurt, coin, explosion, power-up)

---

## Controls

| Key | Action |
|---|---|
| `←` / `→` | Move left / right |
| `Space` / `↑` | Jump |

---

## Project Structure

```
First Game/
├── Scripts/
│   └── player.gd          ← Player movement & physics
├── Scenes/
│   ├── game.tscn          ← Main game scene
│   ├── player.tscn        ← Player character scene
│   └── platform.tscn      ← Platform scene
├── Assets/
│   ├── sprites/
│   │   ├── knight.png     ← Player sprite sheet
│   │   ├── slime_green.png
│   │   ├── slime_purple.png
│   │   ├── coin.png
│   │   ├── fruit.png
│   │   ├── platforms.png
│   │   └── world_tileset.png
│   ├── sounds/
│   │   ├── jump.wav
│   │   ├── coin.wav
│   │   ├── hurt.wav
│   │   ├── explosion.wav
│   │   ├── power_up.wav
│   │   └── tap.wav
│   ├── music/
│   │   └── time_for_adventure.mp3
│   └── fonts/
│       ├── PixelOperator8.ttf
│       └── PixelOperator8-Bold.ttf
└── project.godot
```

---

## How To Run

1. Install **[Godot 4](https://godotengine.org/download)**
2. Open Godot → **Import Project** → select `project.godot`
3. Open `Scenes/game.tscn` and press **Play**

---

## Player Stats

| Parameter | Value |
|---|---|
| Speed | 130 px/s |
| Jump Velocity | -300 px/s |
| Physics | `CharacterBody2D` + `move_and_slide()` |
