# Saidawan Radio — Static Web Player

This repository contains the published static web entry point for Saidawan Radio.

- **Website:** https://saidawan-radio.github.io/
- **Organization:** https://github.com/saidawan-radio

## Purpose

The site is the presentation layer of the project. It provides a browser-based radio-style music player that displays track information and plays audio files stored in the `pocket01`–`pocket06` repositories. GitHub Raw URLs provide the audio/artwork assets; the site does not itself store the complete music library.

## Current repository structure

The inspected branch contains an `index.html` entry point that mounts the application into a `root` element and loads compiled JavaScript/CSS from `/assets/`. This is a built static frontend rather than a conventional backend application.

## Data and playback flow

1. The frontend obtains track metadata from the configured public JSON/catalogue sources.
2. It displays track details and, where available, cover artwork.
3. It uses each track's public media URL to play audio in the browser.
4. GitHub Pages serves the static application files; GitHub Raw serves media stored in the pocket repositories.

## Deployment

The repository is intended for GitHub Pages. When publishing changes, ensure the built `index.html`, asset paths, and configured catalogue URLs match the deployment base path. The current repository snapshot exposes compiled assets; if you want to modify React components or rebuild the application, locate the original frontend source and build configuration first.

## Related repositories

- [`audio-data`](https://github.com/saidawan-radio/audio-data): Telegram metadata catalogue.
- [`audio-source`](https://github.com/saidawan-radio/audio-source): JSON source aggregation.
- [`pocket01`](https://github.com/saidawan-radio/pocket01) through [`pocket06`](https://github.com/saidawan-radio/pocket06): audio and related assets.
- [Organization profile](https://github.com/saidawan-radio/.github): overall architecture and repository map.

## Important distinction

This is a **static radio-style player**, not necessarily a single continuous live audio stream delivered by Icecast or another streaming server. Audio is fetched by the listener's browser from the configured track URLs. The playback experience depends on the frontend's playlist/queue logic and the availability of the media files.
