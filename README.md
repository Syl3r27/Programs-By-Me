#include <iostream>
#include <cstdlib>
#include <ctime>

void playRussianRoulette() {
    int chambers[6] = {0, 0, 0, 0, 0, 1}; // 1 bullet, 5 empty chambers
    
    // Shuffle the chambers to simulate spinning the cylinder
    std::srand(static_cast<unsigned>(std::time(0)));
    for (int i = 0; i < 6; ++i) {
        int randIndex = std::rand() % 6;
        std::swap(chambers[i], chambers[randIndex]);
    }

    // Simulate firing the gun
    std::cout << "Spinning the chamber...\n";
    int shot = chambers[std::rand() % 6];

    if (shot == 1) {
        std::cout << "Bang! You're shot.\n";
    } else {
        std::cout << "Click! You're safe.\n";
    }
}

int main() {
    playRussianRoulette();
    return 0;
}
