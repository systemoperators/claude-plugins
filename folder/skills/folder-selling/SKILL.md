---
name: folder-selling
description: "Sell or give away files and folders from Folder: connect Stripe, what can be sold, prices, free downloads and emails, previews, changes, and how a product did."
---

# Sell or give away files and folders

Use these when the person asks to sell or give away something they made, to set up payments, or how a product did. Never offer to sell something they did not ask about.

## What can be sold

Any file or folder in their folder on Folder: an ebook, music, beats and sample packs, photos and Lightroom presets, templates, videos, courses and LUTs, Claude skills, or any PDF or zip. Not a folder in their own Cloudflare, and not a guest's folder until they keep it. To send one person a file, make a share link instead (folder-sharing).

## Stripe, once, for a price

A free product needs nothing. A price needs their own Stripe account, connected once on folder.dev › Settings › Payments. Connect Stripe opens Stripe, where they pick their account and allow File Sales by Folder; with no Stripe account, they make one there. Or Use My Own Stripe Key takes a restricted key with Checkout Sessions, Products and Prices set to Write, and Payment Intents and Charges set to Read.

Buyers pay that account directly. Folder never holds the money and takes nothing during the beta; the fee is Stripe's own. The same card asks two things: Stripe takes care of tax (it adds 3.5% to Stripe's fee) or they do it themselves, and whether the price includes tax or adds it on top. This connection cannot connect Stripe or make those choices: send them to the page. Until real payments open on Folder, Stripe connects in test mode: no money moves, and free products work as they will later.

## Put it on sale

sell_file puts one file on its own page; sell_folder puts a whole folder there, which buyers open after paying to take each file, never a zip. Each lives at buy.folder.dev under their handle.

- Price: in US dollars, price for one amount, or pay_what_you_want with price as the least (0 lets people download free) and suggested_price. Left out, it is free.
- ask_email: buyers leave their email before a download, the way to collect emails with a free file.
- cover and pictures: photos in their folder shown on the page, a cover and up to 7 more.
- show: what buyers see before paying: watermark (PREVIEW across each photo, the default), plain, small, blurred, or names only. video_seconds plays 0, 10 or 30 seconds of a video.
- For a folder: layout grid or list, and later_files included (files added later reach buyers, the default) or snapshot.

The first call says what will be public and answers a confirm code. Ask the person, and only after they say yes call again with that code. Give them the link it returns.

## After it is on sale

The page always gives the newest version of the file: they change it in their folder. list_products lists what they sell, with each link. update_product changes the words, price, pictures, preview, whether it shows on their page (show_on_page), and whether buyers get an email when it changes (email_updates). unpublish_product stops it; buyers who paid keep their download. Both ask first the same way. list_sales answers how one did, with the count and the total earned.

Refunds are made in their Stripe Dashboard, and a refunded buyer's download stops. Versions such as Personal and Commercial licenses, and discount codes, are added on the product's Edit on folder.dev.

Report a sale or a change only after the tool answers, with the link it returned.

## By kind

### How to Write and Sell an Ebook

A PDF sold with sell_file shows a reader with its first pages before paying (a fifth of the book, 1 to 20 pages) and its page count. When an EPUB with the same name sits beside the PDF in the same folder, both formats are listed and the buyer gets both, so suggest putting both files side by side first. Pictures for the page can be the cover and a few spreads, through cover and pictures.

### How to Sell Music, Beats and Sample Packs

An MP3 or a WAV plays its first 10 or 30 seconds on the page before paying, alone or as each file in a folder. Set it with video_seconds, 0 for none. M4A, FLAC and AIFF show only their name and size. Set cover (and pictures) to the cover art. A sample pack sells as itself with sell_folder (show names, layout list): buyers open the folder after paying and take each file, never a zip. With later_files included, sounds added later reach them; snapshot keeps it to what is there now. A zip through sell_file works too. A beat's lease tiers, such as Basic, Premium and Exclusive, are versions added on the page's Edit, each with its own price and its own file from the same folder.

### How to Sell Photos and Lightroom Presets

A folder of photos sold with sell_folder sells as itself, never a zip: after paying, buyers open the folder and take each photo full size. With later_files included, photos added later reach buyers; snapshot keeps it to what is there now. One photo, or a zip of them, sold with sell_file shows its pictures on the page. show sets what buyers see before paying: watermark (PREVIEW across each photo, the default), plain (smaller copies), small (thumbnails), blurred, or names (only names and sizes). iPhone HEIC photos show as JPEG copies. cover and pictures pick the main picture and up to 7 more. A Lightroom preset pack usually sells as a zip through sell_file, with before and after photos as cover and pictures. Personal and Commercial licenses are versions, each with its own price, added on the page's Edit.

### How to Sell Templates: Notion, Figma, Canva and Spreadsheets

A template that is a link (a Notion duplicate link, a Canva template link, a Google Sheets copy link) is not a file. Sell a PDF or a text file that holds the link and the instructions through sell_file, and say so plainly. A PDF shows its first pages before paying (a fifth of them, at least 1). So the link goes on the last page of a PDF of two pages or more, or in a text file. A .fig, an .xlsx or a zip shows its name and size. Screenshots of the template are the page's pictures: cover and pictures, a cover plus up to 7 more. Personal and Commercial licenses, or one version per tool, are versions added on the page's Edit, each with its own price and optionally its own file. The page always gives the newest version, and buyers can be emailed when it changes.

### How to Sell Videos: Footage, Courses and LUTs

An MP4, MOV, M4V or WebM under 100 MB plays its first 10 or 30 seconds on the page before paying (video_seconds sets it, 10 by default; 0 for none). A larger video shows only its name and size, so suggest a short trailer under 100 MB as its own file. A folder sold with sell_folder plays the first video in it that has a clip (files sort by name, so 00 Trailer.mp4 comes first; grid layout, not list). A course sells as a folder of numbered lessons, never a zip: after paying buyers open it and download each file. There is no streaming player after paying. With later_files included, lessons added later reach buyers; snapshot keeps it to what is there now. A LUT pack usually sells as a zip of .cube files through sell_file, with before and after stills as cover and pictures (up to 7 more). Personal and Commercial licenses are versions, each with its own price and optionally its own file, added on the page's Edit.

### How to Make and Sell a Claude Skill

A skill is a folder with SKILL.md at its root: sell it with sell_folder (show names is a good choice). Its page shows the file list, the front matter and the first 12 lines, never the rest. After paying, the buyer's page has one line that puts it in ~/.claude/skills, and files changed later reach buyers. Help them write SKILL.md well before selling it.
