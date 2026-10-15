# Northwind Pixel Studio: practice pack

Fictional company. All names, numbers and accounts are invented for training.

**As of:** Thursday 2026-10-15. Bank data runs from 2026-07-01 to 2026-10-14.

This is the practice data for Week 6 of the AI Business Brain cohort: build your finance team (Bookkeeper, Controller, Analyst). Use it with your own AI assistant. It must be able to run code on files (ChatGPT desktop, Claude, Codex and Hermes can).

## What is in the folder

| Path | What it is |
|---|---|
| `rules.md` | The owner's finance rules; read it first (Numbers Contract, approval traffic light, matching, VAT, tax set-aside, cash floor, forecast conventions) |
| `context/company-context.md` | Who the studio is, prices, clients, recurring costs, the business rules (tax set-aside, VAT, cash floor, receipts) and the decision on the table |
| `bank/bank-statement-2026-07-01_to_2026-10-14.csv` | Bank statement, one line per transaction, signed amounts (negative = money out), running balance |
| `invoices/sales-invoices.csv` | Every sales invoice issued June to October 2026, with status and paid date |
| `budget/budget-2026.csv` | Monthly budget July to December 2026, cash basis (revenue = client payments received, excluding VAT) |
| `receipts/` | Receipt photos (5 files) |
| `northwind-books.xlsx` | The books workbook: README, Bank, Sales invoices, Budget, Categories, and two empty tabs to fill: Ledger and Exceptions |
| `skills/` | The four finance skills (BOOK7, CASH7, KPI7, DECIDE7), one SKILL.md each |

Receipts:
- `receipts/2026-07-21_voltmarket.png`
- `receipts/2026-08-12_framewise.png`
- `receipts/2026-09-02_cloudcrate.png`
- `receipts/2026-09-24_bistro-larkspur.png`
- `receipts/2026-09-24_railnord.png`

**File notes.** The bank file starts with an OPENING BALANCE line (1 July) and ends with a CLOSING BALANCE line (14 October); neither is a transaction. In each CSV, line 1 is the fictional-data notice and line 2 holds the column names (the Bank, Sales invoices and Budget tabs of the workbook follow the same layout, so a row number in a tab equals the line number in its CSV). Dates are YYYY-MM-DD. Amounts are EUR with 2 decimals. Account numbers are fake.

## Three suggested tasks

1. **Bookkeeper (BOOK7).** Fill the Ledger and Exceptions tabs for 1 July to 14 October from the bank statement, the receipts and the sales invoices. Do the maths in code and reconcile to the bank balance on 14 October.
2. **Controller (CASH7).** Write the Money Monday brief as of 15 October: cash today, money owed to us with aging, what we owe (VAT and the tax set-aside), free cash, a 13-week forecast and runway against the cash floor. Draft reminders for overdue invoices. Send nothing.
3. **Analyst (DECIDE7).** Write the decision brief: can we hire a part-time assistant at EUR 1,500/month from 1 November? Options, maths in code, assumptions, scenarios, risks, a recommendation and what would change your mind.

Then check one number by hand against its source file and row.

## Ground rules

- The AI never does maths in its head, never touches money, and every number shows where it came from.
- Practise on this fictional data. If you later use your own exports, keep them on your own machine and share aggregates only.
- This is training material, not tax, legal or accounting advice.
