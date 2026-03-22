# 🐍 Snake

<div align="center">
  <img src="ASSETS/main.svg" width="200" alt="Snake Game Icon"/>
</div>

<div align="center">
  A classic Snake game built from scratch on <strong>Android</strong> using <strong>OpenGL ES 3.0</strong> and native C/C++.
</div>

---

## About

This project is a hands-on exploration of low-level graphics programming on Android. Instead of relying on game engines or high-level frameworks, everything is built manually — from the OpenGL shader pipeline to the game loop and input handling.

The snake eats cherries 🍒, grows longer, and the game ends when it hits a wall or itself. Simple rules, raw rendering.

## Tech Stack

| Layer       | Technology                     |
|-------------|--------------------------------|
| Platform    | Android (Native Activity)      |
| Graphics    | OpenGL ES 3.0                  |
| Native code | C / C++                        |
| Build       | CMake + Gradle                 |
| Entry point | Kotlin (`MainActivity`)        |

## Architecture

```
app/src/main/
├── kotlin/             # Kotlin entry point (MainActivity)
└── native/
    ├── main.cpp         # Game loop, input handling, swipe detection
    ├── renderer/
    │   ├── renderer.c/h # OpenGL setup, game rendering
    │   └── draw.c/h     # Shader compilation, draw primitives
    ├── game/
    │   └── snake.c/h    # Game state & logic (pure C, no GL)
    └── utils/
        └── utils.h      # Utility helpers
```

## 🎮 How It Works

- **Rendering**: A minimal OpenGL ES 3.0 pipeline with vertex/fragment shaders. Each cell on a 20x20 grid is drawn as a colored quad — no textures, no sprites, just raw triangles and uniforms.
- **Game logic**: Pure C module with no OpenGL dependencies. Manages the snake body, direction, collision detection, and cherry placement.
- **Input**: Swipe gestures mapped to direction changes. Tap to restart on game over.
- **Game loop**: Time-based ticking (~5 moves/sec) driven by `clock_gettime`.

## Colors

| Element      | Color        |
|--------------|--------------|
| Background   | Black        |
| Snake body   | Green        |
| Snake head   | Bright green |
| Cherry 🍒    | Red          |

## License

[MIT](LICENSE)