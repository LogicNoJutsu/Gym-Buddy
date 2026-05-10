# 🏋️ GymBuddy

A personal gym & swimming tracking app for **Venky** and **Anchita** — built as a single HTML file, hosted on GitHub Pages, and synced via GitHub Gist.

---

## 🌐 Live App

**[logicnojutsu.github.io/Gym-Buddy](https://logicnojutsu.github.io/Gym-Buddy/)**

> **Note:** The file in this repo must be named `index.html` for GitHub Pages to serve it correctly.

---

## ✨ Features

### 👤 Two Profiles
- **Venky** — 5'6", Bulk & Recomp goal
- **Anchita** — 5'3", Fat Loss & Toning goal
- Each profile has its own independent workout tracking, weight log, and stats

### 📅 7-Day Workout Splits
| Day | Venky | Anchita |
|-----|-------|---------|
| Monday | Chest + Triceps | Arms + Abs |
| Tuesday | Back + Biceps | Cardio + Full Body |
| Wednesday | Shoulders + Abs | Arms + Shoulders |
| Thursday | Legs + Glutes | Lower Body + Abs |
| Friday | Chest + Arms | Arms + Cardio |
| Saturday | Back + Shoulders | Full Body + Tummy Focus |
| Sunday | Full Body / Recovery | Yoga + Stretch |

### 🏋️ Workout Sessions
- Warm-up → Main exercises → Cool-down structure
- Tappable set circles with pop animation
- Progress bar tracking per session and per day
- Notes field per exercise to log weights used
- Reschedule any day to another day

### 💡 Exercise Instructions
Each exercise has 3 tabs:
- **Tips** — technique cues and coaching notes
- **Posture** — Start Position + End Position images (from ExerciseDB via jsDelivr CDN)
- **Video** — direct YouTube search link

### ⚖️ Weight Tracking
- Tap the ⚖️ icon on each profile card to log your weight
- Shows last 3 entries with date stamps on the landing screen
- Stores up to 10 entries per profile

### 🏊 Swimming Tracking
- Tap the **🏊 Swims** chip on the workout home screen to log a swim session
- Track laps, duration (minutes), and distance (metres)
- Monthly swim count shown in the top bar
- Last 3 sessions shown in the log modal

### 📊 Attendance Tracking
- Gym days counter shown as **X/Y** (days attended / today's date)
- Auto-increments every time you open your profile
- Tracked per calendar month

### 🔥 Streak & Progress
- Weekly progress bar (days completed / 7)
- Streak counter based on consecutive days done

### ☁️ GitHub Gist Sync
- Sync all data between Venky & Anchita's devices automatically
- Auto-pushes on every change, auto-pulls on app open
- Manual push/pull available in Settings

---

## ⚙️ Setup Guide

### GitHub Pages (hosting the app)
1. Rename `gymbuddy.html` → `index.html` in this repo
2. Go to repo **Settings** → **Pages** → Source: `main` branch, root `/`
3. Visit `https://logicnojutsu.github.io/Gym-Buddy/`

### GitHub Gist Sync (data sharing between devices)
Both Venky and Anchita need to do this **once** on their own device.

#### Step 1 — Create a Gist
1. Go to [gist.github.com](https://gist.github.com)
2. Filename: `gymbuddy-data.json`
3. Content: `{}`
4. Click **Create secret gist**
5. Copy the Gist ID from the URL: `gist.github.com/logicnojutsu/`**`<THIS_PART>`**

#### Step 2 — Create a GitHub Token
1. Go to [github.com](https://github.com) → your avatar → **Settings**
2. Scroll to **Developer settings** → **Personal access tokens** → **Tokens (classic)**
3. Click **Generate new token (classic)**
4. Name: `GymBuddy Sync`
5. Expiration: `No expiration` (or set a date)
6. Scopes: tick **`gist`** only
7. Click **Generate token** — copy it immediately (shown only once)

#### Step 3 — Connect in the app
1. Open GymBuddy → tap ⚙️ (top right of landing screen)
2. Paste your **GitHub Token**
3. Paste the **Gist ID**
4. Tap **Save & Test Connection**
5. Repeat on the other person's device with the **same** Gist ID and token

> Data now syncs automatically every time anything changes.

---

## 📱 Adding to iPhone Home Screen (PWA-style)
1. Open the app in **Safari** on iPhone
2. Tap the **Share** button (box with arrow)
3. Scroll down → tap **Add to Home Screen**
4. Name it `GymBuddy` → tap **Add**
5. It now opens full-screen like a native app

---

## 🛠 Tech Stack
- Pure **HTML + CSS + JavaScript** — no frameworks, no build step
- **localStorage** for offline data persistence
- **GitHub Gist API** for cross-device sync
- **jsDelivr CDN** for exercise images (ExerciseDB, open license)
- **Google Fonts** — Bebas Neue + DM Sans
- Hosted on **GitHub Pages**

---

## 📁 File Structure
```
Gym-Buddy/
├── index.html      ← The entire app (rename from gymbuddy.html)
└── README.md       ← This file
```

---

## 🔄 Data Sync Architecture
```
Device A (Venky)          GitHub Gist            Device B (Anchita)
      │                  gymbuddy-data.json              │
      │  ──── push ────►  { sets, weights,  }            │
      │                   { swims, streaks  }            │
      │  ◄─── pull ────   { gymDays, notes  }  ◄── push ─┤
      │                                                  │
  auto-sync on change                         auto-sync on change
  auto-pull on open                           auto-pull on open
```

---

## 🙏 Credits
- Exercise images: [yuhonas/free-exercise-db](https://github.com/yuhonas/free-exercise-db) (MIT License)
- Served via [jsDelivr](https://www.jsdelivr.com/) CDN
- Built with ❤️ for Venky & Anchita
