# 🚆 Bangladesh Railway Ticket Booking Autobot

A fast, clean, and intelligent Google Chrome Extension (Manifest V3) built to automate ticket booking on the official **Bangladesh Railway E-Ticketing Portal** ([eticket.railway.gov.bd](https://eticket.railway.gov.bd/)).

Designed with human-paced interactions, adjacent seat prioritization, real-time Bangladesh Standard Time (BST) synchronization, and a modern zero-scroll UI.

---

## ✨ Features

### 1. ⚡ Automatic Route Search & Form Filling

- Automatically enters **From Station**, **To Station**, **Journey Date**, and **Seat Class**.
- Handles Bangladesh Railway's autocomplete dropdown reliably.
- Triggers search automatically whether you start from the homepage (`/`, `/en`, `/home`) or search results.

### 2. 🚆 Direction-Independent Train Matching

- Matches trains cleanly by **name** rather than direction numbers.
- Works both ways for outbound and return journeys (e.g., `Dhaka → Kishoreganj` or `Kishoreganj → Dhaka` for _Kishoreganj Express_).

### 3. 🎯 Smart Seat Selection (Middle & Beside Priority)

- **1 Seat**: Prioritizes comfortable middle-window seats near the center of the coach.
- **2, 3, 4 Seats**: Always searches for adjacent side-by-side seats in the same row or directly across the aisle.
- Only selects the exact number of seats specified (1, 2, 3, or 4 seats) — no accidental double bookings.

### 4. 📊 Most-Available Coach Prioritization

- Evaluates all available compartments (coaches) in real time.
- Automatically selects seats from the coach with the **highest number of available seats** (e.g., coach with 42 seats over coach with 5 seats) to maximize booking success.

### 5. ⚙️ Built-In Station & Train Manager

- Add, edit, and delete stations (with station codes) anytime.
- Add, edit, and delete train names without touching the codebase.
- One-click restore to default train and station lists.
- Settings are saved automatically via `chrome.storage.local`.

### 6. 🕒 Live Bangladesh Standard Time (BST)

- Live digital clock synchronized with Asia/Dhaka time zone right in the header bar.
- Essential for timing 8:00 AM (intercity) and 8:00 PM advance ticket releases down to the second.

### 7. 🛡️ User Verification & Payment Safety Halt

- Pauses automation when reaching CAPTCHA or OTP input for secure manual entry.
- Halts when reaching the payment gateway so you can complete payment safely with bKash, Nagad, cards, etc.

### 8. 🎨 Clean, Minimalist UI

- Compact dark-themed dashboard that fits cleanly on your screen without scrolling.
- Quick date selectors: **Today**, **Tomorrow**, **+2 Days**, **+3 Days**.
- Adjustable speed presets: **Ultra (50ms)**, **Fast (150ms)**, **Normal (350ms)**, **Safe (600ms)**.
- Collapsible Activity Log for troubleshooting.

---

## 📂 Project Structure

```text
├── manifest.json                  # Manifest V3 extension configuration
├── index.html                     # Popup UI entry point
├── assets/
│   ├── popup-C-4qXFbC.js         # React 18 popup application bundle
│   └── popup-Bl4wzrQn.css         # Modern dark-theme stylesheet
├── background/
│   └── serviceWorker.js          # MV3 Background service worker & state coordinator
└── content/
    └── content.js                # DOM automation engine & intelligent seat selector
```

---

## 🚀 How to Install in Google Chrome

Follow these steps to load this extension into Google Chrome:

### Step 1: Download or Clone the Repository

Clone the repository with git:

```bash
git clone https://github.com/your-username/RailwayBooking.git
```

_(or download as a ZIP file from GitHub and extract it)_

### Step 2: Open Chrome Extensions

1. Open Google Chrome.
2. In the address bar, type:
   ```text
   chrome://extensions
   ```
   and press **Enter**.

### Step 3: Enable Developer Mode

- In the top-right corner of the Extensions page, toggle on **Developer mode**.

### Step 4: Load the Extension

1. Click the **Load unpacked** button in the top-left corner.
2. Select the folder containing `manifest.json` (the `dist` folder or root project folder).
3. Click **Select Folder**.

### Step 5: Pin to Toolbar

- Click the puzzle piece icon (Extensions) next to the address bar.
- Find **Railway Ticket Booking Tools** and click the pin (📌) icon to keep it accessible.

---

## 📖 How to Use

1. **Log in** to your account at [https://eticket.railway.gov.bd/](https://eticket.railway.gov.bd/).
2. Click the **Railway Booking** extension icon in your Chrome toolbar.
3. Configure your trip:
   - **From / To**: Select origin and destination stations.
   - **Date**: Click a quick button (_Tomorrow_, _+2 Days_, etc.) or pick from the calendar.
   - **Train**: Type or select your target train.
   - **Class**: Choose your seat class (e.g., `S_CHAIR`, `SNIGDHA`, `AC_B`).
   - **Seats**: Select 1, 2, 3, or 4 seats.
   - **Speed**: Choose human pacing (Fast `150ms` or Normal `350ms` recommended).
4. Click **START AUTOBOT**.
5. The extension will automatically:
   - Navigate to or submit the search on Bangladesh Railway.
   - Find your target train and class.
   - Switch to the coach with the most tickets available.
   - Select middle / adjacent seats beside each other.
   - Stop and highlight the **Continue** button.
6. Review your ticket details and proceed to checkout securely!

---

## 🛠️ Tech Stack

- **Platform:** Google Chrome Extension (Manifest V3)
- **Frontend:** React 18, Lucide Icons, CSS Custom Properties
- **Background:** Chrome Extension Service Worker (`chrome.runtime`, `chrome.storage.local`)
- **Automation:** Native DOM Mutation Observer & Async Polling Engine

---

## ⚠️ Disclaimer

This tool is created for educational and personal convenience purposes to assist users with fast form-filling on the Bangladesh Railway portal. Users must comply with Bangladesh Railway's official terms of service. The developers do not store or transmit any user credentials or personal information.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
