# 🎮 Retro Replay Hub — Reseller OS

> **A free, single-file inventory management and business-tracking app for eBay, Poshmark, Mercari, Whatnot, Facebook Marketplace, and multi-channel resellers.**

Made with ♥ by [RetroReplayHub.com](https://retroreplayhub.com) · *Free reseller tool · No support SLA · Updates released as available*

---

## ⚡ Quick Start — No Installation Required

1. **Download** `retro-replay-hub.html` from this repository
2. **Open it** in any modern web browser (Chrome, Firefox, Safari, Edge)
3. **That's it.** No server, no npm, no build step, no account, no dependencies to install

The entire app is one self-contained HTML file. Run it locally or host it on GitHub Pages, Cloudflare Pages, Netlify, or any static host.

---

## 💾 Your Data Is Saved Automatically

Retro Replay Hub stores everything **locally in your browser using IndexedDB**. Your inventory, expenses, mileage, goals, and business settings persist across page refreshes, browser restarts, and re-deploys — no cloud account required.

- ✅ Data survives refreshes and closing the tab
- ✅ Works fully offline after the first load
- ⚠️ Data is tied to **one browser on one device**. Use the **Export** feature regularly to back up, and **Import** to move data to another device.
- ⚠️ Clearing your browser's site data / cache will erase your saved data — export first.

---

## 🚀 Deploying to a Hosting Site

### Cloudflare Pages (Recommended — Free, Fastest)
1. Log in to the [Cloudflare Dashboard](https://dash.cloudflare.com)
2. Go to **Workers & Pages → Create → Pages → Direct Upload**
3. Rename `retro-replay-hub.html` to `index.html`, then drag and drop it
4. Hit **Deploy** — live in seconds at a `*.pages.dev` URL
5. Add your own domain under **Custom Domains**

### GitHub Pages (Free)
1. Fork or clone this repository
2. Rename `retro-replay-hub.html` to `index.html`
3. Go to your repo **Settings → Pages**
4. Set Source to the `main` branch, root folder `/`
5. Your app goes live at `https://yourusername.github.io/your-repo-name`

### Netlify (Free)
1. Go to [netlify.com](https://netlify.com) → **Add new site → Deploy manually**
2. Rename `retro-replay-hub.html` to `index.html`
3. Drag and drop the file — live instantly at a `*.netlify.app` URL

### Vercel (Free)
1. Rename `retro-replay-hub.html` to `index.html`
2. Drag the folder into the [Vercel dashboard](https://vercel.com/new), or run `vercel` from the CLI

> **Tip:** Renaming the file to `index.html` gives you clean URLs (`yoursite.com` instead of `yoursite.com/retro-replay-hub.html`).

---

## 🧩 Features

| Area | What it does |
|------|--------------|
| **Dashboard** | At-a-glance stats: inventory value, profit, active listings, recent activity |
| **Inventory** | Add, edit, search, and filter items by status. Barcode scan to auto-fill product details |
| **Barcode Lookup** | Scan UPC / EAN / ISBN to pull title, brand, category & image from free public databases |
| **Profit Calculator** | Per-platform fee math (eBay, Poshmark, Mercari, etc.) with ROI, margin & break-even |
| **Expenses** | Track business costs by category with month-over-month totals |
| **Mileage** | Log trips and auto-calculate IRS-rate tax deductions |
| **Reports** | Revenue, profit, category breakdowns and inventory aging |
| **Goals** | Accept challenges and track progress toward sales/revenue targets |
| **Storage** | Organize where items are physically stored |
| **Labels** | Generate printable SKU/QR labels |
| **Import / Export** | Drag-and-drop CSV import and one-click CSV export for all data |
| **Settings** | Business profile, logo, contact, billing/tax info, dark mode, and platform preferences |

---

## 📷 Barcode / Product Lookup

The scanner chains **three free public APIs** (no API key required):

1. **Open Food Facts** — consumer products, food, electronics
2. **Open Library** — books by ISBN
3. **UPCitemdb** — general merchandise *(free tier: ~100 lookups/day)*

Plug in a USB/Bluetooth barcode scanner (it types like a keyboard) or enter codes manually. Found products auto-fill the Add Item form.

---

## 📥 Importing & Exporting Data

- **Export:** Settings/Import-Export page → choose Inventory, Expenses, or Mileage → downloads a CSV.
- **Import:** Drag a CSV onto the import zone (or click to browse). The app previews rows before adding them.
- Use export → import to **back up** your data or **move it to another device/browser**.

---

## 🏪 Make It Yours

You can fully rebrand the app for your own business — no coding required:

- **Rename the file to match your business.** The HTML file can be renamed to anything you like, e.g. `my-shop.html` or `vintage-finds.html`. It will work exactly the same. (If you're hosting it, renaming it to `index.html` still gives you the cleanest URLs.)
- **Set your business name and logo in Settings.** Open the app, go to the **Settings** page, and update your **business name** and upload your **logo**. These appear throughout the app and are saved automatically in your browser — no need to edit any code.
- You can also add your contact details, billing/tax info, and platform preferences from the same Settings page.

---

## 🛠️ Customizing the App

Everything lives in the single HTML file. Open it in any text editor:

- **Business name, logo, contact, tax info** → set these in the in-app **Settings** page (saved automatically — no code editing needed)
- **Brand colors** → edit the `BRAND` object near the top of the `<script>` block
- **Dark/light theme palettes** → edit the `DARK` and `LIGHT` objects
- **IRS mileage rate** → edit `MILEAGE_RATE` (also adjustable in Settings)
- **Platform fee rates** → edit the `FEES` object inside the Profit Calculator
- **Navigation items** → edit the `NAV_ITEMS` array

No rebuild needed — just save the file and refresh.

---

## 🧪 Tech Stack

- **React 18** (via CDN) + **Babel Standalone** for in-browser JSX — no build tooling
- **IndexedDB** for local data persistence
- Pure inline SVG icons, no icon-library dependency
- Single `.html` file, ~170 KB

---

## ⚠️ Support & Updates

This app is offered **free, with no official support or SLA**. That said, we'll do our best to ship frequent updates and fixes. Issues and pull requests are welcome on the repository.

---

## 📄 License

Free to use and modify for personal and commercial reselling. See repository for license details.

---

*Made with ♥ by [RetroReplayHub.com](https://retroreplayhub.com)*
