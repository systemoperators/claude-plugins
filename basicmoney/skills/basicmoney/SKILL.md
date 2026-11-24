---
name: basicmoney
description: Turn bank, credit card and brokerage statement PDFs into transactions as Excel or CSV, checked to add up, and say how to download statements from a bank.
---

# Bank statements with Basic Money

Use Basic Money when the person has a bank, credit card or brokerage statement as a PDF. It gives the transactions as a spreadsheet and says whether the statement adds up. It also says how to download statements from a bank. General questions and writing do not need Basic Money.

convert_bank_statement reads the account, dates and transactions from a statement PDF, checks whether the balances add up, and links to Excel and CSV. For brokerage statements it checks the opening and closing values and can report money-weighted returns across consecutive statements. A conversion result expires after 24 hours. When a signed-in person converts a PDF attached in chat, the tool also saves the statement to their library. Call the tool without a file or code to get the upload page. The person can upload PDFs there and bring back the code as result_id. For a password-protected PDF, direct the person to the upload page to enter the password. Keep passwords out of the chat. Use a PDF with selectable text.

get_statement_guide gives a bank's own steps to download statements, with the date they were read; menus change, so say they are the bank's words as of that date.

list_accounts, list_statements and search_transactions read the statements the person kept in Basic Money, signed in; the first call asks them to connect. They read only that person's own library and change nothing.

Basic Money cannot move money, pay a bill or make a budget.
