# ClassSpinner

ClassSpinner is a modern, responsive, and offline-capable Progressive Web Application (PWA) designed to facilitate interactive and random participant selection. Perfect for classrooms, professional presentations, panel discussions, or events, it provides an engaging slot-machine-style draw animation while seamlessly tracking participation and performance statistics.

---

## 🚀 Key Features

*   **🎰 Slot-Machine Draw Engine**: Features a 3-line animated rolling wheel that mimics a slot machine, providing excitement and engagement for participants before revealing the drawn candidate.
*   **📊 Live Participant Tracking**: Manages attendee details inline including ID Number, Name, Presence (`isPresent`), and Selection Inclusion (`isIncluded`).
*   **📈 Participation Stats**: Tracks how many times a participant has been selected (`timesSelected`), how many times they answered (`timesAnswered`), and their correct answer count (`timesCorrect`).
*   **💾 Auto-Saving & Local Storage**: Automatically persists all data modifications to the browser's `LocalStorage` with an in-memory fallback, ensuring zero data loss on page refreshes.
*   **📂 CSV Import & Export**:
    *   **Export**: Save your roster and statistics as a `.csv` file using the modern **File System Access API** (native save dialog) with anchor-download fallbacks.
    *   **Import**: Load external student or participant lists via CSV file parsing instantly.
*   **🎯 Fair Selection Flow**: When a participant is drawn, their selection count increases, and their inclusion status is automatically disabled. This ensures everyone gets a turn before resetting the group.
*   **📱 Offline-Ready (PWA)**: Uses Service Workers (`sw.js`) and a Web Manifest (`manifest.json`) to cache assets, allowing the app to run completely offline.
*   **⚡ Premium User Experience**:
    *   Smooth view-focus scroll targeting the drawn winner's row.
    *   Glassmorphism-styled floating control action bar.
    *   Responsive layout optimized for mobile, tablet, and desktop views.

---

## 🛠️ Technology Stack

*   **Core**: HTML5, Vanilla CSS3 (Custom Glassmorphism and animations)
*   **Layout & Styling**: Bootstrap 5, Bootstrap Icons
*   **Logic & Animation**: JavaScript (ES6+), jQuery
*   **PWA Integrations**: Service Worker API, Web App Manifest
*   **Mobile Capabilities**: Out-of-the-box support for compile-to-mobile wrapper configurations via **CapacitorJS**.

---

## 📦 Getting Started

### Prerequisites
To run the web application locally, you only need a modern web browser.

### Running the App
1.  **Clone or Download** the repository.
2.  Open `index.html` directly in your browser:
    *   *Note*: The Progressive Web App (PWA) offline features and service worker caching require a server context (using HTTP or HTTPS protocol, e.g., via `localhost`).
3.  To run with a local server, you can use any static server extension or CLI utility (e.g. `npx serve .`, Live Server in VS Code, or Python's `python -m http.server`).

---

## 📂 CSV Data Format

When importing or exporting participant lists via CSV, the file should use standard comma separation with the following header layout:

```csv
id,idNumber,name,isPresent,isIncluded,timesSelected,timesAnswered,timesCorrect
1,"7025241001","Achmad Bisri",1,1,0,0,0
2,"7025241002","Windi Eka Yulia Retnani",1,1,0,0,0
```

### Data Fields Table
| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the record. |
| `idNumber` | String | Registration, Student, or Employee number. |
| `name` | String | Full name of the participant. |
| `isPresent` | Boolean (0/1 or true/false) | Determines if the person is present. |
| `isIncluded` | Boolean (0/1 or true/false) | Determines if the person is eligible for the current spin. |
| `timesSelected` | Integer | Total times the participant was picked by the spinner. |
| `timesAnswered` | Integer | Total times the participant answered a question. |
| `timesCorrect` | Integer | Total times the participant answered correctly. |

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
