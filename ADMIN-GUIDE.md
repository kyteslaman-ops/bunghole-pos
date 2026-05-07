# The Bunghole POS - Manager & Admin Guide

> Everything staff can do, plus reports, money management, employees, and settings.
> Log in with a **Manager** PIN to unlock all tabs.

---

## Manager-Only Tabs

When you log in as a Manager, you see extra tabs with a lock icon:

| Tab           | What it's for                                    |
|---------------|--------------------------------------------------|
| **Reports**   | Sales data, analytics, pour cost                 |
| **Drawer**    | Cash drawer, shift open/close, tip pool          |
| **Voids**     | Cancelled orders log                             |
| **Timesheet** | Employee hours, clock corrections                |
| **Audit**     | Full action log of everything that happens        |
| **Settings**  | Employees, taxes, categories, backup/restore     |

Staff members see Register, Inventory, and Rooms only.

---

## Opening & Closing a Shift

### Opening

1. Go to **Drawer** tab
2. Tap **"Open Shift"**
3. Count your opening float and enter the dollar amount (e.g., $200)
4. Tap **Open Shift**

The drawer is now active. All cash sales during this shift are tracked.

### During the shift

Use the drawer buttons as needed:

- **Paid In**: Cash added to the drawer (e.g., manager drops change). Enter amount + reason.
- **Paid Out**: Cash removed (e.g., bought ice from the store). Enter amount + reason.

The **Expected Cash** updates in real time:

```
Expected = Opening Float + Cash Sales + Paid In - Paid Out
```

### Closing

1. Count all the cash in the drawer
2. Tap **"Close Shift"**
3. Review the shift summary (opening float, cash sales, paid in/out)
4. Enter the **Counted Cash** amount
5. **Variance** auto-calculates:
   - Green = exact match
   - Red = over or short -- **you must enter a reason** (e.g., "till short", "miscounted")
6. **Tip Pool**: check "Allocate tip pool now" to split tips immediately
   - **Equal share**: splits evenly among employees who made sales
   - **Manual %**: enter custom percentage per employee (must total 100%)
7. Tap **"Close Shift & Generate Z-Report"**

A printable Z-Report opens in a new window.

---

## Reports

### Date range

Use the preset buttons at the top: **Today**, **Yesterday**, **Last 7d**, **Last 30d**, **MTD**, or pick **Custom** dates.

All data below updates to match your selected range.

### KPI Dashboard

Six cards at the top:

| Card      | Shows                          |
|-----------|--------------------------------|
| Revenue   | Total sales including tips     |
| Tips      | Total tips                     |
| Items     | Number of items sold           |
| Trans     | Number of transactions         |
| Card      | Card payment total             |
| Cash      | Cash payment total             |

### Transaction Table

Every sale in the range. Each row has:

- **Receipt** button: reprint/view any past receipt
- **Refund** button (red arrow): process a partial or full refund (see below)
- **"R" badge**: appears on transactions that have been partially or fully refunded

### Refunds

Below the transaction table. Shows all processed refunds with original tx reference, items, method, reason, and amount.

### Hourly Sales Heatmap

Visual bar chart showing revenue by hour (0-23). Use this for staffing decisions -- see when you're busiest.

### Top Sellers (Sales Mix)

Ranked list of items by quantity sold. Shows qty, revenue, and % of total revenue. Use this for:

- Ordering: stock up on top sellers
- Menu decisions: consider dropping dead SKUs (listed below)

### Dead SKUs

Items with **zero sales** in the selected date range. If something hasn't sold in 30 days, consider removing it.

### Pour Cost / COGS

Approximate cost analysis for liquor and cocktails:

| KPI            | What it means                              |
|----------------|--------------------------------------------|
| Revenue        | Total liquor + cocktail sales              |
| Est. Cost      | Estimated ingredient cost                  |
| Margin         | Revenue minus cost                         |
| Pour Cost %    | Cost / Revenue -- industry target: 18-24%  |

**Per-item breakdown** shows cost, revenue, and margin % for each product.

**How cost is calculated:**
- Bourbon/liquor: `bottleCost / (bottleSize_oz / pourSize_oz)`, scaled by pour modifier
- Cocktails: flat default of $3 per drink (configurable in Settings)
- This is approximate -- adjust the cocktail cost default in Settings for your recipes

---

## Processing a Refund

1. Go to **Reports** tab
2. Find the transaction in the table
3. Tap the red **refund** button
4. **Select items** to refund (or tap "Full Refund" for everything)
5. Choose **Refund Method**: Card, Cash, or Original Method
6. Enter a **Reason** (required)
7. Review the refund total
8. Tap **"Process Refund"**

The refund:
- Restores stock on refunded items
- Logs an audit entry
- Appears in the Refunds section of Reports
- Marks the original transaction with an "R" badge

**You cannot double-refund** -- already-refunded items are tracked.

---

## Z-Report

The Z-Report is your end-of-day summary. Access it two ways:

1. **Reports tab** > tap **"Z-Report"** button (uses "today" by default)
2. **Drawer tab** > Close Shift auto-generates one

The report opens in a new printable window showing:
- Revenue breakdown (card, cash, room)
- Tips total
- Transaction and item counts
- Voids count and value
- Per-employee breakdown (sales, transactions, tips)
- Per-category breakdown

Tap **Print** in the popup to print it.

---

## Employee Management

