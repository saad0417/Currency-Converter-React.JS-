<div align="center">

# 💱 Currency Converter
### React.js · Currency API · Tailwind CSS · Custom Hooks

A fast, responsive currency converter web app built with **React.js** that fetches real-time exchange rates from a live Currency API — supporting conversion between 150+ world currencies with a clean, minimal UI.

---

</div>

## 🧩 Overview

This **Currency Converter** is a single-page React application that lets users instantly convert between any two currencies using live exchange rate data. It features a custom React hook for API logic, debounced input for performance, swap functionality, and a fully responsive interface built with Tailwind CSS.

---

## ✨ Features

- 🔄 **Real-time exchange rates** fetched from Currency API
- 💰 **150+ currencies** supported with full names and symbols
- ⇄ **Swap button** — instantly reverse from/to currencies
- ⚡ **Live conversion** — updates as you type
- 📱 **Fully responsive** — works on mobile, tablet, and desktop
- 🧠 **Custom React hook** (`useCurrencyInfo`) for clean API separation
- 🕐 **Last updated timestamp** shown for rate freshness
- ✅ Input validation with user-friendly error handling

---

## 🛠️ Tech Stack

| Technology | Usage |
|---|---|
| **React.js** | UI framework, component architecture |
| **Tailwind CSS** | Styling and responsive layout |
| **Currency API** | Live exchange rate data |
| **Custom Hook** | `useCurrencyInfo` — fetches and returns rate data |
| **Vite** | Development server and build tool |

---

## 🧠 Custom Hook — `useCurrencyInfo`

```js
// hooks/useCurrencyInfo.js
import { useEffect, useState } from "react";

function useCurrencyInfo(currency) {
  const [data, setData] = useState({});

  useEffect(() => {
    fetch(`https://cdn.jsdelivr.net/npm/@fawazahmed0/currency-api@latest/v1/currencies/${currency}.json`)
      .then(res => res.json())
      .then(res => setData(res[currency]));
  }, [currency]);

  return data;
}

export default useCurrencyInfo;
```

---

## 🏗️ Project Structure

```
currency-converter/
│
├── public/
├── src/
│   ├── components/
│   │   └── InputBox.jsx        ← Reusable currency input component
│   ├── hooks/
│   │   └── useCurrencyInfo.js  ← Custom hook for API calls
│   ├── App.jsx                 ← Main app logic (swap, convert, state)
│   ├── main.jsx
│   └── index.css
│
├── index.html
├── tailwind.config.js
├── vite.config.js
└── package.json
```

---

## ⚙️ Getting Started

### Requirements
- Node.js v16+
- npm or yarn

### Steps
```bash
# 1. Clone the repository
git clone https://github.com/your-username/currency-converter.git

# 2. Navigate into the project
cd currency-converter

# 3. Install dependencies
npm install

# 4. Start the development server
npm run dev

# 5. Open in browser
http://localhost:5173
```

---

## 🔌 API Used

**@fawazahmed0 Currency API** — free, no API key required

```
Base URL:
https://cdn.jsdelivr.net/npm/@fawazahmed0/currency-api@latest/v1/currencies/{currency}.json

Example:
https://cdn.jsdelivr.net/npm/@fawazahmed0/currency-api@latest/v1/currencies/usd.json
```

Returns a JSON object with exchange rates for all supported currencies relative to the base.

---

## 🚀 Roadmap

- [ ] Dark mode toggle
- [ ] Conversion history log
- [ ] Favourite/pinned currency pairs
- [ ] Offline support with cached rates
- [ ] PWA (installable on mobile)

---

## 👨‍💻 Developer

**Muhammad Saad Akhtar**
BS Software Engineering — Superior University Lahore
*Passionate about React.js and building practical web tools*

---

<div align="center">

📜 *For educational purposes. Free to use and modify.*

</div>