# Project Plan: Squid Game Challenge PWA

    ## Project Structure

    ```
    squid-game-challenge/
    ├── index.html          (Main HTML file)
    ├── style.css           (Main CSS file)
    ├── app.js              (Main JavaScript file)
    ├── service-worker.js   (Service worker for offline support)
    ├── assets/             (Folder for images, icons)
    └── triplit.js          (Triplit library)
    ```

    ## Phase 1: Landing Page & Core Setup

    **Goal:** Develop a compelling and visually striking landing page using placeholder assets. Establish the project's core structure, including the initial HTML layout, basic styles, and foundational JavaScript functions. Implement the basics for the local storage and Triplit connectivity. Set up offline functionality for the landing page using a service worker.

    **Note:** During this phase, placeholder images, icons, and a basic logo will be used for rapid development. Production-ready assets will be integrated in a later phase. The logo placeholder will include a circle, a triangle, and a square.

    **Detailed Requirements:**

    ### 1. Project Setup

    *   [ ] Create the project directory `squid-game-challenge/`.
    *   [ ] Create `index.html`, `style.css`, and `app.js` files in the root directory.
    *   [ ] Create an `assets/` folder for images and icons.
    *   [ ] Initialize a Git repository in the root directory.

    ### 2. HTML Structure (`index.html`)

    *   [ ] Include a `<head>` section with:
        *   [ ] `<meta charset="UTF-8">`
        *   [ ] `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
        *   [ ] `<title>Squid Game Challenge</title>`
        *   [ ] `<link rel="stylesheet" href="style.css">`
        *   [ ] Service worker registration.
        *   [ ] Link to the manifest file (create a basic `manifest.json` if not already done).
    *   [ ] Include a `<body>` section with:
        *   [ ] `<header>` containing:
          *  [ ]  **Placeholder Logo:** A placeholder for the logo in the top left corner.
        *   [ ] `<section id="hero">` containing:
            *   [ ] Large title: "Squid Game Challenge".
            *   [ ] Tagline: "Are you ready for the challenge?".
            *   [ ] **Placeholder** preview of games (simple colored squares or basic icons for 5 planned games).
            *   [ ] "Play Now!" button.
            *   [ ] **Placeholder** Background (e.g., a solid gray color or a simple pattern).
        *   [ ] `<footer>`.
        *   [ ] Link to JavaScript: `<script src="app.js"></script>`.
        *   [ ] Link to Triplit library: `<script src="triplit.js"></script>`.

    ### 3. CSS Structure (`style.css`)

    *   [ ] Global Styles:
        *   [ ] Dark background color (e.g., `#121212`).
        *   [ ] Basic font settings (e.g., sans-serif).
        *   [ ] Reset default margins and paddings.
    *   [ ] Styles for the hero section:
        *   [ ] Layout of title, tagline, and game preview.
        *   [ ] **Placeholder** background styles.
        *   [ ] "Play Now!" button styles (including hover effects).
        *   [ ] Use `rem` units for sizing.
    *   [ ] Responsive design for mobile devices (using media queries).

    ### 4. Triplit Setup (`app.js`)

    *   [ ] Include the Triplit library in `index.html`.
    *   [ ] Implement the client connection to the Triplit server in `app.js`.

    ### 5. Service Worker (`service-worker.js`)

    *   [ ] Create `service-worker.js`.
    *   [ ] Functionality:
        *   [ ] Cache `index.html`, `style.css`, `app.js`, `triplit.js`, and placeholder assets in the `assets/` folder.
        *   [ ] Serve cached files when offline.
    *   [ ] Implement service worker registration in `app.js`.
    *   [ ] Implement fetch events to check cache first.
    *   [ ] Implement logic for caching assets and updating the cache.

    ### 6. Local Storage Functions (`app.js`)

    *   [ ] Implement `loadLocalData()` function:
        *   [ ] Retrieve data from `localStorage` using the key "squidGameData".
        *   [ ] Parse and return data, or an empty object if not found.
    *   [ ] Implement `saveLocalData(data)` function:
        *   [ ] Stringify the provided `data` object.
        *   [ ] Save to `localStorage` using the key "squidGameData".

    ### 7. User Creation (`app.js`)

    *   [ ] Implement `createUser(username)` function:
        *   [ ] Generate a random UUID for the user ID.
        *   [ ] Save the user object (including `UserID` and `username`) to local storage.

    **Deliverables for Phase 1:**

    *   [ ] Functional and visually basic landing page using placeholder assets, including a logo placeholder with a circle, a triangle, and a square
    *   [ ] Basic local storage setup.
    *   [ ] Offline landing page functionality.
    *   [ ] Triplit basic connection ready.
    *   [ ] User creation functionality.

    **Note:** This `plan.md` file will be used as a checklist during the implementation of Phase 1. Ensure each item is checked off upon completion. Remember that placeholder assets are expected for this phase and will be replaced later.

    ## Backend API Strategy (Offline and Online)

    We will leverage Triplit as our client-side database, which will serve as the "backend API" when the application is offline.

    **Offline Mode:**

    *   Triplit will be the single source of truth for data.
    *   UI will interact directly with the local Triplit database using queries.
    *   No separate mock backend API is needed for offline scenarios.

    **Online Mode:**

    *   When online, Triplit will automatically synchronize local data with the remote database (if configured).
    *   UI interactions and data fetching will primarily use Triplit, which manages the synchronization.

    **Initial Data Population:**

    *   We will explore options for initial data population, such as seed data or fetching data on the first online sync.

    ## Internationalization (i18n)

    We will implement internationalization for UI labels, allowing users to change the language in the settings.

    **Implementation Plan:**

    1. **Translation Files:** Create JSON files for each supported language (e.g., `en.json`, `es.json`).
    2. **i18n Library:** Integrate an i18n library (e.g., `i18next`).
    3. **Loading Translations:** Implement logic to load translation files based on the user's selected language.
    4. **Applying Translations:** Use the i18n library to dynamically translate UI labels.
    5. **Language Setting:**
        *   Add a language selection control to the settings page.
        *   Persist the selected language in `localStorage`.
        *   Implement logic to reload translations and update the UI when the language is changed.
    6. **User Data i18n (Future Consideration):** We will initially focus on UI label translation. User data i18n may be considered for future enhancements.

    **Phase-Specific Considerations:**

    *   **Phase 1:** Focus on setting up the basic project structure and potentially hardcoding UI labels. Plan for the i18n implementation.
    *   **Phase 2:** Implement the i18n library and basic translation setup for key UI elements. Add the language setting to the settings page.
    *   **Phase 3:** Translate all UI labels across the application.
    *   **Phase 4:** Test the i18n implementation thoroughly.

    ## Mock Backend API Strategy

    During the development process, we will utilize mock backend API endpoints to enable parallel frontend and backend development.

    **Implementation Plan:**

    1. **API Contract Definition:** Frontend and backend teams will agree on API endpoints and data structures.
    2. **Mocking Strategy:** We will initially use static JSON files to simulate API responses. For more complex interactions, we may consider using a mocking library like `fetch-mock`.
    3. **Mock Data Creation:** JSON files containing mock data will be created in a `/mock-api` directory (or similar).
    4. **Frontend Implementation:** Frontend code will fetch data from these mock endpoints.
    5. **Switching to Real API:** A configuration variable (`useMockApi`) will be used to toggle between mock and real API endpoints.

    **Phase-Specific Considerations:**

    *   **Phase 1:** Focus on setting up the basic structure and potentially using static JSON for any data needed on the landing page (if any).
    *   **Phase 2:** Implement mock API endpoints for fetching game data, leaderboard data, etc., using static JSON or in-memory data.
    *   **Phase 3:** As the backend develops, gradually replace mock API calls with calls to the real API, toggling the `useMockApi` setting.
