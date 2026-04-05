# 🎬 CineScope — Interactive Movie Explorer

A responsive, single-page movie discovery app built with Vanilla JavaScript and the TMDB API.

[![Live Demo](https://img.shields.io/badge/Live-Demo-green?style=for-the-badge)](https://your-live-url.netlify.app)
[![GitHub Repo](https://img.shields.io/badge/GitHub-Repo-blue?style=for-the-badge)](https://github.com/yourusername/cinescope)

---

## ✨ Features

- 🔍 **Live Search** — Debounced search with real-time filtering as you type
- 🎭 **Genre Filtering** — Browse movies by genre using quick-select chips
- 📄 **Movie Detail Modal** — Click any movie for full details (rating, runtime, overview, backdrop)
- 📦 **Pagination** — "Load More" button for progressive loading
- ⏳ **Loading State** — Animated skeleton cards while data is fetching
- ❌ **Error State** — Friendly UI for network errors or empty results
- 📱 **Fully Responsive** — Works on mobile (2-col), tablet, and desktop (auto-fill grid)
- 🎨 **Clean Dark UI** — Custom design with CSS variables and smooth animations

---

## 🛠 Technologies Used

| Technology | Purpose |
|---|---|
| HTML5 | Markup & semantic structure |
| CSS3 | Styling, animations, responsive grid |
| JavaScript (ES6+) | App logic, API calls, DOM manipulation |
| TMDB API | Movie data source (free, public) |
| Google Fonts | Typography (Bebas Neue + DM Sans) |

> No frameworks used — pure Vanilla JS to keep things lean and demonstrate fundamentals clearly.

---

## 🌐 API Used

**[The Movie Database (TMDB)](https://www.themoviedb.org/)**

Endpoints used:
- `GET /trending/movie/week` — Home feed (trending movies)
- `GET /search/movie?query=` — Search
- `GET /discover/movie?with_genres=` — Genre filter
- `GET /genre/movie/list` — Genre list for chips
- `GET /movie/{id}` — Full movie detail for the modal

Get a free API key at: https://www.themoviedb.org/settings/api

---

## 📁 Project Structure

```
cinescope/
├── index.html       # All HTML, CSS, and JS in one file
└── README.md        # This file
```

> Everything is in a single `index.html` for simplicity and zero-config deployment.

---

## 🚀 Setup & Run

### Option 1 — Just open the file
```bash
# Clone the repo
git clone https://github.com/yourusername/cinescope.git
cd cinescope

# Open in browser
open index.html
```

### Option 2 — Local dev server
```bash
npx serve .
# Then visit http://localhost:3000
```

### ⚠️ API Key
Replace the `API_KEY` constant in `index.html` with your own TMDB key:
```js
const API_KEY = 'your_api_key_here';
```

---

## 🏗 Architecture Decisions

### State Management
All app state is managed through simple JavaScript variables:
```
currentQuery, currentGenre, currentPage, totalPages, isLoading, genreMap
```
No external library needed — the app is small enough that prop drilling / direct DOM updates are clear and maintainable.

### Component Approach
While this is Vanilla JS (not React/Vue), I followed a component-inspired structure:
- `createCard(movie)` — Renders a single movie card element
- `showSkeletons()` — Renders loading placeholder cards
- `openModal(id)` — Fetches and renders the detail modal
- `fetchMovies(append)` — Core data-fetching function with full state handling

### Search Debouncing
Search input triggers an API call after a **450ms debounce** — fast enough to feel responsive, slow enough to avoid hammering the API on every keystroke.

### Error Handling
- Network errors show a user-friendly error state in the grid
- Modal fetch errors show an inline message
- A toast notification system provides non-blocking feedback

### Responsive Design
Uses CSS `grid` with `auto-fill` and `minmax()` — no media query breakpoints needed for the card grid. Additional breakpoints handle typography and modal sizing.

---

## 📸 Screenshots

> *(Add screenshots of your running app here)*

---

## 🙏 Credits

- Movie data: [TMDB](https://www.themoviedb.org/)
- Icons: SVG from [Feather Icons](https://feathericons.com/)
- Fonts: [Google Fonts](https://fonts.google.com/)

---

*Built as part of the Frontend Developer Intern Assignment — April 2026*
