# prowl

**Prowl** is an uncompromising, local-first scouting and pit management web application built for the **First Robotics Competition (FRC)**. Designed to operate flawlessly in network-banned, low-connectivity stadium environments, Prowl uses a fully decentralized architecture to collect data in the stands and compile it instantly in the pits—all without requiring an internet connection.

## 🚀 Key Features

*   **100% Offline-First (PWA):** Installable on any iOS, Android, Windows, Mac, or ChromeOS device. Runs entirely out of the local browser cache.
*   **QR Data Pipeline:** Compresses robust JSON match metrics into highly dense QR codes to sync data from the stands to the pit manager without cell service.
*   **Dexie.js Local Storage:** Backed by IndexedDB for high-speed, persistent data storage right on the scout's hardware.
*   **Dual-Purpose Interface:** Built-in modular systems for both match scouting tracks and pit mechanic checklists.

## 🛠️ Tech Stack

*   **Framework:** React 18+ via [Vite][1] (TypeScript template)
*   **PWA Wrapper:** `vite-plugin-pwa`
*   **Database:** [Dexie.js][2] (IndexedDB wrapper)
*   **Compression:** `lz-string` (For ultra-dense QR payloads)
*   **QR Engines:** `qrcode.react` (Generator) & `html5-qrcode` (Scanner)

## 📦 Getting Started

### Prerequisites

Ensure you have [Node.js][3] installed (v18 or higher recommended).

### Installation

1. Clone the repository:
```bash
git clone https://github.com/plooof/prowl.git
cd prowl
```

2. Install dependencies:
```bash
npm install
```

3. Run the development server locally:
```bash
npm run dev
```

4. Build the offline production static assets:
```bash
npm run build
```

## 🗜️ The Data Workflow

```
[ Stand Scouts: Phones/Tablets ] 
      │ 
      ├──> Saves data locally to IndexedDB (via Dexie.js)
      └──> Generates Compressed QR Code on screen via lz-string
            │
            ▼
[ Pit Manager: Laptop/Tablet ]
      │
      └──> Scans phone QR code using built-in webcam or hardware scanner
      └──> Decompresses payload and populates Master Database
```

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE][4] file for details. Built in accordance with the FIRST Robotics principles of *Gracious Professionalism* and *Coopertition*.

[1]:	https://vite.dev/
[2]:	https://dexie.org/
[3]:	https://nodejs.org/
[4]:	LICENSE