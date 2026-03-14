# NewsApp

A mobile-friendly news app built with **Vue 3**, **Vite**. It loads top headlines from the [GNews API](https://gnews.io/), with search, filter by number of articles, and responsive card layout.

## Features

- **Headlines** – Fetch top news articles (title, date, source, image, link).
- **Search** – Filter articles by title, author, or content as you type.
- **Filter** – Choose how many articles to load (1–50) via a toggle panel.
- **Responsive** – Works on desktop and mobile; max width ~1200px on large screens.
- **Offline fallback** – If the API returns 403 (invalid key or quota), sample articles with dates are shown so the app still runs.

## Prerequisites

- **Node.js** 18+ (LTS recommended)
- **npm** (included with Node)
- **GNews API key** (free at [gnews.io](https://gnews.io/))

## Quick start

### 1. Install dependencies

```bash
npm install
```

### 2. Set your API key (optional but recommended)

Create a `.env` file in the project root:

```env
VITE_GNEWS_API_KEY=your_gnews_api_key_here
```

Get a key at [gnews.io](https://gnews.io/). Without a valid key, the API returns 403 and the app shows sample articles instead.

### 3. Run in the browser

```bash
npm run dev
```

Open the URL shown (e.g. `http://localhost:5173/`).

### 4. Build for production

```bash
npm run build
```

Output is in the `dist` folder.

## Run on mobile (Capacitor)

### iOS

```bash
npm run build
npx cap sync ios
npx cap open ios
```

Build and run from Xcode on a simulator or device.

### Android

```bash
npm run build
npx cap sync android
npx cap open android
```

Build and run from Android Studio.

## Project structure

- `src/App.vue` – Root component, renders the articles view.
- `src/components/Articles.vue` – Header, filter panel, search bar, and article list (GNews fetch, search, filter logic).
- `src/style.css` – Global CSS variables (colors, shadows) used by the app.
- `index.html` – Entry HTML; loads Material Icons for search/filter icons.

## Tech stack

- **Vue 3** (Composition API, `<script setup>`)
- **Vite**
- **Axios** (HTTP requests to GNews)
- **Capacitor** (optional native iOS/Android)
- **CSS variables** in `src/style.css` for theming

## API note

The app uses the GNews **top-headlines** endpoint. Free tier limits (e.g. request count or `max` articles) apply. For 403 errors, check your key and quota at [gnews.io](https://gnews.io/).
