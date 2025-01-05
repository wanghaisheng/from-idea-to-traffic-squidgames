# Triplit Schema Definition

    This document outlines the schema for our Triplit database.

    ## Collections

    ### Users

    *   **Collection Name:** `users`
    *   **Fields:**
        *   `UserID` (String, Primary Key): Unique identifier for the user (UUID).
        *   `username` (String): User's display name.

    ### Scores

    *   **Collection Name:** `scores`
    *   **Fields:**
        *   `ScoreID` (String, Primary Key): Unique identifier for the score entry (UUID).
        *   `UserID` (String, Foreign Key referencing `users.UserID`): ID of the user who achieved the score.
        *   `GameID` (String): Identifier for the game (e.g., "red-light-green-light", "dalgona-candy").
        *   `score` (Number): The score achieved in the game.
        *   `time` (Number, Optional): Time taken to complete the game (in seconds or milliseconds).
        *   `date` (String): Date when the score was achieved (ISO date string).

    ### Games

    *   **Collection Name:** `games`
    *   **Fields:**
        *   `GameID` (String, Primary Key): Unique identifier for the game (e.g., "red-light-green-light").
        *   `gameName` (String): Display name of the game (e.g., "Red Light, Green Light").

    ## Relationships

    *   `scores.UserID` references `users.UserID` (One-to-Many: One user can have multiple scores).

    ## Indexes (To be determined based on query patterns)

    *   Consider indexing `scores.UserID` and `scores.GameID` for efficient leaderboard queries.
    *   Consider indexing `users.username` for efficient user lookup.

    ## Example Data

    **Users:**

    ```json
    [
      { "UserID": "a1b2c3d4-e5f6-7890-1234-567890abcdef", "username": "PlayerOne" },
      { "UserID": "f9e8d7c6-b5a4-3210-9876-543210fedcba", "username": "GameMaster" }
    ]
    ```

    **Scores:**

    ```json
    [
      { "ScoreID": "l0m9n8o7-p6q5-4321-0fed-cba987654321", "UserID": "a1b2c3d4-e5f6-7890-1234-567890abcdef", "GameID": "red-light-green-light", "score": 150, "time": 15.2, "date": "2024-11-05" },
      { "ScoreID": "z9y8x7w6-v5u4-5678-90ab-cdef01234567", "UserID": "f9e8d7c6-b5a4-3210-9876-543210fedcba", "GameID": "dalgona-candy", "score": 80, "time": 28.5, "date": "2024-11-05" }
    ]
    ```

    **Games:**

    ```json
    [
      { "GameID": "red-light-green-light", "gameName": "Red Light, Green Light" },
      { "GameID": "dalgona-candy", "gameName": "Dalgona Candy" }
    ]
    ```

    **Further Considerations:**

    *   Review and adjust indexes based on actual query patterns during development.
    *   Consider adding more fields as needed (e.g., timestamps for creation/update).
