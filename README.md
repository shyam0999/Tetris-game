# Tetris Game (Console-Based)

This is a simple **console-based Tetris game** written in C++ without any external libraries like SFML. The game is played using ASCII characters in the terminal.

## 🚀 Features
- **Fully playable Tetris game** in the console
- **Real-time keyboard controls** for movement and rotation
- **Automatic block dropping** with adjustable speed
- **Basic collision detection** for stacking blocks

## 🎮 Controls
- **A** → Move Left
- **D** → Move Right
- **S** → Drop Faster
- **W** → Rotate Block
- **Esc** → Quit (Manually close the console)

## 🛠 How to Compile & Run

### Windows
1. Open **Command Prompt** and navigate to the game folder:
   ```sh
   cd path\to\your\tetris-game
   ```
2. Compile using **MinGW**:
   ```sh
   g++ tetris.cpp -o tetris.exe -std=c++11
   ```
3. Run the game:
   ```sh
   tetris.exe
   ```

### Linux/macOS
1. Open **Terminal** and navigate to the game folder:
   ```sh
   cd path/to/your/tetris-game
   ```
2. Compile using **g++**:
   ```sh
   g++ tetris.cpp -o tetris -std=c++11
   ```
3. Run the game:
   ```sh
   ./tetris
   ```

## 🔧 Notes
- The game **currently only works properly on Windows** because it uses `_kbhit()` and `_getch()` from `<conio.h>`.
- For **Linux/macOS support**, `_kbhit()` needs to be replaced with a proper `termios` implementation.
- The console **clears** itself every frame to simulate movement.

## 📜 License
This project is open-source and free to use. Feel free to modify and improve it!

