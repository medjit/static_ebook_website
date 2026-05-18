# static_ebook_website

# 🎧 Minimalist Static Audiobook Player

A lightweight, purely static web application designed to host and play audiobook collections. This project features a dynamic UI driven by JSON data, automatic unit conversion for file sizes, and a custom CSS-animated "live monitor" cover.

## ✨ Features

* **Zero Backend:** Runs entirely in the browser using HTML5, CSS3, and Vanilla JavaScript.
* **JSON-Driven Playlists:** Easily manage your library by updating a single `playlistData` object.
* **Smart Formatting:**
* **Auto-scaling Sizes:** Converts file sizes from KB to MB or GB automatically for better readability.
* **Duration Formatting:** Converts total seconds into readable `HH:MM:SS` or `MM:SS` formats.


* **Interactive UI:**
* **Collapsible Folders:** Authors are grouped into folders that expand/shrink on click.
* **Dynamic Now Playing:** Real-time updates for titles and authors in the player interface.


* **Tech-Aesthetic Cover:** A standalone JS-injected "Equalizer" animation that simulates an active audio monitor.

## 🚀 Getting Started

### 1. Structure

Place your audio files in an `audio/` directory. Your project should look like this:

```text
project-root/
│
├── index.html
├── style.css
├── script.js
└── audio/
    ├── author_name/
    │   └── book_file.mp3

```

### 2. Configure the Library

Open `script.js` and update the `playlistData` object. The application automatically generates the UI based on this structure:

```javascript
const playlistData = {
  folders: [
    {
      folder_name: "author_folder",
      display_name: "Author Name",
      files: [
        {
          title: "Book Title",
          filename: "file.mp3",
          length: 3600, // In seconds
          size_kb: 51200 // In Kilobytes
        }
      ]
    }
  ]
};

```

### 3. Run

Simply open `index.html` in any modern web browser. No local server (like Node.js or Python) is required.

## 🛠️ Technical Overview

* **Initialization:** The app boots via `window.addEventListener("DOMContentLoaded", initApp)`.
* **Performance:** UI animations are CSS-driven to ensure zero CPU overhead during audio playback.
* **Data Handling:** Uses `Math.floor` and `padStart` for time calculations and a scaling loop for file size conversions.

## 📜 License

This project is open-source and free to use for personal audiobook collections.