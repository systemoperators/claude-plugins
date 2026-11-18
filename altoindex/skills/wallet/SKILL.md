---
name: wallet
description: Search Wallet passes and orders
argument-hint: [shop, airline, event or date]
paths:
  - "**/alto-index/wallet/**"
  - "**/alto-index/wallet-orders/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- wallet

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Apple Wallet exported by Alto Index to:
  <alto-index>/wallet/ (passes)
  <alto-index>/wallet-orders/ (orders, when Wallet's Finance folder is given and Wallet is unlocked)


## layout

- one file per pass in wallet/: `{YYYY-MM-DD} {name in lowercase}.md`, an undated pass by its name alone
- one file per order in wallet-orders/: `{YYYY-MM-DD} {shop in lowercase}.md`, the day it was placed

## frontmatter

passes: title, id, created (signed), modified (added to Wallet), tags (wallet and the kind), kind (flight, transit, event, card, other), date, organization, expires, voided, serial

orders: title (shop and order number), id, created (placed), modified, source_url (the shop's order page), tags (wallet, order), merchant, domain, order_number, status (open, completed, cancelled), total, currency, items, card (name and last four), carrier, tracking, expected, delivered, return_by

## body

- a pass: the fields on its front, then ## Back, ## Details, ## Where, ## Barcode
- an order: ## Items (quantity, title, variant, price), ## Payment (the shop's own summary lines, total, each payment with the card), ## Shipping (carrier, tracking link, delivered or expected), ## Returns

## tips

- total is a number and currency its ISO code: sum orders by currency, never across currencies
- find what was spent at a shop: grep merchant or domain in wallet-orders/
- find a trip: kind: flight or transit in wallet/, by date
- a pass with date_source: signed carries no date of its own; the date is when it was signed
