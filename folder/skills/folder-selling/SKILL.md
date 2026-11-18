---
name: folder-selling
description: Sell or give away a file from Folder, change a product, stop it, and see how it did.
---

# Sell or give away a file

Use these when the person asks to sell or give away one of their files, or asks how a product did. Never offer to sell a file they did not ask about.

sell_file puts one file from their folder on Folder on its own page at buy.folder.dev, at a price or free. Its first call says what would go on sale and answers a confirm code: ask the person, and call it again with the code only after they say yes. A free file needs nothing more; a price works once they have connected their own Stripe on folder.dev, Settings › Payments, and buyers pay that account. Only files in their folder on Folder, never a folder in their own Cloudflare; to send one person a file, make a share link instead.

list_products lists what they sell or give away, with each product's link. update_product changes a product's title, description, or whether buyers leave their email first, and unpublish_product stops one: both ask first, the same way. list_sales answers how one did, with the count and the total earned.

Report a sale or a change only after the tool answers, with the link it returned.
