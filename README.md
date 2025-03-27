#include <iostream>
#include <vector>
#include <conio.h> // For keyboard input
#include <windows.h> // For Sleep function
#include <cstdlib>

const int WIDTH = 10;
const int HEIGHT = 20;

// Tetromino shapes
const std::vector<std::vector<std::vector<int>>> tetrominoes = {
    {{1, 1, 1, 1}}, // I
    {{1, 1}, {1, 1}}, // O
    {{0, 1, 0}, {1, 1, 1}}, // T
    {{0, 1, 1}, {1, 1, 0}}, // S
    {{1, 1, 0}, {0, 1, 1}}, // Z
    {{1, 0, 0}, {1, 1, 1}}, // J
    {{0, 0, 1}, {1, 1, 1}}  // L
};

class Tetris {
private:
    std::vector<std::vector<int>> grid;
    int score = 0;
    int level = 1;
    int speed = 500;
    
public:
    Tetris() {
        grid.resize(HEIGHT, std::vector<int>(WIDTH, 0));
    }
    
    void display() {
        system("cls");
        std::cout << "Score: " << score << "  Level: " << level << "\n";
        for (int i = 0; i < HEIGHT; i++) {
            for (int j = 0; j < WIDTH; j++) {
                std::cout << (grid[i][j] ? "#" : ".") << " ";
            }
            std::cout << "\n";
        }
    }
    
    void processInput() {
        if (_kbhit()) {
            char ch = _getch();
            switch (ch) {
                case 75: // Left arrow
                    std::cout << "Move Left\n";
                    break;
                case 77: // Right arrow
                    std::cout << "Move Right\n";
                    break;
                case 72: // Up arrow
                    std::cout << "Rotate\n";
                    break;
                case 80: // Down arrow
                    std::cout << "Soft Drop\n";
                    break;
                case 32: // Spacebar
                    std::cout << "Hard Drop\n";
                    break;
                case 27: // Escape
                    std::cout << "Pause/Exit\n";
                    exit(0);
            }
        }
    }
    
    void run() {
        while (true) {
            display();
            processInput();
            Sleep(speed);
        }
    }
};

int main() {
    Tetris game;
    game.run();
    return 0;
}

