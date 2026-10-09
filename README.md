# Food Finder

Find free food in Austin. Live at [foodfinder.wiki](https://foodfinder.wiki).

Food Finder is a two-page web app that shows free food resources around Austin, like food pantries, community fridges, and pop-ups. One page is a map and the other is a bulletin board, and every location links between the two.

Built April 3-4, 2026 at the HackTX Hack Hack Goose hackathon by Jia Luthra and Zara Siddiqi.

## Features

- **Map:** an interactive Leaflet map with a pin for each location. Clicking a pin shows the address, hours, a short description, and a link to that location's note on the bulletin board.
- **Bulletin board:** each location appears as a sticky note with its details and photo, plus a link back to its pin on the map.
- **Two-way links:** the links use URL fragments (for example `bulletin.html#hope-food-pantry`), so opening one scrolls to and highlights the right note, or zooms the map to the right pin and opens its popup.
- **Community posts:** anyone can add a free food event to the board with a name, location, date, details, and an optional link.

## How it works

All location data lives in one file, `data.js`. Both pages read from it, so adding one entry there creates the map pin, the sticky note, and the links between them. There is no backend or build step.

| File | Purpose |
|---|---|
| `data.js` | The list of locations (name, address, coordinates, hours, description, image) |
| `index.html`, `script.js` | The map page |
| `bulletin.html`, `bulletin.js` | The bulletin board and post form |
| `style.css` | Shared styles for both pages |

## Built with

HTML, CSS, JavaScript, [Leaflet](https://leafletjs.com/), and OpenStreetMap tiles. Hosted on GitHub Pages.

## Run it locally

Clone the repo and open `index.html` in a browser. You need an internet connection for the map tiles.

## Known limitations

- Posts added through the form are not saved. They disappear when the page reloads because there is no database yet.
- Photo uploads on the post form are not hooked up yet.
- The list of locations is small and maintained by hand.

## Next steps

- Save community posts so they persist
- Finish photo uploads
- Add more locations and filters for day and time