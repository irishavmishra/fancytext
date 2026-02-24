# Fancytext

Client-side fancy text and PUBG-style nickname generator.

Live: https://www.facehuntershow.com/

## What It Does

Fancytext converts plain input into many Unicode-decorated text variants that can be copied and used in games, social profiles, chats, and bios. It provides dozens of instantly generated styles, symbols, and decorative effects in a single-page interface.

## Key Technical Decisions

- Built as a static HTML/CSS/JavaScript app so all processing happens in the browser with zero backend dependency
- Kept the app dependency-light by using CDN-hosted Bootstrap and jQuery for layout and DOM interaction, which makes deployment as static hosting straightforward
- Included clipboard.js behavior in the client bundle to support one-click copy actions for every generated style row

## Hard Problems I Solved

1. Unicode style generation needed broad character coverage while still handling symbols and mixed input. I used transformation maps and style-specific functions so text can be converted into many visual variants while preserving unsupported characters.

2. Real-time updates across many output rows can feel laggy if rendering is inefficient. I structured generation logic to update all variants directly from a single input flow so users get immediate feedback while typing.

3. Copy UX had to be frictionless on repeated actions across many generated lines. I wired each output entry to copy targets with dedicated copy controls so users can quickly test and reuse multiple styles.

## Tech Stack

- Frontend: HTML5, CSS3, JavaScript (ES5/ES6 style)
- UI Framework: Bootstrap 4 (CDN)
- DOM Utilities: jQuery
- Icons: Font Awesome
- Clipboard: clipboard.js
- Deployment: Static hosting

## Running Locally

1. Clone the repo: `git clone <your-repo-url>`
2. Move into the project: `cd fancytext`
3. Start a local static server (example): `python3 -m http.server 3000`
4. Open `http://localhost:3000`
