# 🎮 Reseller Central — The Free Reseller Platform

> **A free, single-file inventory management and business tracking app for eBay, Poshmark, Mercari, Whatnot, Facebook Marketplace, and multi-channel resellers.**

Created and maintained by [RetroReplayHub.com](https://retroreplayhub.com)

---

## ⚡ Quick Start — No Installation Required

1. **Download** `reseller-central.html` from this repository
2. **Open it** in any modern web browser (Chrome, Firefox, Safari, Edge)
3. **That's it.** No server, no npm, no dependencies, no account needed

The entire app is one self-contained HTML file. Open it locally, put it on GitHub Pages, Cloudflare Pages, Netlify, or any static host.

---

## 🚀 Deploying to a Hosting Site

### GitHub Pages (Free)
1. Fork or clone this repository
2. Go to your repo **Settings → Pages**
3. Set Source to `main` branch, root folder `/`
4. Rename `reseller-central.html` to `index.html`
5. Your app will be live at `https://yourusername.github.io/your-repo-name`

### Cloudflare Pages (Free, Fastest)
1. Log in to [Cloudflare Dashboard](https://dash.cloudflare.com)
2. Go to **Workers & Pages → Create → Pages → Direct Upload**
3. Drag and drop the `reseller-central.html` file (rename to `index.html`)
4. Hit Deploy — live in seconds at a `*.pages.dev` URL
5. Add your custom domain under **Custom Domains**

### Netlify (Free)
1. Go to [netlify.com](https://netlify.com) → **Add new site → Deploy manually**
2. Drag and drop the `reseller-central.html` file
3. Rename it `index.html` before uploading for clean URLs
4. Live instantly at a `*.netlify.app` URL

### Vercel (Free)
1. Install Vercel CLI: `npm i -g vercel`
2. In the folder containing your HTML file, run: `vercel`
3. Follow the prompts — your app deploys in under a minute

### Self-Hosted / Any Web Server
Simply place `reseller-central.html` (or `index.html`) in your web server's public directory. It works with Apache, Nginx, IIS, or any static file server.

---

## 🎨 Customizing for Your Business

### Option 1 — Use the Built-in Settings Page (Easiest)
1. Open the app
2. Click **Settings** in the sidebar (or the gear icon in the top-right)
3. Fill in your **Business Profile**: name, logo, tagline, contact info, address, tax ID
4. Your logo and business name will appear in the topbar, sidebar, and purchase order previews
5. Settings are saved automatically to your browser's localStorage

### Option 2 — Edit the Source Code (Developers)

Open `reseller-central.html` in any text editor (VS Code recommended). All configuration is near the top of the `<script>` block.

#### Change the default business name
Find this line (~line 1320) and change the default values:
```js
const BIZ_DEFAULT = {
  name: 'My Reseller Shop',        // ← Change this
  tagline: 'Games • Movies • Music • Fashion',  // ← And this
  ...
};
```

#### Change the app color scheme
Find the `BRAND` object near line 50:
```js
const BRAND = {
  yellow:  '#F5C842',   // Primary accent — change to your brand color
  cyan:    '#00E5FF',   // Secondary accent
  magenta: '#FF00CC',   // Third accent
  dark:    '#1A1A1A',   // Dark background
};
```

#### Change the dark mode colors
Edit the `DARK` and `LIGHT` theme objects near line 32:
```js
const DARK = {
  bg: '#0F0F0F',        // Main background
  card: '#1C1C1E',      // Card/panel background
  text: '#F2F2F7',      // Primary text
  // ... etc
};
```

#### Add seed inventory data
Find `const INIT_INV = [...]` and add your items to pre-populate on first load:
```js
const INIT_INV = [
  {
    id: 1,
    sku: 'YOUR-001',
    title: 'Item Name',
    category: 'Electronics',
    brand: 'Sony',
    condition: 'Good',
    qty: 1,
    cost: 10.00,
    price: 39.99,
    status: 'Listed',      // 'Listed' | 'Unlisted' | 'Sold' | 'Returned'
    platform: 'eBay',
    location: 'Shelf A1',
    daysListed: 5,
    notes: 'Optional notes'
  },
  // ... more items
];
```

#### Change marketplace fee rates
Find `const FEES = {...}` inside `ProfitPage`:
```js
const FEES = {
  eBay: 0.1315,           // 13.15%
  Poshmark: 0.20,         // 20%
  Mercari: 0.10,          // 10%
  Etsy: 0.065,            // 6.5%
  'FB Marketplace': 0.0,  // Free local
  Whatnot: 0.08,          // 8%
};
```

#### Add a new navigation page
1. Add your page to `NAV_ITEMS`:
```js
{id: 'mypage', label: 'My Page', icon: 'star'}
```
2. Create your page component:
```jsx
function MyPage({T}) {
  return (
    <div style={{padding: '24px 28px', overflowY: 'auto', flex: 1}}>
      <div style={{fontSize: 26, fontWeight: 800, color: T.text}}>My Page</div>
      {/* your content */}
    </div>
  );
}
```
3. Add it to `PAGES` inside `App()`:
```js
mypage: <MyPage T={T}/>,
```

---

## 📱 App Features

| Page | Description |
|------|-------------|
| 🏠 Dashboard | Sales funnel, KPIs, active challenges, recent activity |
| 📦 Inventory | Full CRUD with search, filter, detail view, ROI calculator |
| 💰 Calculator | Real-time profit calculator for 6+ platforms |
| 🧾 Expenses | Category tracking, recurring expenses, month comparison |
| 🚗 Mileage | IRS mileage deduction log with trip breakdown |
| 📊 Reports | P&L statement, charts, platform & category performance |
| 🎯 Goals | Challenge system with progress tracking |
| 🗄️ Storage | Location management with item drill-down |
| 🏷️ Labels | Avery/Dymo/Zebra label printing with bulk select |
| 📤 Import/Export | Real CSV download + CSV paste import |
| ⚙️ Settings | Business profile, logo upload, preferences, help |

---

## 💾 Data Persistence

By default, business settings are saved to **browser localStorage**. Inventory data resets on page refresh because this is a client-only demo app.

To persist all data across sessions, you have two options:

**Option A — Export/Import CSV manually**
Use the Import/Export page to download a CSV backup before closing, and re-import when you return.

**Option B — Add a backend (Developer)**
The app is built with React + Babel standalone. You can integrate any API by replacing the `useState` data with `fetch()` calls to your backend:
```js
// Replace useState with useEffect + fetch
useEffect(() => {
  fetch('/api/inventory')
    .then(r => r.json())
    .then(data => setInventory(data));
}, []);
```

---

## 🏗️ Technical Stack

- **Frontend:** React 18 (via CDN), Babel Standalone (JSX in-browser)
- **Fonts:** Inter (Google Fonts), Press Start 2P (logo)
- **Icons:** Custom inline SVG (Lucide-style, no external dependency)
- **Storage:** Browser localStorage for settings
- **Size:** ~124KB single HTML file
- **Dependencies:** Zero npm packages · Zero build tools required

---

## 🤝 Contributing

We welcome contributions! The best ways to help:

1. **Report bugs** — Open a GitHub Issue with steps to reproduce
2. **Request features** — Open a GitHub Issue with your use case
3. **Submit a PR** — Fork, make changes, test in browser, open pull request
4. **Share it** — Tell other resellers about this tool!

### Development Setup
No build tools needed. Just:
1. Clone the repo
2. Open `reseller-central.html` in your browser
3. Edit in VS Code with the **Live Server** extension for hot reload
4. That's it — no `npm install`, no webpack, no bundler

---

## 📋 Changelog

### v1.0.0 — June 2026
- Initial release
- 11 fully-featured pages
- Business profile with logo upload
- Dark/Light mode
- Real CSV export (inventory, expenses, mileage)
- Label printing (Avery, Dymo, Zebra)
- Goal & challenge system
- Profit calculator with 6 platforms
- IRS mileage deduction tracking

---

## ⚠️ Support Policy

This app is provided **free of charge** as a gift to the reseller community by RetroReplayHub.com.

- ❌ No paid support or SLAs
- ❌ No guaranteed response times  
- ✅ We will **do our best** to release frequent updates
- ✅ Bug reports via GitHub Issues are welcome
- ✅ Community PRs are encouraged

If this tool helps your reselling business, please:
- ⭐ Star the GitHub repository
- 📣 Share it with other resellers
- 💬 Leave feedback in GitHub Issues

---

## 📄 License

MIT License — free to use, modify, and distribute for personal or commercial use. Attribution appreciated but not required.

---

*Reseller Central is made with ♥ by [RetroReplayHub.com](https://retroreplayhub.com) · Free for the reseller community*
