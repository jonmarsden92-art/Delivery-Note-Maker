# Kingsway Group – Delivery Note Tool

A fully offline, single-file web app that replaces the `DN_Config_Tool_V2_2.xlsx` Excel tool. It generates clean, professional delivery notes for door system deliveries.

---

## Features

- **Project details** — name, reference, phase, sales order, version, project manager, site contact
- **Delivery address** — full address fields
- **Logistics** — collection date/time, unload capability, transport type, goods description
- **Section 1 – Door Schedule** — add/remove door rows with inline validation (type, fire rating, frame finish, DTM flag, lock type, special notes)
- **Section 2 – Components** — add/remove component rows with code autocomplete, description lookup, and live alerts
- **48hr delivery notice check** — auto-detects if delivery date is within 48 hours
- **Validation logic** carried over from Excel:
  - DTM door missing interface unit
  - Cylinder bolt count vs door count
  - Pellets warning when all frames are primed
  - Key quantity warnings
  - KG64 deadbolt keep vs Double/L&H door count
  - Unknown component codes
- **⚡ Auto-fill components** from the door schedule (architraves, pellets, intumescent, bolts, discs, keys, closers)
- **Print / Save PDF** — uses browser print dialog; the generated note is print-optimised (no UI chrome)
- **100% offline** — zero external dependencies, no server required

---

## Usage

### Option 1 – Just open it

Download `index.html` and open it in any modern browser. No install, no server.

### Option 2 – GitHub Pages

1. Fork this repo
2. Go to **Settings → Pages → Source: main branch / root**
3. Your tool will be live at `https://yourusername.github.io/delivery-note-tool/`

### Option 3 – Serve locally

```bash
# Python 3
python -m http.server 8080
# then open http://localhost:8080
```

---

## Repo Structure

```
delivery-note-tool/
├── index.html      ← entire app (HTML + CSS + JS, self-contained)
└── README.md
```

---

## Generating a Delivery Note

1. **Configure tab** — fill in all project, address, logistics, door and component data
2. Click **⚡ Generate Delivery Note** (or switch to **Preview / Print** tab)
3. Review the preview — it shows only the clean delivery note (no validation columns)
4. Click **🖨 Print / Save PDF** to print or export to PDF via your browser

---

## Component Code Autocomplete

All component codes from the Item List are built in. Start typing a code in the Components table and the browser will suggest matching codes with their descriptions.

---

## Customising

All item codes and descriptions are in the `ITEM_DB` object at the top of the `<script>` block. Add, remove, or amend entries there.

Option lists (door types, fire ratings, frame finishes, lock types) are at the top of the script as simple arrays.

---

## Browser Support

Works in all modern browsers (Chrome, Firefox, Edge, Safari). Print-to-PDF works best in Chrome.

---

## Licence

Internal tool — Kingsway Group. Not for redistribution.
