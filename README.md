# 🎬 Movie Finder

A full-stack MERN application that lets users search for movies using the TMDB (The Movie Database) API, browse popular titles, and save favorites to a personal collection backed by MongoDB.

![Status](https://img.shields.io/badge/status-active-success)
![License](https://img.shields.io/badge/license-MIT-blue)

## 📸 Screenshots

> Add screenshots here after running the app locally, e.g.:
> `![Home Page](./screenshots/home.png)`

## ✨ Features

- 🔍 Search movies by title using the TMDB API
- 🎞️ Browse trending/popular movies on load
- ❤️ Save and remove favorite movies (persisted in MongoDB)
- ⚡ Fast, responsive UI built with React + Vite
- 🔐 API key kept secure on the backend (never exposed to the client)
- 🧱 Clean REST API with proper error handling

## 🛠️ Tech Stack

**Frontend:** React 18, React Router, Vite, Axios
**Backend:** Node.js, Express
**Database:** MongoDB (Mongoose ODM)
**External API:** [TMDB API](https://www.themoviedb.org/documentation/api)

## 📁 Folder Structure

```
movie-finder/
├── backend/
│   ├── config/
│   │   └── db.js              # MongoDB connection
│   ├── models/
│   │   └── Favorite.js        # Favorite movie schema
│   ├── routes/
│   │   ├── movies.js          # TMDB proxy routes
│   │   └── favorites.js       # Favorites CRUD routes
│   ├── server.js              # Express app entry point
│   ├── package.json
│   └── .env.example
├── frontend/
│   ├── src/
│   │   ├── api/                # Axios API clients
│   │   ├── components/         # React components
│   │   ├── App.jsx
│   │   ├── App.css
│   │   ├── main.jsx
│   │   └── index.css
│   ├── index.html
│   ├── package.json
│   └── .env.example
└── README.md
```

## 🚀 Getting Started

### Prerequisites

- Node.js v18+
- MongoDB running locally or a MongoDB Atlas connection string
- A free [TMDB API key](https://www.themoviedb.org/settings/api)

### 1. Clone the repository

```bash
git clone https://github.com/your-username/movie-finder.git
cd movie-finder
```

### 2. Backend Setup

```bash
cd backend
npm install
cp .env.example .env
# then edit .env and add your MONGO_URI and TMDB_API_KEY
npm run dev
```

The backend runs on `http://localhost:5000` by default.

### 3. Frontend Setup

Open a new terminal:

```bash
cd frontend
npm install
cp .env.example .env
npm run dev
```

The frontend runs on `http://localhost:5173` by default.

## 🔑 Environment Variables

**backend/.env**

| Variable | Description |
|---|---|
| `PORT` | Port for the Express server (default `5000`) |
| `MONGO_URI` | MongoDB connection string |
| `TMDB_API_KEY` | Your TMDB API key |
| `TMDB_BASE_URL` | TMDB API base URL |
| `CLIENT_ORIGIN` | Frontend URL, used for CORS |

**frontend/.env**

| Variable | Description |
|---|---|
| `VITE_API_BASE_URL` | URL of the backend API |

## 📡 API Endpoints

### Movies (proxied from TMDB)

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/movies/search?query=&page=` | Search movies by title |
| GET | `/api/movies/popular?page=` | Get popular movies |
| GET | `/api/movies/:id` | Get details for a single movie |

### Favorites

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/favorites` | Get all saved favorites |
| POST | `/api/favorites` | Save a movie to favorites |
| DELETE | `/api/favorites/:tmdbId` | Remove a movie from favorites |

## 🧪 Possible Improvements

- User authentication (JWT) so each user has their own favorites list
- Pagination controls on search results
- Movie detail page with cast, trailer, and reviews
- Debounced live search
- Dark/light theme toggle

## 📄 License

This project is licensed under the MIT License — free to use and modify.

## 🙌 Acknowledgements

- Movie data provided by [The Movie Database (TMDB)](https://www.themoviedb.org/)
