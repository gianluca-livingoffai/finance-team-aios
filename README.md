# Finance team for your AI Business Brain

**Four skills that give an AI Business Brain a finance and business intelligence team: a Bookkeeper, a Controller and an Analyst. You, the owner, are the CFO.**

Made for Week 6 of the AI Business Brain cohort, "Build your Finance & Business Intelligence team", with Egils Boitmanis' AIOS method. The skills use the same format as the public [AIOS library](https://github.com/arete-aios/aios) and link to its skills where they rely on them.

> Use checked numbers for budgets, forecasts and decision briefs, with human approval for financial actions.

In marketing, a wrong word costs a click. In finance, a wrong number costs a decision.

## Three rules

1. **The AI never does maths in its head.** Numbers come from files, maths from code or spreadsheet formulas.
2. **The AI never touches the money.** It reads, calculates and drafts. You approve, you pay, you send.
3. **Every number shows where it came from.** File plus row, or the calculation that produced it.

## The team

| Role | Skill | Job | Output | Cadence | Hands off to |
|---|---|---|---|---|---|
| **Bookkeeper** | [`BOOK7`](skills/book7/SKILL.md) | Turn bank exports, receipts and invoices into one clean ledger, reconciled to the bank balance, plus an exceptions list | Ledger rows and exceptions, with the match rate | Weekly, or at month close | Controller |
| **Controller** | [`CASH7`](skills/cash7/SKILL.md) | The Money Monday brief: cash today, money owed to you with aging, money you owe (bills, VAT, tax set-aside), free cash, 13-week forecast, runway against your cash floor. Drafts payment reminders, never sends | One-page brief and reminder drafts | Every Monday | You, to approve reminders. Analyst |
| **Analyst** | [`KPI7`](skills/kpi7/SKILL.md) | Five to seven KPIs with formulas, monthly budget against actual with a reason for each big variance, a private KPI page through DASHBOARD7 | Monthly KPI file, aggregated page | Monthly | You |
| **Analyst** | [`DECIDE7`](skills/decide7/SKILL.md) | A decision brief for a money question: options including "not now", maths in code, assumptions, scenarios, risks, a recommendation, checked with VERIFY7 | Decision brief and a decision log with review dates | On demand | You |

**You are the CFO.** You own the approvals, the Numbers Contract and the cash floor.

How the work flows:

```
bank exports, receipts, invoices
              |
            BOOK7      ledger + exceptions, reconciled to the bank
           /     \
       CASH7     KPI7  ---> private page via DASHBOARD7
           \     /
           DECIDE7     ---> decision log, reviewed after 30 or 90 days
```

## The Numbers Contract

Paste these seven lines into your Constitution.

```
THE NUMBERS CONTRACT
1. Numbers come from files; maths comes from code or spreadsheet formulas, never from the model's head.
2. Every figure carries its source: file plus row or ID.
3. Totals reconcile to a control number (bank closing balance, invoice count). If they do not, stop and report the gap.
4. Facts and assumptions are labelled separately; every forecast lists its assumptions.
5. Unknown stays unknown: never fill a gap with a plausible number.
6. One currency per total; conversions state the rate, its date and its source.
7. Private by default: raw figures stay in private files; shared pages, chats and other models see aggregates only.
```

## The approval traffic light

Paste this into your Constitution too.

```
APPROVAL TRAFFIC LIGHT
Green, the AI does it alone: read exports, categorise, calculate, reconcile, flag anomalies, draft reports.
Yellow, the AI drafts and you approve: payment reminders to clients, changes to categories or budget, sharing or publishing any dashboard, anything sent to your accountant.
Red, never: pay, transfer, sign, file taxes, delete records, share credentials or account numbers.
```

## Install

Each `SKILL.md` is written to your AI, not to you. The last line of every file tells the assistant to save the skill in your skills layer, add its trigger line to your skills-CONTEXT file, and confirm in one line what it saved and where.

**Your assistant must be able to run code on files.** ChatGPT desktop, Claude, Codex and Hermes can when that capability is on. If yours cannot, the skill says so and stops instead of guessing. That is the skill working, not failing.

