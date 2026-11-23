---
name: basicmoney
description: Turn bank, credit card and brokerage statement PDFs into transactions as Excel or CSV, checked to add up, and say how to download statements from a bank.
---

# Bank statements with Basic Money

Use Basic Money when the person has a bank, credit card or brokerage statement as a PDF. It gives the transactions as a spreadsheet and says whether the statement adds up. It also says how to download statements from a bank. General questions and writing do not need Basic Money.

convert_bank_statement reads a statement PDF: the account, its dates and every transaction. It says whether the opening balance and the transactions come to the closing balance, or by how much it is off. It links the result as Excel and CSV. Where the chat cannot hand the file over, call it with neither a file nor a code. The answer is an upload page where the person drops the statements and gets a code to bring back as result_id. A statement locked with a password is named in locked: send the person to the upload page to type the password there; never ask for a password in the chat. A photo or a scan cannot be read: it needs the text a PDF carries.

get_statement_guide gives a bank's own steps to download statements, with the date they were read; menus change, so say they are the bank's words as of that date.

list_accounts, list_statements and search_transactions read the statements the person kept in Basic Money, signed in; the first call asks them to connect. They read only that person's own library and change nothing.

Basic Money cannot move money, pay a bill or make a budget. What a statement holds is kept 24 hours under an unguessable id for anyone who is not signed in, then deleted.

## Available tools

Generated from ops-registry.json: 5 tools. Only v1 operations are available.

| Read tool | Returns |
|---|---|
| convert_bank_statement | each statement read, its account and dates, whether its opening balance plus every transaction comes to its closing balance (or by how much it is off), the transactions (date, description, amount, category), each statement's and transaction's currency as an ISO code when the statement prints one; for a brokerage statement its value at the start and end and whether its own summary adds up, and over brokerage statements that follow one another the money-weighted return each year and since the start; the files locked with a password; and a link to the result page with Excel and CSV, kept 24 hours |
| get_statement_guide | how to download that bank's statements, step by step on its website and in its app, each step with the bank's own menu words; how far back statements go, the formats, how to get older ones; the page with the guide drawn; and the bank's own help page it comes from |
| list_accounts | each account in the person's Basic Money library with its latest balance (a card's is what is owed), the day it is from, how many statements are kept and whether every one adds up; banks before cards, the largest first |
| search_transactions | the person's own transactions that match every word of the query in any order (the bank's words or the clean name), between the dates when given, newest first, each with its date, description, amount, currency and account; how many matched and their sum |
| list_statements | each statement in the person's library: its account, its dates, how many transactions, and whether its opening balance plus every transaction comes to its closing balance or by how much it is off; newest first |

| Write tool | Action | Operation | Approval |
|---|---|---|---|