Go to **Settings** tab > **Employees** section.

### Add an employee

1. Enter their **Name**
2. Enter a **4-digit PIN** (must be unique)
3. Select **Role**:
   - **Staff**: Register, Inventory, Rooms only
   - **Manager**: All tabs + settings access
4. Tap **Add**

### Edit an employee

Tap **Edit** next to their name. You can change:
- Name
- PIN (enter a new 4-digit PIN)

PINs are hashed -- you can't see existing PINs, only set new ones.

### Disable / Enable

Tap **Disable** to temporarily block an employee from logging in. Tap **Enable** to restore access. Use this instead of deleting for employees on leave.

### Remove

Tap **X** to permanently delete an employee. Cannot be undone. The Owner account cannot be removed.

---

## Timesheet

### Clocking in/out

- Every employee can tap the **clock icon** in the header to clock in or out
- Or from the Timesheet tab, tap **"Clock In/Out (me)"**

### Viewing hours

1. Go to **Timesheet** tab
2. Pick a date range (Today, Last 7d, etc.)
3. **Totals by Employee**: shows shifts count and total hours
4. **Entries**: shows each individual clock in/out with times and hours

### Corrections

If someone forgot to clock out or times are wrong:

1. Find the entry in the **Entries** table
2. Tap **Edit** to change Clock In / Clock Out times
3. Or tap **X** to delete a bad entry

All timesheet changes are logged in the Audit trail.

---

## Inventory Management

Go to the **Inventory** tab (accessible to all staff).

### Adding a product

1. Tap **"+ Add"**
2. Fill in:
   - **Name** (required)
   - **Category** (pick from dropdown)
   - **Emoji** (optional, for the product card)
   - **Price** (required -- or use bottle pricing below)
3. For **bourbon/liquor categories**, bottle pricing fields appear:
   - **Bottle Cost**: what you paid
   - **Bottle Size**: ml (default 750)
   - **Pour Size**: oz per serving (default 1.5)
   - **Markup**: multiplier (default 4x)
   - The retail price auto-calculates: `(bottleCost / pours) x markup`
4. Set **Stock** and **Low Alert** threshold
5. Tap **Add**

### Restocking

Tap the **+** button on any item. Enter how many bottles/units received. Stock adds up (doesn't replace).

### Bulk import

Tap **Bulk** to paste many items at once. Format: `Name | Category | Price | Stock` (one per line).

### Load New Bourbons

In **Settings**, the "Add New Bourbons" section has a button to merge the latest bourbon inventory without losing any existing edits.

---

## Business Settings

In the **Settings** tab:

| Setting                    | Default | What it does                                    |
|----------------------------|---------|-------------------------------------------------|
| Business Name              | The Bunghole Bourbon Lounge | Shows on receipts      |
| Sales Tax Rate (%)         | 6%      | Applied to all items                            |
| Bardstown Liquor Tax (%)   | 7.5%    | Extra tax on bourbon, cocktails, flights only   |
| Cocktail Cost Default ($)  | $3.00   | Used in pour cost report for cocktail COGS      |

Tap **Save Settings** after making changes.

### Categories

You can add or remove product categories. Each category has a name and emoji icon. Removing a category does NOT delete products in it.

---

## Backup & Restore

**Always back up before major changes.**

### Export (backup)

Two ways:
- Tap the **floppy disk icon** in the header (always visible)
- Or go to Settings > tap **"Export"**

Downloads a `.json` file with all data: products, transactions, employees, settings, everything.

### Restore (import)

1. Go to Settings > tap **"Restore"**
2. Pick a previously exported `.json` file
3. Confirm -- this **overwrites all current data**
4. App reloads with restored data

### Clear All Data

Settings > Danger Zone > **Clear All Data**. Requires two confirmations. Resets to factory defaults. **This cannot be undone.**

---

## Audit Trail

The **Audit** tab logs every action in the system:

- Logins (successful and failed)
- Sales (amount, payment type)
- Voids (amount, reason)
- Refunds
- Inventory changes (add, edit, delete, restock)
- Employee changes (add, edit, enable/disable, remove)
- Settings changes (tax rates, etc.)
- Time clock events

### Filtering

Use the dropdown to filter by event type: All, Logins, Sales, Voids, Inventory, Employee, Settings, Time Clock.

### Export

Tap **"Export CSV"** to download the full audit log as a spreadsheet-ready CSV file.

---

## Voids

The **Voids** tab shows all cancelled orders with:
- Today's void count and dollar value lost
- Full history: time, employee, items, amount, reason, and notes

Use this to monitor for suspicious voiding patterns.

---

## Quick Reference

```
OPEN SHIFT      Drawer > Open Shift > enter float > Open
CLOSE SHIFT     Drawer > Close Shift > count cash > enter variance reason > allocate tips > Close
Z-REPORT        Reports > Z-Report button, or auto-generated on shift close
ADD EMPLOYEE    Settings > name + 4-digit PIN + role > Add
REFUND          Reports > find transaction > Refund button > select items > reason > Process
REPRINT         Reports > find transaction > Receipt button
TIMESHEET FIX   Timesheet > find entry > Edit > correct times
BACKUP          Header floppy disk icon, or Settings > Export
RESTORE         Settings > Restore > pick .json file
POUR COST       Reports > scroll to Pour Cost section (auto-calculated)
AUDIT EXPORT    Audit > Export CSV
```
