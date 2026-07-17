# Ballad Health Organizational Development Tools

Internal web apps for the Ballad Health OD team, hosted on GitHub Pages with Firebase Firestore for real-time shared access.

**Live URL:** https://tchastain26.github.io/organizational-development-tools/

## Apps

### Orientation Bag Tracker
Plan seating and bag placement for orientation day. Configurable two-seat table layouts (default: 6-6-6, 108 chairs) with repeated rows or custom row-by-row combinations such as 6-6-4. Fill algorithm places bags center-out, front to back. Real-time sync across devices via Firebase.

### Catered Lunch Log
Running log of team catered lunches — date and what was served. Shared in real time.

### Computer Issues Tracker
Report and track computer issues in the department. Submit issues, filter by Open/Resolved, mark resolved.

### Meeting Agenda Builder
Add items to the upcoming team meeting agenda. Month navigation, anyone can contribute, check off items as discussed.

## Tech Stack

- Vanilla HTML/CSS/JS — no build tools, no frameworks
- Firebase Firestore for real-time shared state
- GitHub Pages for hosting

## Firebase

Project: `ballad-od-tools`
Config: `firebase-config.js` (root of repo)
Firestore collections: `bag-tracker`, `catered-lunches`, `computer-issues`, `meeting-agenda`

Note: Firestore is in test mode — rules expire 30 days after project creation. When they expire, set open read/write rules in Firebase Console > Firestore > Rules.

## Repo Structure

```
organizational-development-tools/
├── index.html                          # App directory / landing page
├── firebase-config.js                  # Firebase project config
├── manifest.json                       # PWA config
├── service-worker.js                   # Offline caching
├── apps/
│   ├── orientation-bag-tracker.html
│   ├── catered-lunch-log.html
│   ├── computer-issues-tracker.html
│   └── meeting-agenda-builder.html
├── styles/
│   └── main.css
└── images/
    ├── icon-192.png
    └── icon-512.png
```

## Deploying Changes

```bash
git add .
git commit -m "description of change"
git push
```

GitHub Pages auto-deploys on push. Changes live in ~1 minute.
