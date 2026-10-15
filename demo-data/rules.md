# Northwind Pixel Studio: finance rules for the AI

Fictional company. All names, numbers and accounts are invented for training.

As of 2026-10-15. Approved by Sofia Lind (fictional).

Read this file first. Company facts (prices, clients, recurring costs, the decision on the table) are in `context/company-context.md`.

## Numbers Contract

1. Numbers come from files; maths comes from code or spreadsheet formulas, never from the model's head.
2. Every figure carries its source: file plus row or ID.
3. Totals reconcile to a control number (bank closing balance, invoice count). If they do not, stop and report the gap.
4. Facts and assumptions are labelled separately; every forecast lists its assumptions.
5. Unknown stays unknown: never fill a gap with a plausible number.
6. One currency per total; conversions state the rate, its date and its source.
7. Private by default: raw figures stay in private files; shared pages, chats and other models see aggregates only.

## Approval traffic light

- **GREEN, the AI does it alone:** read exports, categorise, calculate, reconcile, flag anomalies, draft reports.
- **YELLOW, the AI drafts and Sofia approves:** payment reminders to clients, changes to categories or budget, sharing or publishing any dashboard, anything sent to the accountant.
- **RED, never:** pay, transfer, sign, file taxes, delete records, share credentials or account numbers.

## Rules

1. **Currency.** EUR.
2. **Categories.** Use the Categories tab of `northwind-books.xlsx`. A new category is a yellow change: propose it, Sofia approves.
3. **Own accounts** (fake numbers, last 4 digits only): business account ...0000, tax reserve ...0002, Sofia's personal account ...0001. Transfers between them are not expenses or revenue.
4. **Receipts.** Which bank lines need a receipt: rule 4 in `context/company-context.md`.
5. **Matching tolerance.** A receipt or invoice matches a bank line within 5 calendar days and to the exact cent in EUR.
6. **Foreign currency.** For card payments in another currency, the EUR amount the bank booked is the cost. Record the original amount and currency, and put the implied rate (bank EUR / original amount) in notes. No external rate source is needed.
7. **VAT.** Invoice-date basis (context rule 2). Q3 VAT is due 25 October 2026; Q4 VAT is due 25 January 2027.
8. **Tax set-aside.** 25% of the net amount (excluding VAT) of each client payment received (context rule 1).
9. **Fixed costs for the cash floor.** Every recurring cost at the price the bank charged most recently; annual plans divided by 12 at the EUR amount the bank booked; the contractor at EUR 1,800 a month.
10. **Cash floor.** 2 x monthly fixed costs. A new fixed cost raises it from the month it starts.
11. **Weeks.** Weeks run Monday to Sunday. Week 1 runs from the as-of date to the next Sunday.
12. **Weekends.** A payment due on a weekend is made on the Friday before.
13. **Scenario date for a big overdue invoice** (context rule 5). In the "collected" scenario, assume collection on 30 October 2026, the date the reminder asks for.
14. **Reminder tone.** Friendly up to 30 days overdue, firm from 31 days, never final.
15. **Billing contacts.** Address reminders to the client name on the invoice. Sofia adds the email address when she sends; no contact file exists.
16. **Phone or Telegram summary.** Not used in this practice pack.
17. **Decision briefs (DECIDE7).** Required for any new recurring cost above EUR 500 a month or any one-off cost above EUR 2,000.
18. **Decision review.** 90 days after a hire.
19. **VERIFY7.** Not available in this practice pack: list the assumptions you would have checked.
20. **Files.** The AI may create new files only inside a `reports/` folder in this pack (briefs, decision log). It never edits or deletes the source files. The one exception: the Bookkeeper fills the Ledger and Exceptions tabs of `northwind-books.xlsx`.
21. **Focus for Q4.** Protect the cash floor, collect overdue invoices, decide on the assistant. Goal of the hire: free Sofia about 10 hours a week for billable design days.