- **ChatGPT desktop, Claude or Codex, working in your Brain folder:** copy the skill folder you want into your Brain's skills folder (in an Arete Brain, `03-skills/`). Then say: `Read 03-skills/book7/SKILL.md and install it.` Adjust the path to where you put it. No folder access? Paste the file's text into the chat; the assistant will hand back what to save and where.
- **Hermes on a server:** put the files in the Brain folder Hermes reads (synced as in Week 3), then ask Hermes in Telegram to read and install the skill. CASH7 can run every Monday on its own: see "Routine mode" inside CASH7 and the [Hermes scheduled tasks](https://hermes-agent.nousresearch.com/docs/user-guide/features/cron) docs. Telegram gets a five line summary with aggregates only; the full brief stays in the Brain.

**Install one at a time, and keep the AIOS rule:** at most three standing skills until the loop has closed once. A skill file sitting in the folder costs nothing. A trigger line in the always loaded core is what makes it standing.

## Start in 15 minutes

Method first, then automate. Run BOOK7 by hand on one bank export.

1. **Paste the Numbers Contract and the traffic light** into your Constitution. (3 minutes)
2. **Export one month from your bank** as CSV or XLSX. An export, never a password. (3 minutes)
3. **Drop it into your Brain's inbox folder.** BOOK7 will propose a finance area and create nothing until you say yes. (1 minute)
4. **Run it.** Open your assistant in the Brain folder and type: `BOOK7. Read the BOOK7 skill, then build a ledger from the bank export in my inbox. Do the maths in code. Reconcile to the closing balance and list every exception with file and row.` It asks for your categories once. (5 minutes)
5. **Check one number by hand against its source.** Pick a ledger row, open the bank export at that row, compare. (2 minutes)
6. **Close with `EXIT7`**, so your answers and the rules land in files. (1 minute)

Next: run CASH7 on the same ledger next Monday.

Prefer to practise first? A fictional practice dataset (a small studio, all names and numbers invented) is in [`demo-data/`](demo-data/). Run the same steps on it.

## Privacy before you upload anything

- **Exports, never passwords.** No bank logins, no API keys, no card numbers in any chat. A stolen API key can cost thousands overnight.
- **Mask what you do not need.** The last four digits identify an account well enough.
- **Check your assistant's data and training settings** before you upload financial files, and prefer a business plan where you have the choice.
- **Raw statements stay in a private folder.** Shared pages, group chats and other models see aggregates only.
- **Connections come later, and read only.** Start with exports. Decline write access even when it is offered.

## What is in this folder

```
finance-team-aios/
  README.md
  LICENSE
  skills/
    book7/SKILL.md     Bookkeeper
    cash7/SKILL.md     Controller
    kpi7/SKILL.md      Analyst: KPIs, budget against actual, private page
    decide7/SKILL.md   Analyst: decision briefs and the decision log
  demo-data/           fictional practice dataset
```

## Credits

- **The method is Egils Boitmanis' AIOS**, built with [FullDigital](https://fulldigital.me) and taught at [AreteAIOS](https://areteaios.com): the five layers (Constitution, Memory, Skills, Tools, Focus), trigger words ending in 7, "method first, then automate", and the rule of three standing skills. The full library: [github.com/arete-aios/aios](https://github.com/arete-aios/aios), CC BY 4.0.
- **These skills link to Egils' skills:** [VERIFY7](https://github.com/arete-aios/aios/blob/main/skills/verify7/SKILL.md) (an independent check that never sees private figures), [DASHBOARD7](https://github.com/arete-aios/aios/blob/main/skills/dashboard7/SKILL.md) (one private page and its privacy gate), [EXIT7](https://github.com/arete-aios/aios/blob/main/skills/exit7/SKILL.md) (close the session), [WEEK7](https://github.com/arete-aios/aios/blob/main/skills/week7/SKILL.md) (the weekly review, with read-only bank options) and [FOCUS7](https://github.com/arete-aios/aios/blob/main/skills/focus7/SKILL.md) (what matters now).
- **Reused text:** the AIOS paragraph in each skill and the closing "on ingest" line come from Egils' skills, used under CC BY 4.0.
- **The four new skills** (BOOK7, CASH7, KPI7, DECIDE7): Gianluca Giuliani, [livingoffai.com](https://livingoffai.com). Version 1.0.0, 15 October 2026.

## License

[Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/). The full legal code is in [`LICENSE`](LICENSE). Use it, change it, ship it. Keep the attribution, for example:

```
Finance team skills by Gianluca Giuliani (livingoffai.com), built on Egils Boitmanis' AIOS method (github.com/arete-aios/aios). CC BY 4.0.
```

## Disclaimer

Not tax, legal or accounting advice. The AI prepares, your accountant files. You stay responsible for every payment, filing and commitment, and for checking that your use of financial data follows the rules that apply to you and, if you are an employee, to your company.
