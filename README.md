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
- Tip selection (None, 15%, 20%, 25%, custom)
- Card or Cash payment
- Room charge for B&B guests (with tip selection)
- Cancel order with reason tracking

### Receipts
- On-screen receipt after every sale
- **Take a photo** if customer needs a copy
- **Email** — Opens email app with receipt ready to send
- All transactions saved in Reports

### Inventory Management
- Full product CRUD (add, edit, delete)
- Bottle pricing calculator:
  - Enter bottle cost (wholesale)
  - Auto-calculates retail price per pour
  - 10 pours per 750ml bottle (1.5oz each)
  - 3× markup standard
- Stock tracking = pours remaining in bottle
- Low-stock alerts at 2 pours remaining
- **Load New Bourbons** button — adds/updates bourbon inventory without losing other data

### Room Charges (B&B Integration)
- 10 rooms from Bourbon Manor pre-loaded:
  - Manor: Sweet Old Fashioned, Mint Julep, Classic Sazerac, Hotty Toddy, Southern Love, Manhattan Honeymoon, Master Distiller's Den
  - Federal House: Debutante's Dream, Magnolia Maiden, Scarlet Starlet
- 2-step flow: Select room → Add tip → Accept Charges
- Tip selection (None, 15%, 20%, 25%, custom)
- Track pending vs. posted charges

### Employee Management
- PIN-based login (4-digit)
- Two roles:
  - **Staff** — Register, Inventory, Rooms
  - **Manager** — All above + Reports, Voids, Audit, Settings
- Add/edit/disable employees (including Owner)

### Taxes
- **Sales Tax** — Configurable % (default 6%)
- **Bardstown City Liquor Tax** — Configurable % for bourbon/alcohol sales

### Reporting & Audit
- Daily sales report with KPIs
- Card vs. Cash vs. Room breakdown
- Tips tracking
- Void/cancel log with reasons
- Full audit trail with CSV export

---

## Bottle Pricing Formula

For small bars with 1-2 bottles of each spirit:

```
Price per Shot = (Bottle Cost / 10 pours) × 3

Example:
- Bottle Cost: $23 (Buffalo Trace from Kroger)
- Pours per Bottle: 10 (750ml ÷ 1.5oz)
- Markup: 3×

Price = ($23 / 10) × 3 = $7 per pour
```

---

## Bourbon Inventory (from Kroger receipts)

### Well ($6-7/pour)
| Bourbon | Bottle Cost | Per Pour |
|---------|-------------|----------|
| 1792 Bourbon | $20 | $6 |
| Jim Beam | $23 | $7 |
| Evan Williams | $23 | $7 |

### Call ($7-9/pour)
| Bourbon | Bottle Cost | Per Pour |
|---------|-------------|----------|
| Buffalo Trace | $23 | $7 |
| Larceny | $23 | $7 |
| Four Roses Yellow | $24 | $7 |
| Wild Turkey Longbranch | $25 | $8 |
| Bulleit Bourbon | $26 | $8 |
| Elijah Craig | $28 | $8 |
| Makers Mark | $28 | $8 |
| Woodford Reserve | $30 | $9 |

### Premium ($11-14/pour)
| Bourbon | Bottle Cost | Per Pour |
|---------|-------------|----------|
| Castle & Key | $36 | $11 |
| Knob Creek 7yr | $36 | $11 |
| Four Roses Single Barrel | $38 | $11 |
| Russells Reserve 10yr | $40 | $12 |
| Angels Envy | $44 | $13 |
| Evan Williams Single Barrel | $45 | $14 |
| 1792 Full Proof | $46 | $14 |
| Willett | $48 | $14 |

### Top Shelf ($15-23/pour)
| Bourbon | Bottle Cost | Per Pour |
|---------|-------------|----------|
| Bulleit Single Barrel | $51 | $15 |
| Woodford Double Oaked | $52 | $16 |
| Rare Breed | $53 | $16 |
| Jackson Purchase | $53 | $16 |
| Angels Envy Rye | $64 | $19 |
| Knob Creek 12yr | $66 | $20 |
| Makers Private Select | $78 | $23 |

### Rare/Allocated ($11-330/pour)
| Bourbon | Bottle Cost | Per Pour |
|---------|-------------|----------|
| Eagle Rare 10yr | $35 | $11 |
| Weller Antique 107 | $55 | $17 |
| Blantons | $65 | $20 |
| EH Taylor Small Batch | $65 | $20 |
| Weller 12 | $80 | $24 |
| George T Stagg | $400 | $120 |
| Pappy 15yr | $700 | $210 |
| Pappy 20yr | $1100 | $330 |

### Other Categories
- **Cocktails** — Old Fashioned, Manhattan, Mint Julep, Whiskey Sour, Kentucky Mule, and more
- **Flights** — Kentucky Classics, Buffalo Trace Family, Weller Journey, Premium Explorer
- **Beer** — Modelo, Bud Light, Michelob Ultra, Corona, Coors Light, Miller Lite, KY Bourbon Barrel Ale
- **Wine** — House Cab, Chardonnay, Pinot Grigio, Prosecco, Champagne
- **Snacks** — Bourbon Pecans, Charcuterie, Pretzel Bites, Bourbon Balls
- **Merch** — T-Shirts, Hats, Glencairn Glasses, Tasting Journals
- **Gift Shop** — Gift Boxes, Candles, Coasters, BBQ Sauce, Bourbon Honey

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

**Stock tracking:**
- Each bourbon starts with 10 pours (1 bottle)
- Stock decreases by 1 per sale
- Low stock alert at 2 pours remaining
- When opening new bottle, edit item and reset stock to 10

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

*Built with Claude Code — April 2026*
