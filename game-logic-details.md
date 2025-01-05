
    # Detailed Game Logic

    This document outlines the detailed game logic for each mini-game.

    ## 1. Red Light, Green Light

    *   **Goal:** The player must reach the finish line before time runs out, only moving when "Green Light" is displayed.
    *   **Game State:**
        *   `isPlaying`: Boolean indicating if the game is currently active.
        *   `isGreenLight`: Boolean indicating the current state of the light.
        *   `player