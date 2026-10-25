# 🎬 CineVault — Movie Watchlist Application

A modern, responsive, dark-themed **Movie Watchlist Application** built with **ReactJS**, **Vite**, **HTML5**, **CSS3**, and **JavaScript ES6**.

Designed for cinema lovers and developed as a complete college full-stack React assignment, featuring three functional views, dynamic statistics, instant searching, multi-criteria filtering, full CRUD capabilities (Create, Read, Update, Delete), custom modal dialogs, and persistent `localStorage` synchronization.

---

## 🌟 Highlights & Key Features

### 1. 🎛️ Three Functional Views
- **Dashboard**:
  - Live metric cards: **Total Movies**, **Watched Movies**, **Unwatched (Queue) Movies**, and **Average Rating**.
  - Dynamic **Progress Bar** visualizing the percentage of watched movies.
  - **"Next Up to Watch" Recommendation**: automatically highlights the next unwatched movie with a one-click *"Mark as Watched"* button.
  - **Top Genres Breakdown**: visual pills displaying distribution of genres.
  - **Recently Added**: preview the latest additions to your library.
- **My Watchlist**:
  - Real-time search by movie title (case-insensitive).
  - Filter by **Genre** (*Action, Sci-Fi, Drama, Animation, Crime, Thriller, etc.*).
  - Filter by **Viewing Status** (*All, Watched, Plan to Watch*).
  - Sort by **Rating** (*Highest / Lowest*), **Release Year** (*Newest / Oldest*), and **Title** (*A to Z*).
  - Toggle between **Grid View** and **Table View**.
  - Full card controls: Quick Watch Status toggle, Edit modal, Delete with confirmation, and Movie Details dialog.
- **Add Movie**:
  - Clean form with live character count.
  - **Interactive 1 to 5 Star Rating** selector with hover previews.
  - Custom **Watched / Plan to Watch** toggle switch.
  - Quick poster presets or custom URL input.
  - **Live Card Preview**: renders in real-time as you type so you see how your movie card will look before adding.
  - Automatic redirect to your watchlist upon adding with a confirmation toast.

### 2. ⚡ Client-Side Form Validation
- Prevents invalid submissions with clear, inline error messages:
  - **Title**: Required and must be at least 2 characters.
  - **Genre**: Required selection from the standard genres list.
  - **Release Year**: Required integer between `1888` (first motion picture) and `2035`.
  - **Rating**: Required value between 1 and 5 stars.

### 3. 💾 LocalStorage Persistence
- Movies are saved directly into the browser's `localStorage` (`cinevault_movies_v1`).
- All changes (adding new movies, editing existing titles, toggling status, deleting) persist after page reloads.
- Pre-loaded with **8 rich sample movies** on the first visit (*Inception, Interstellar, The Dark Knight, Spirited Away, Parasite, Pulp Fiction, Dune: Part Two, Spider-Man*).
- Includes a **"Restore Sample Movies"** button in the footer and empty state to easily restore the original collection during testing.

### 4. 🎨 Cinematic Dark-Themed Aesthetic & Responsive Layout
- Tailored dark color palette: obsidian (`#080b11`), deep slate (`#0f1523`), glowing amber accents (`#f59e0b`), emerald for completed movies, and rose for delete actions.
- Glassmorphism effects with backdrop blur.
- Modern typography via Google Fonts (*Outfit* and *Plus Jakarta Sans*).
- Fully responsive on desktop computers, laptops, tablets, and smartphones.

---

## 🛠️ Technology Stack

| Technology | Purpose |
| :--- | :--- |
| **ReactJS (v19)** | Declarative UI, Component Architecture, State & Effect Hooks |
| **Vite** | Ultra-fast build tool and local development server |
| **HTML5 & CSS3** | Semantic structure, flexbox/grid layout, CSS variables, keyframe animations |
| **JavaScript (ES6+)** | Modern syntax (arrow functions, destructuring, modules, array methods) |
| **Lucide React** | Clean, modern iconography |
| **LocalStorage API** | Browser-side client data persistence |

---

## 📂 Project Structure

```text
Movie Watchlist Application/
├── index.html                   # Entry HTML with Google Fonts & metadata
├── package.json                 # Project dependencies & npm scripts
├── vite.config.js               # Vite configuration
├── README.md                    # Project documentation & setup instructions
└── src/
    ├── main.jsx                 # React root mounting point
    ├── App.jsx                  # Main state container, routing, and CRUD logic
    ├── index.css                # Global design system tokens and resets
    ├── App.css                  # Component-specific styles and animations
    ├── data/
    │   └── initialMovies.js     # Default curated movies, genres, and poster presets
    └── components/
        ├── Navbar.jsx           # Top navigation bar with active tab indicators & mobile menu
        ├── Dashboard.jsx        # Stats overview, progress bar, Next Up, top genres
        ├── Watchlist.jsx        # Filter toolbar, search bar, sort, grid & table views
        ├── AddMovie.jsx         # Add movie form with validation & live card preview
        ├── MovieCard.jsx        # Individual movie card with star rating & status toggle
        ├── EditMovieModal.jsx   # Pre-filled modal for editing movie details
        ├── MovieDetailsModal.jsx# Full synopsis modal with director & date details
        ├── DeleteConfirmModal.jsx# Safe confirmation dialog before deletion
        ├── Toast.jsx            # Animated feedback notifications
        └── Footer.jsx           # Project footer with sample reset and tech stack tags
```

