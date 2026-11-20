---
name: folder-selling
description: Sell or give away a file from Folder, change a product, stop it, and see how it did.
---

# Sell or give away a file or a folder

Use these when the person asks to sell or give away one of their files or folders, or asks how a product did. Never offer to sell something they did not ask about.

sell_folder puts a whole folder on its own page: before paying, buyers see what is inside the way the person picks (photos with a watermark, small, blurred, or only the names); after paying, they open the folder and take each file, never a zip. Files added later reach buyers unless the person wants only what is there now. It asks first the same way.

sell_file puts one file from their folder on Folder on its own page at buy.folder.dev, at a price or free. Its first call says what would go on sale and answers a confirm code: ask the person, and call it again with the code only after they say yes. A free file needs nothing more; a price works once they have connected their own Stripe on folder.dev, Settings › Payments, and buyers pay that account. Only files in their folder on Folder, never a folder in their own Cloudflare; to send one person a file, make a share link instead.

list_products lists what they sell or give away, with each product's link. update_product changes a product's title, description, or whether buyers leave their email first, and unpublish_product stops one: both ask first, the same way. list_sales answers how one did, with the count and the total earned.

Report a sale or a change only after the tool answers, with the link it returned.
