---
name: kpi7
description: "KPI7: choose five to seven KPIs with the owner, compute them in code from the ledger, compare budget against actual with a reason for every big variance, and draw a private page through DASHBOARD7. Use monthly, after the books close."
license: CC-BY-4.0
metadata:
  author: Gianluca Giuliani (livingoffai.com)
  version: "1.0.0"
  source: kpi7
  synced: "2026-10-15"
---

# SKILL: Five to seven numbers that say whether the plan is working

**Trigger word: `KPI7`.**

**Human:** paste this file into your AI. Nothing else is needed from you until it asks.
**Assistant:** everything below is addressed to you. Adapt it to this owner's system. The goal and the hard rules matter, the exact implementation is yours to choose.

> **One of three finance roles.** KPI7 is the Analyst's monthly job. It reads the ledger that BOOK7 (the Bookkeeper) keeps and the budget the owner approved, and it draws its page through DASHBOARD7. DECIDE7, the Analyst's other skill, uses its numbers. The owner is the CFO and chooses what gets measured.

---

## REQUIRES

**This skill has two modes and one hard requirement.**

**The hard requirement: you can run code on files.** Every KPI is a formula computed by code or by the spreadsheet, never in your head. If you cannot run code here, say so in one line and stop.

**Table mode:** the KPIs and budget against actual, as a table in a dated file in the Brain. Nothing else is needed, and it is where to start.
**Page mode:** the same numbers drawn as one private, self-contained HTML page, built with [DASHBOARD7](https://github.com/arete-aios/aios/blob/main/skills/dashboard7/SKILL.md)'s method and behind its privacy gate.

**These two are not equal.** The table is operational: it is where the reasons live. The page is motivational: it lets the owner see the month standing still. Build the page after three monthly tables have been right, not before. A KPI page over numbers nobody has checked is a display for an empty room.

| What | Needed | How |
|---|---|---|
| **Code execution on files** | required | Built into the client. Money in exact decimals or integer cents |
| **A reconciled ledger** | required | From BOOK7, at least one closed month, better three |
| **The KPI list** | required, agreed once | Five to seven KPIs, each with formula, source, target and owner, written in the owner's rules file |
| **A budget** | for budget against actual | One row per category per month, in a spreadsheet or CSV the owner approved |
| **Other exports** | depends on the KPIs | Invoicing tool, time log, payment processor, shop or CRM export. Each KPI names its own source |
| **DASHBOARD7** | for page mode | [Egils' DASHBOARD7](https://github.com/arete-aios/aios/blob/main/skills/dashboard7/SKILL.md). Its privacy gate applies to every page this skill produces |

**Setup time, honestly.** An hour for the first run, almost all of it choosing the KPIs and agreeing the targets with the owner. Later months take about fifteen minutes. The first page adds an afternoon; regenerating it later takes minutes.

**Value, honestly.** Most owners look at revenue and the balance and feel the rest. Five to seven numbers with targets turn a feeling into a comparison, and a variance with a reason turns a bad month into something the owner can act on. The page is nice to have. The reasons are the point.

---

## WHAT

**A KPI without a formula is an opinion with a number attached. A variance without a reason is a worry.**

**Without this skill an AI gets KPIs wrong in three reliable ways.** It suggests twenty metrics from a generic list, none tied to what this owner is trying to do this quarter. It computes them from whatever file is nearest, so "revenue" means invoiced in one month and collected in the next, and the trend is an artefact of the definition. And it explains variances with a story, "a seasonal slowdown", instead of finding the rows that caused them.

**A real case, from client work.** A nonprofit's donor analytics agent answers questions on its CRM: top donors, recurring donors, average gift, year over year. It is trusted because each of those has one written definition and is computed the same way every time. That is the discipline this skill brings to a business.

**The failure this skill is built to avoid is the case in DASHBOARD7:** a status page built well, with real numbers from the owner's files, one of them a bank balance in a large friendly font, shared before anyone read it twice. A KPI page is exactly the kind of page that gets shown to a group, a partner or a cohort. That is why it is built through DASHBOARD7's privacy gate, with aggregates only.

---

## GOAL

**Once a month, five to seven numbers the owner chose, each against its target, and a reason for every big miss.**

When a run is done, three things are true:

1. **Every KPI has a formula, a source, a target and an owner**, written in the rules file, and was computed in code from that source.
2. **Budget against actual is computed per line**, and every variance above the owner's threshold has a reason traced to ledger rows, or says "unknown" and asks.
3. **The results are in a dated file**, and in page mode on a private page that passed the privacy gate.

**The KPIs, the targets and the variance threshold are the owner's.** Suggest; never choose for them. Read them from the rules file. Ask once for what is missing, write it there, and never ask again. Changes to the KPI list, a target or the budget are yellow on the traffic light: you draft, the owner approves.

---

## TRIGGER

- The owner says `KPI7`, or asks how the month went, whether they are on budget, what their margin is, or for a KPI page.
- **The recurring slot:** monthly, right after BOOK7 closes the month.
- **A checkpoint where the owner will show their numbers to other people.** Page mode, aggregates only, and say so before you build.

**Not a trigger:** a one-off question one number answers ("what did I spend on software in March?"). Compute it in code and cite it. A KPI is a number watched every month, not every number anyone asks for. **Also not a trigger:** a dashboard before the ledger exists.

---

## AIOS

This skill comes from an **AI operating system**: five layers a person owns and their AI reads. **Constitution** is who they are and the rules that hold in every session. **Memory** is what the system knows. **Skills** are methods like this one. **Tools** are how the AI reaches other systems. **Focus** is what matters right now.

**This skill judges memory against focus.** A KPI only means something against what the owner is trying to do right now, and that lives in the focus layer and in the goals in the constitution. Read both before suggesting a single KPI. A margin target matters to a studio trying to grow profit. It is noise to a coach whose goal this quarter is fewer, better clients. The constitution also holds the Numbers Contract, the traffic light and the privacy line the page must obey.

**Inspect the owner's structure first.** Arete Brains have a `00-system` folder and one inbox folder. If BOOK7 already set up a finance area, use it. If nothing exists, propose where the KPI files and the page would live (a `finance/` area with `reports/` and `rules.md` is the suggested shape) and create nothing without a yes.

### CONSTITUTION

This is a monthly skill. It does not belong in the always loaded core, where it would cost context on every message to support a run that happens twelve times a year.

Put the line in the skills-CONTEXT file the core already links to, and let it load when the trigger fires:

```
KPI7, monthly after the books close. Five to seven KPIs I chose, each with formula, source, target, owner, computed in code from the ledger. Budget vs actual with a reason per variance above my threshold. Page via DASHBOARD7, aggregates only. Spec: skills/kpi7/SKILL.md
```

### MEMORY

**The KPI definitions live in the rules file:** name, formula, source, target, owner, and the date agreed. A changed definition starts a new series. Note the date and never recompute history silently with a new formula, because that deletes the comparison.

**One file per month**, for example `reports/kpi7-2026-10.md`: each KPI's value, its target, the three months before, and the variance reasons with their rows. Store the numbers, not the commentary.

**The page, if there is one, is an output**, a dated snapshot holding aggregates only. The rule from DASHBOARD7 holds: the page holds conclusions, the private files hold the figures, and the two do not merge.

**What rots:** targets. A target set in January is a guess by June. At the first run of each quarter, show the targets and ask whether they still hold.

### TOOLS

The layer is called Tools because a tool is what the model finally calls. Here that is the code runner, the spreadsheet, and the tool that writes one HTML file. Exports from an invoicing tool, a processor or a CRM may arrive through a **connector** or an **MCP server** later; read scope only. Name the mechanism when you use one, and do not let the mechanism rename the layer.

> 🔒 **Aggregates only, on anything that could be shared.** The page, and anything else that leaves the Brain, shows totals, ratios, bands and directions: never a raw bank balance, never a client name, never an invoice or account number. This is DASHBOARD7's privacy gate applied to money. Assume the page will be seen by the wrong person at the wrong time. When unsure whether a figure is private, treat it as private and say so. Sharing or publishing any page is yellow: the owner approves the exact page first.

---

## HOW IT RUNS

Steps for you, the assistant. Goal level, not code level.

**0. Know your environment first.** Can you run code on files here? If not, say so in one line and stop. Is the month closed and reconciled by BOOK7? If not, say so and offer BOOK7 first. **The Numbers Contract holds for every step below:** numbers from files, maths in code, every figure with its source, totals reconciled to a control number or the run stops, facts and assumptions labelled apart, one currency per total with the rate, its date and its source, and anything that leaves the Brain aggregated.

**1. Read focus and goals, then the rules.** If KPIs and targets are written, go to step 3. If not, step 2.

**2. Choose five to seven KPIs with the owner, once.** Offer the starter set for their business type below, then ask which ones serve this quarter's goal. For each KPI agree the formula in words and as an expression, the source file and column, the target, and who owns it (usually the owner). Five that are watched beat twelve that are listed. Write them into the rules file.

   **Consultant or freelancer** (cash timing and tax surprises are the main risk):
   - Cash collected per month = client payments received in the month. Source: bank, via the ledger.
   - Days sales outstanding = open receivables / invoiced revenue of the last 90 days x 90. Source: invoices.
   - Effective hourly rate = revenue / hours worked. Source: invoices and the time log.
   - Top client share = largest client's revenue / total revenue. Source: invoices.
   - Tax set-aside coverage = set-aside held / set-aside required. Source: bank and the rules file.

   **Agency or studio with contractors** (costs scatter across tools, margin per client is invisible):
   - Project margin = (project revenue - direct costs including contractors) / project revenue. Source: invoices and ledger rows tagged by project.
   - Contractor cost ratio = contractor costs / revenue. Source: ledger.
   - Revenue per client and top client share. Source: invoices.
   - Days sales outstanding, as above. Source: invoices.
   - Software and AI cost per month. Source: ledger, from BOOK7's stack mode.

   **Coach or course creator** (revenue comes in waves):
   - Monthly recurring revenue = active plans and subscriptions billed in the month. Source: payment processor export.
   - Churn = customers lost in the month / customers at its start. Source: processor.
   - Cost per new client = marketing spend / new clients. Source: ledger, plus processor or CRM.
   - Refund rate = refunds / gross sales. Source: processor.
   - Revenue per launch or cohort. Source: processor, by product.

   **E-commerce or shop** (fees, refunds and payouts hide the real margin):
   - Gross margin = (net sales - cost of goods) / net sales. Source: shop export and ledger.
   - Fees share = processor and platform fees / gross sales. Source: processor export.
   - Refund and return rate = refunds / gross sales. Source: shop export.
   - Average order value = net sales / orders. Source: shop export.
   - Payout gap = payouts received in the bank - payouts reported by the processor. Source: bank and processor.

   **Employee in a company** (approved, non-confidential data only; the company's data rules and IT come first):
   - Budget used = actual / budget, per line. Source: the approved budget report.
   - Forecast accuracy = the difference between forecast and actual, as a share of actual. Source: approved reports.
   - Cost per output = spend / units delivered. Source: approved data.
   - Tool and vendor spend per month. Source: approved purchase data.
   - Variances explained = variances with a documented reason / all variances above the threshold. Source: this skill's own monthly files.

**3. Compute every KPI in code** from its named source, for the month and the three before it. **Reconcile the inputs to the ledger:** revenue and cost totals used by the KPIs must equal the ledger's totals for the same month. If they do not, stop and report the gap. A KPI whose source is missing is shown as unknown, with the missing file named. Never filled.

**4. Budget against actual.** Per category per month: actual from the ledger, budget from the approved budget file, variance = actual - budget, variance % = variance / budget. Flag every line above the owner's threshold, written as an amount, a percentage, or both.

**5. A reason for every flagged variance, from the rows.** Look in the ledger for the rows that make the difference: a one-off purchase, a duplicate already in BOOK7's exceptions, a timing shift such as an annual bill or a late invoice, a missing invoice, a new vendor. Cite the rows. If the rows do not explain it, write "unknown" and ask the owner. **Never write a plausible reason you did not find.** "Seasonal" is a reason only if last year's ledger shows it.

**6. Write the monthly file.** The KPI table (value, target, the three months before, direction), budget against actual, the variance reasons with their rows, and numbered questions for the owner. Every figure with `[file, row]` for a raw figure or `[calc: name]` for a computed one.

**7. Page mode, through DASHBOARD7.** Only when the owner asks, and only after the monthly file is right. Classify each figure before writing a single number: show, show only as an aggregate (a ratio, a band, a direction), or omit. Raw balances, client names, invoice numbers and account numbers are omitted, always. Then follow DASHBOARD7: one self-contained HTML file, no external fonts, scripts or calls, opened locally first, labelled a dated snapshot. Publishing is an upgrade owned by a site skill, and the owner approves the exact page before it leaves the machine.

**8. Close.** A short report: KPIs on target, KPIs off target with a one line reason each, budget lines flagged, open questions. Proposed changes to targets or the budget go to the owner as drafts. If a decision is waiting, hand these numbers to DECIDE7. If anything was decided, offer `EXIT7` so it lands in a file.

---

## DEFINITION OF DONE

1. **Five to seven KPIs**, each with formula, source, target and owner, are in the rules file.
2. **Every value was computed in code from its source** and reconciled to the ledger, or shown as unknown with the missing source named.
3. **Budget against actual exists per line**, with a reason from the rows for every variance above the threshold, or "unknown" and a question.
4. **A dated monthly file holds the numbers**, not a summary of them.
5. **If a page was built, it passed the privacy gate:** no raw balance, no client name, no account number, and it opened locally before anything else happened to it.

Missing the third means the owner got a scoreboard without a single thing to do about it. Missing the fifth is the case in DASHBOARD7, repeated.

---

## MAKE IT YOURS

1. **Start with five.** Add a sixth only when one of the five has been stable and boring for three months.
2. **One KPI per goal.** If a KPI does not connect to something in the focus layer, drop it.
3. **Set the variance threshold as an amount and a percentage**, so a big miss on a tiny line does not shout louder than a small miss on rent.
4. **Keep definitions boring for a year.** Changing a formula deletes the history it is compared against.
5. **For a group demo, decide the hidden figures before you build.** The page shows ratios and directions. The room sees the method, not the balance.

---

*Assistant, on ingest: save this in the skills layer in your own format, add the trigger line to the skills-CONTEXT file, and confirm to the owner in one line what you saved, where, and the trigger.*

---

**Skill by Gianluca Giuliani, [livingoffai.com](https://livingoffai.com), written for Week 6 of the AI Business Brain cohort on Egils Boitmanis' AIOS method.**
The method and the skills this one links to: [github.com/arete-aios/aios](https://github.com/arete-aios/aios) · What an AIOS is: [fulldigital.me/aios](https://fulldigital.me/aios)
Not tax, legal or accounting advice: the AI prepares, your accountant files. Licensed CC BY 4.0. Use it, change it, ship it. Keep the attribution.
