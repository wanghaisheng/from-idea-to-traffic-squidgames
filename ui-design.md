# UI Design Details

    This document outlines the detailed UI design for each page within the Squid Game Challenge PWA. It includes descriptions of each page, the color palette used, and the layout of elements.

    ## Color Palette

    The primary color scheme for the application is inspired by the *Squid Game* series, featuring a dark background with vibrant neon accents.

    *   **Primary Background:** `#121212` (Dark Gray)
    *   **Secondary Background:** `#1E1E1E` (Slightly Lighter Dark Gray)
    *   **Primary Text Color:** `#FFFFFF` (White)
    *   **Secondary Text Color:** `#B0B0B0` (Light Gray)
    *   **Accent Color 1 (Neon Green):** `#39FF14`
    *   **Accent Color 2 (Neon Pink):** `#FF1493`
    *    **Accent Color 3 (Squid Green):** `#1A7E2C`
    *   **Button Color (Primary):** `#39FF14`
    *   **Button Text Color (Primary):** `#000000`
    *   **Error Color:** `#FF4136` (Red)
    *   **Success Color:** `#2ECC40` (Green)

    ## Page Designs

    ### 1. Landing Page

    *   **Description:** The first page users see, introducing the game and providing a way to start playing.
    *   **Color Palette:** Primarily uses the Primary Background, Primary Text Color, and Accent Color 1 for the "Play Now!" button. Game preview icons may use Accent Color 2.
    *  **Logo Placeholder:** Use a basic shape that incorporates the core elements of a circle, triangle, and square, filled with  `#FFFFFF` (White).
    *   **Layout:**
        *   **Header:**
            *   Centered title: "Squid Game Challenge" (Primary Text Color, potentially using an outlined or neon effect with Accent Color 1).
               *    **Placeholder Logo:** A placeholder for the logo should be placed in the top left corner.
        *   **Hero Section (Centered on the page):**
            *   Large title: "Squid Game Challenge" (Primary Text Color, larger font size).
            *   Tagline: "Are you ready for the challenge?" (Secondary Text Color, smaller font size).
            *   Horizontal row of game preview icons (using placeholder images initially). Icons can have a subtle neon glow (Accent Color 1 or 2) on hover.
            *   Prominent "Play Now!" button (Button Color (Primary), Button Text Color (Primary)). Button should be large and easily tappable/clickable.
        *   **Footer:**
            *   Simple copyright information or links (Secondary Text Color).

    ### 2. Game Selection Page

    *   **Description:** Displays a list of available mini-games for the user to choose from.
    *   **Color Palette:** Primarily uses the Secondary Background, Primary Text Color, and Accent Colors for highlights and interactive elements.
    *   **Layout:**
        *   **Header:**
            *   Centered title: "Select a Game" (Primary Text Color).
            *   Back button (icon or text, Secondary Text Color, can highlight on hover).
        *   **Main Content Area (Grid or Flexbox layout):**
            *   Each game is represented by a visually distinct card or tile.
            *   **Game Tile/Card:**
                *   Placeholder image or icon for the game.
                *   Game title (Primary Text Color).
                *   Brief description (Secondary Text Color, optional).
                *   "Play" button for the specific game (Button Color (Primary), Button Text Color (Primary)).
                *   Tiles should be arranged in a responsive grid that adapts to different screen sizes.
        *   **Footer:** (Optional) Navigation or settings links.

    ### 3. Individual Game Page (Template - Specifics will vary per game)

    *   **Description:** The interface for playing a specific mini-game.
    *   **Color Palette:** Primarily uses the Secondary Background, Primary Text Color. Game-specific elements will use Accent Colors for interactive parts.
    *   **Layout:**
        *   **Header:**
            *   Game title (Primary Text Color, centered).
            *   Back button (icon or text, Secondary Text Color).
            *   Potentially a pause button or icon.
        *   **Game Area (Central and prominent):**
            *   The main interactive area where the game is played.
            *   Background of this area may vary depending on the game (e.g., a canvas element).
        *   **Information Panel (Top or Bottom):**
            *   Timer display (Primary Text Color, can use Accent Color 2 for emphasis).
            *   Score display (Primary Text Color, can use Accent Color 1 for emphasis).
            *   Game instructions (toggleable or brief inline text, Secondary Text Color).
        *   **Controls Area (Bottom or Sides):**
            *   Game-specific control buttons or indicators. Buttons should use Button Color (Primary) and Button Text Color (Primary).
        *   **Game Over/Win Overlay:**
            *   A modal or overlay that appears when the game ends.
            *   Displays "Game Over" or "You Win!" (Success Color for Win, Error Color for Over).
            *   Final score.
            *   Buttons: "Play Again", "Back to Menu", "Share Score".

    ### 4. Settings Page

    *   **Description:** Allows users to configure application settings, such as language and sync options.
    *   **Color Palette:** Primarily uses the Secondary Background, Primary Text Color, and Accent Colors for interactive elements.
    *   **Layout:**
        *   **Header:**
            *   Centered title: "Settings" (Primary Text Color).
            *   Back button (icon or text, Secondary Text Color).
        *   **Main Content Area (List or Form layout):**
            *   **Language Selection:**
                *   Label: "Language" (Primary Text Color).
                *   Dropdown or list of available languages. Selected language highlighted with an Accent Color.
            *   **Sync Settings:**
                *   Label: "Enable Sync" (Primary Text Color).
                *   Toggle switch (inactive state can be a dark gray, active state can use Accent Color 1).
            *   **User Profile:**
                *   Label: "Username" (Primary Text Color).
                *   Display current username (Secondary Text Color).
                *   "Change Username" button (Button Color (Primary), Button Text Color (Primary)).
        *   **Footer:** (Optional) Links to terms of service, privacy policy, etc.

    ### 5. Leaderboard Page

    *   **Description:** Displays the top scores for each game.
    *   **Color Palette:** Primarily uses the Secondary Background, Primary Text Color. Highlight top scores or user's score with Accent Colors.
    *   **Layout:**
        *   **Header:**
            *   Centered title: "Leaderboard" (Primary Text Color).
            *   Back button (icon or text, Secondary Text Color).
        *   **Main Content Area (Tabbed or Sectioned layout):**
            *   Sections or tabs for each game.
            *   **Leaderboard Table for each game:**
                *   Columns: Rank, Username, Score, Time (optional), Date (optional).
                *   Table headers (Secondary Text Color).
                *   Table rows with player data (Primary Text Color).
                *   Highlight the current user's score row with a subtle background color or Accent Color.
                *   Top scores (e.g., top 3) can be visually emphasized with different styling or icons (using Accent Colors).
        *   **Footer:** (Optional) Information about leaderboard updates.

    ### 6. User Profile Page

    *   **Description:** Displays the user's profile information and provides access to settings.
    *   **Color Palette:** Primarily uses the Secondary Background, Primary Text Color. Interactive elements use Accent Colors.
    *   **Layout:**
        *   **Header:**
            *   Centered title: "User Profile" (Primary Text Color).
            *   Back button (icon or text, Secondary Text Color).
        *   **Main Content Area:**
            *   **Username Display:**
                *   Label: "Username" (Primary Text Color).
                *   Display username (Primary Text Color, larger font).
                *   "Edit" button next to the username (Button Color (Primary), Button Text Color (Primary)).
            *   **Statistics (Optional):**
                *   Display user's high scores for each game.
                *   Number of games played.
            *   **Navigation Links:**
                *   Link to the "Settings" page (using styled links or buttons).
        *   **Footer:** (Optional) Logout button.

    **General UI Considerations:**

    *   **Typography:** Use clear and readable fonts. Consider using a primary font for headings and a secondary font for body text.
    *   **Spacing and Padding:** Maintain consistent spacing and padding throughout the application for a clean and organized look.
    *   **Iconography:** Use consistent and easily recognizable icons. Consider using a specific icon library.
    *   **Responsiveness:** Ensure all pages adapt well to different screen sizes and orientations. Use flexible layouts (Flexbox or Grid).
    *   **Interactions:** Provide clear visual feedback for user interactions (e.g., button presses, hover effects). Use subtle animations for transitions where appropriate.
    *   **Accessibility:** Follow accessibility guidelines (WCAG) regarding color contrast, keyboard navigation, and screen reader compatibility.
