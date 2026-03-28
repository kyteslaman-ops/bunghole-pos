# The Bunghole Bourbon Lounge — POS System

A free, web-based Point of Sale system for **The Bunghole Bourbon Lounge** at BourbonManor.com.

## Business Info

| | |
|---|---|
| **Address** | 714 N 3rd Street, Bardstown, KY 40004 |
| **Email** | thebungholebourbonlounge@gmail.com |
| **Website** | BourbonManor.com |

**Live POS:** https://bunghole-pos.kyteslaman.workers.dev

---

## Features

### Register
- Product grid with categories (Cocktails, Flights, Bourbon tiers, Beer, Wine, etc.)
- Bourbon pour modifiers (Shot, Neat, Rocks, Tasting, Double)
- Cocktail bourbon upgrades (Well → Call → Premium → Top Shelf → Rare)
- Quick search across all products
- 86 mode (mark items as unavailable)

### Cart & Checkout
- Add/remove items with quantity controls
- Tip selection (15%, 20%, 25%, custom)
- Card or Cash payment
- Room charge for B&B guests
- Cancel order with reason tracking

### Receipts
- On-screen receipt after every sale
- **Text/Share** — Send via iMessage, AirDrop, or copy
- **Email** — Opens email app with receipt ready to send
- **Print** — For thermal receipt printers (80mm format)
- All transactions saved in Reports

### Inventory Management
- Full product CRUD (add, edit, delete)
- Bottle pricing calculator:
  - Enter bottle cost (wholesale)
  - Auto-calculates retail price per pour
  - Standard 1.5oz pour, configurable markup (3-5x)
- Stock tracking with low-stock alerts
- Bulk import via JSON

### Room Charges (B&B Integration)
- 10 rooms from Bourbon Manor pre-loaded:
  - Manor: Sweet Old Fashioned, Mint Julep, Classic Sazerac, Hotty Toddy, Southern Love, Manhattan Honeymoon, Master Distiller's Den
  - Federal House: Debutante's Dream, Magnolia Maiden, Scarlet Starlet
- Post charges to guest rooms
- Track pending vs. posted charges

### Employee Management
- PIN-based login (4-digit)
- Two roles:
  - **Staff** — Register, Inventory, Rooms
  - **Manager** — All above + Reports, Voids, Audit, Settings
- Add/edit/disable employees

### Reporting & Audit
- Daily sales report with KPIs
- Card vs. Cash breakdown
- Tips tracking
- Void/cancel log with reasons
- Full audit trail with CSV export

---

## Bottle Pricing Formula

For small bars with 1-2 bottles of each spirit:

```
Retail Price = (Bottle Cost / Pours per Bottle) × Markup

Example:
- Bottle Cost: $26 (Buffalo Trace)
- Bottle Size: 750ml = ~25.36 oz
- Pour Size: 1.5 oz
- Pours per Bottle: 16
- Markup: 4×

Retail = ($26 / 16) × 4 = $6.50 per pour
```

---

## Default Inventory

### Bourbon Tiers
| Tier | Examples | Markup |
|------|----------|--------|
| Well | Evan Williams, Jim Beam | 4× |
| Call | Buffalo Trace, Maker's Mark, Woodford | 4× |
| Premium | Angel's Envy, Four Roses SiB, Knob Creek 12 | 4× |
| Top Shelf | Blanton's, Weller 12, E.H. Taylor | 5× |
| Rare | Pappy 15/20/23, BTAC, Michter's 20 | 4-5× |

### Top 10 Beers
Modelo Especial, Bud Light, Michelob Ultra, Corona Extra, Coors Light, Miller Lite, Budweiser, Heineken, Busch Light, Natural Light

### Cocktails
Old Fashioned, Manhattan, Mint Julep, Whiskey Sour, Kentucky Mule, Boulevardier, Paper Plane, Gold Rush, and more

---

## Setup

### Access the POS
1. Open Safari on iPad/phone
2. Go to: `bunghole-pos.kyteslaman.workers.dev`
3. Add to Home Screen for app-like access

### Default Login
- PIN: `5366` (Owner account)
- Change this in Settings after first login!

### iPad Setup for Business
1. Create Apple ID with free iCloud email: `yourname@icloud.com`
2. Sign into iPad with business Apple ID
3. Set up Google Voice for free business phone number
4. Add POS to Home Screen

---

## Hardware (Optional)

### Receipt Printer (iOS Compatible)
- **Star Micronics TSP143IIIBi** (~$250) — Bluetooth, works with iPad
- Amazon: Search "Star TSP143IIIBi"

### Cash Drawer
- **Volcora Cash Register Drawer** (~$50) — RJ11, connects to printer
- Auto-opens when receipt prints

---

## Tech Stack

| Component | Technology |
|-----------|------------|
| Frontend | Single HTML file, vanilla JS, CSS |
| Hosting | Cloudflare Workers (free) |
| Data Storage | localStorage (browser) |
| Code Repository | GitHub |

---

## Development

### Edit the Project
```bash
cd ~/Downloads/bunghole-pos-v3
claude
```

Or use the shortcut (if set up):
```bash
pos
```

### Deploy Changes
```bash
npx wrangler deploy
```

### Push to GitHub
```bash
git add .
git commit -m "your message"
git push origin main
```

---

## File Structure

```
bunghole-pos-v3/
├── index.html      # Complete POS application
├── worker.js       # Cloudflare Worker entry point
├── wrangler.toml   # Cloudflare configuration
└── README.md       # This file
```

---

## Costs

| Service | Cost |
|---------|------|
| Cloudflare Workers | **Free** (100K requests/day) |
| GitHub | **Free** |
| Google Voice | **Free** |
| iCloud email | **Free** |
| **Total** | **$0/month** |

---

## Data Storage

All data is stored in the browser's localStorage on the iPad:
- Transactions
- Inventory
- Employees
- Settings
- Audit logs

**Storage capacity:**
- 1,000 sales ≈ 2 MB
- 10,000 sales ≈ 20 MB
- iPad has 64-256 GB — years of data fits easily

**Backup:** Use the 💾 button in the header to download a JSON backup.

---

## Support & Updates

**Project Location:** `~/Downloads/bunghole-pos-v3`

**GitHub:** https://github.com/kyteslaman-ops/bunghole-pos

**To make changes:** Open Terminal → type `pos` → tell Claude what you need

---

## License

Private project for The Bunghole Bourbon Lounge at BourbonManor.com

---

*Built with Claude Code — March 2026*
