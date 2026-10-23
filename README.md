# 🎬 MovieExplorer

MovieExplorer is a responsive movie discovery web application built with **React, Vite, and Tailwind CSS**. It uses the **TMDB API** to display real movie information, allowing users to explore trending and popular movies, search for movies, filter results, view movie details, watch trailers, and save their favorite movies.
## 🖼️ MovieExplorer – Image Integration
<img width="1037" height="383" alt="image" src="https://github.com/user-attachments/assets/0e6b6ed3-003f-4969-bb03-81167988bc16" /> 
<img width="1058" height="411" alt="image" src="https://github.com/user-attachments/assets/c0f807ac-4f01-48fb-8484-620fc7d7230b" />
<img width="1058" height="373" alt="image" src="https://github.com/user-attachments/assets/65690192-9588-448c-b46a-1f708f2c4a99" />
<img width="1019" height="289" alt="image" src="https://github.com/user-attachments/assets/59503d28-a853-4149-8eca-545d01d62b26" />
<img width="1031" height="287" alt="image" src="https://github.com/user-attachments/assets/88674845-2714-449e-bb5a-fd68980b416c" />


## ✨ Features

- **Trending Movies** — Discover movies trending on TMDB.
- **Popular Movies** — Explore currently popular movies.
- **Top-Rated Movies** — Find highly rated movies.
- **Now Playing** — Browse movies currently playing in theaters.
- **Upcoming Movies** — Discover upcoming releases.
- **Movie Search** — Search for movies by title.
- **Filters** — Filter movies by genre, year, and language.
- **Sorting** — Sort movie results using supported sorting options.
- **Pagination** — Load additional movies and browse result pages.
- **Movie Details** — View movie descriptions, ratings, release years, and images.
- **YouTube Trailers** — Watch available movie trailers inside the movie details modal.
- **Favorites** — Save favorite movies using browser `localStorage`.
- **Responsive Design** — Use the application on desktop, tablet, and mobile screens.
- **Loading and Error States** — Handle loading, empty results, and API errors.

## 🛠️ Technologies Used

- React
- Vite
- JavaScript
- Tailwind CSS
- TMDB API
- YouTube embedded player
- Lucide React
- Browser `localStorage`

## 📋 Prerequisites

Before running the project, make sure you have:

- Node.js installed
- npm installed
- A TMDB account and API key
- Git installed (for version control)

## 🚀 Getting Started

### 3. Install dependencies

```bash
npm install
```

### 4. Configure the TMDB API key

Create a `.env` file in the project root directory.

```env
VITE_TMDB_API_KEY=your_actual_tmdb_api_key
```

Replace `your_actual_tmdb_api_key` with your own TMDB API key.

The application reads the key in `tmdb.js` using:

```js
const API_KEY = import.meta.env.VITE_TMDB_API_KEY;
```

**Important:** Do not commit your `.env` file to GitHub. Since Vite exposes `VITE_` variables in browser-side code, this key is not a secret once the application runs in the browser. For production applications requiring confidential credentials, use a backend to protect them.

### 5. Start the development server

```bash
npm run dev
```

Open the local URL shown in your terminal, usually:

```text
http://localhost:5173
```

## 🔌 TMDB API Integration

MovieExplorer uses TMDB to retrieve real movie data.

The API integration is organized in `src/Locals/tmdb.js`.

### How it works

1. Store the TMDB API key in `.env`.
2. Read the key using `import.meta.env.VITE_TMDB_API_KEY`.
3. Define the TMDB API base URL.
4. Use a reusable `fetchTMDB()` function to send requests and handle errors.
5. Create helper functions for trending, popular, top-rated, now-playing, upcoming, search, discover, movie details, and trailer requests.
6. Format the API response using `formatMovie()` and `formatMovieResults()`.
7. Pass the formatted movie data to React components for display.

### Trailer integration

The `getMovieTrailer(movieId)` function requests video metadata from TMDB for the selected movie. It selects a suitable YouTube trailer when one is available.

The movie details modal uses the returned YouTube video key to construct an embed URL and display the trailer through an HTML `<iframe>`.

No separate YouTube API key is required just to embed a publicly embeddable YouTube video.

## 💾 Favorites

The application uses browser `localStorage` to save favorite movies. This allows favorites to remain available after refreshing the page in the same browser, provided the stored data is not cleared.

Favorites are stored locally and are not automatically synchronized across different devices.

## 📜 Available Scripts

| Command | Description |
|---|---|
| `npm run dev` | Start the development server |
| `npm run build` | Create a production build |
| `npm run preview` | Preview the production build |
| `npm run lint` | Run linting, if configured in `package.json` |

## 🐛 Troubleshooting

**Movies are not loading**
- Check your internet connection.
- Verify your TMDB API key in `.env`.
- Confirm that the API key has the required access.
- Check the browser console and Network tab for errors.
- Restart the Vite development server after changing `.env`.

**Images are not displaying**
- Verify that the TMDB image URL and poster path are valid.
- Check the browser Network tab for failed image requests.
- Confirm that a fallback image is provided when a poster is missing.

**Trailers are not playing**
- Check whether TMDB returned a YouTube trailer for that movie.
- Verify that the returned video key is used in the embed URL.
- Some YouTube videos do not allow embedding.

**Favorites are missing**
- Check whether browser `localStorage` has been cleared.
- Ensure the application reads and writes favorites using the same storage key.

## 🔒 Environment Variables

Never upload your actual `.env` file containing credentials.

Add the following to `.gitignore` if it is not already present:

```gitignore
node_modules/
dist/
.env
.env.*
!.env.example
```

You can commit an `.env.example` file containing only a placeholder:

```env
VITE_TMDB_API_KEY=your_tmdb_api_key_here
```

## 👨‍💻 Contributing

1. Fork the repository.
2. Create a feature branch.
3. Make your changes.
4. Test the application.
5. Submit a pull request.

## 📄 Disclaimer

This project is intended for educational and demonstration purposes. Movie metadata and related images are provided through TMDB. MovieExplorer is not endorsed or certified by TMDB.

This product uses the TMDB API but is not endorsed or certified by TMDB.

## 📬 Contact

For questions, suggestions, or bug reports, please open an issue in the GitHub repository.
