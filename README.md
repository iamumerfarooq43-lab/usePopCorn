# 🍿 usePopcorn

A React-based movie discovery and personal watchlist app powered by the [OMDb API](https://www.omdbapi.com). Search for any movie, explore details, rate it with a star system, and keep track of everything you've watched — all saved locally in your browser.

---

## 🚀 Features

- 🔍 **Real-time movie search** — results appear as you type (min. 3 characters)
- 🎬 **Detailed movie view** — poster, plot, cast, director, genre, IMDb rating & runtime
- ⭐ **Star rating system** — rate movies on a 1–10 scale before adding to your list
- 💾 **Persistent watchlist** — saved to `localStorage`, survives page refresh
- 📊 **Watchlist summary** — avg. IMDb rating, avg. user rating, avg. runtime
- ⌨️ **Keyboard shortcuts** — `Enter` to focus search, `Escape` to close movie details
- ❌ **Delete from watchlist** — remove any movie from your watched list
- 🚫 **Race condition handling** — uses `AbortController` to cancel stale API requests

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| React 18+ | UI library & component framework |
| JavaScript (ES6+) | Core language |
| CSS3 | Custom styling |
| OMDb API | Live movie data |
| localStorage | Client-side data persistence |
| AbortController | Cancels in-flight fetch requests |

---

## 🪝 Custom Hooks

| Hook | Description |
|---|---|
| `useMovies(query)` | Fetches movies from OMDb, manages loading/error states |
| `useLocalStorageHook(initialState, key)` | Syncs React state with localStorage |
| `useKey(key, action)` | Global keyboard event listener with auto cleanup |

---

## 📁 Project Structure
```
src/
├── App.js                  # Root component, state & layout
├── StarRating.js           # Reusable star rating component
├── useMovies.js            # Custom hook — movie search & fetch
├── useLocalStorageHook.js  # Custom hook — localStorage persistence
├── useKey.js               # Custom hook — keyboard shortcuts
├── index.css               # Global styles
└── index.js                # React DOM entry point
```

---

## ⚙️ Getting Started

### Prerequisites

- Node.js v16+
- A free OMDb API key → [omdbapi.com/apikey.aspx](https://www.omdbapi.com/apikey.aspx)

---

## 📦 Component Tree
```
App
├── NavBar
│   ├── Logo
│   ├── Search
│   └── NumResults
└── Main
    ├── Box (Left — Search Results)
    │   └── MovieList → Movie
    └── Box (Right — Watchlist / Details)
        ├── MovieDetails → StarRating
        ├── WatchedSummary
        └── WatchedMoviesList → WatchedMovie
```

---

## 🎯 Built With Learning In Mind

This project demonstrates real-world React patterns including custom hooks, component composition, controlled inputs, derived state, and side effect management with `useEffect` and `useRef`.