---

## 🚀 How to Run the Project Locally

Follow these simple steps:

### Prerequisites
Make sure you have **Node.js** (v18 or higher) installed on your system. You can verify by opening your terminal / command prompt and running:
```bash
node -v
npm -v
```

### Step 1: Clone or Navigate to the Project Folder
Open your terminal (PowerShell, Command Prompt, or Bash) in the project directory:
```bash
cd "Movie Watchlist Application"
```

### Step 2: Install Dependencies
Install the required packages:
```bash
npm install
```

### Step 3: Start the Development Server
Launch the local Vite server:
```bash
npm run dev
```

You will see output similar to:
```text
  VITE v8.3.5 ready in 715 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
```

### Step 4: Open in Your Browser
Open your favorite browser (Chrome, Edge, Firefox, Brave) and visit:
👉 **[http://localhost:5173/](http://localhost:5173/)**

---

## 🧪 How to Test Each Feature (Grading Walkthrough)

1. **Dashboard View**:
   - Verify the 4 cards at the top: *Total Movies (8)*, *Watched Movies (5)*, *Unwatched Movies (3)*, and *Average Rating (4.9)*.
   - Look at the progress bar: it shows *63% Watched*.
   - Look at *"Next Up To Watch"*: displays an unwatched movie with a button to *"Mark as Watched"*. Click it and watch the statistics update in real-time!
2. **Search by Title**:
   - Go to **My Watchlist**.
   - In the search bar, type `Inception`. Notice only *Inception* is displayed.
   - Click the `✕` button to clear the search.
3. **Genre & Status Filtering**:
   - In the genre dropdown, select **Animation**. You will see *Spirited Away* and *Spider-Man*.
   - Click the **Watched** status button to view only watched animated movies.
   - Click **Reset Filters** to restore all movies.
4. **Grid vs Table View**:
   - Click the **Table** button in the top right to switch to list view. Click **Grid** to switch back.
5. **Adding a Movie with Form Validation**:
   - Go to **Add Movie**.
   - Try clicking **Add to Watchlist** without typing a title: notice the red inline validation error *"Movie title is required."*
   - Type a title (e.g., `Gladiator II`), choose a Genre, enter a release year, click the 5th star, toggle status to **Watched**, and click **Add to Watchlist**.
   - Notice the green toast notification and that you are automatically redirected to the Watchlist where your new movie is displayed at the top!
6. **Editing a Movie**:
   - On any movie card, click the **Pencil icon (Edit)**.
   - Modify the rating or notes, then click **Save Changes**.
7. **Deleting a Movie**:
   - Click the **Trash icon (Delete)** on a movie card.
   - A confirmation dialog appears asking to confirm. Click **Delete Movie**. The movie is removed with a toast notification.
8. **Testing LocalStorage Persistence**:
   - Refresh your browser tab (`F5` or `Ctrl + R`).
   - Notice that your added, edited, or deleted movies remain exactly as you left them!
9. **Restoring Sample Data**:
   - Scroll to the footer and click **"Restore Sample Movies"** anytime to reset back to the original 8 movies.

---

## 💡 Key React Concepts Used (For Viva / College Evaluation)

1. **Functional Components & JSX**: Clean, modular components (`Navbar`, `MovieCard`, `Dashboard`, etc.) returning declarative JSX syntax.
2. **`useState` Hook**:
   - Used for managing `movies` list, `activeTab` navigation, `searchTerm`, `selectedGenre`, `selectedStatus`, `sortBy`, `viewMode`, modal states, and form inputs.
3. **`useEffect` Hook**:
   - Automatically saves any update in `movies` to `localStorage` whenever the state changes.
   - Manages auto-dismiss timers for toast notifications.
4. **Conditional Rendering**:
   - Displaying active tab views, modal overlays, empty state messages when no search results match, and inline validation warnings.
5. **Controlled Form Components**:
   - All input fields are controlled by React state (`value={title}`, `onChange={...}`), enabling real-time validation and live card previewing.
6. **Props & Lifting State Up**:
   - The root component (`App.jsx`) holds the shared movie list and passes handler functions down to children (`onToggleWatched`, `onEdit`, `onDelete`).
