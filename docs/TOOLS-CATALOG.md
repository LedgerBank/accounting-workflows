# Proposed accounting and audit tools

These 60 identifiers are proposed tool specifications, not implemented API names. R = read; P = prepare; W = write the scoped review workspace; X = execute a separately authorized domain action. No tool grants its own permissions.

## Evidence and intake

Inputs: Entity, period and authorized source references.

| Proposed ID | Tool | Mode | Output | Typical users |
|---|---|---|---|---|
| evidence.inventory | Inventory source documents | R | Document register with provenance and missing items | accountant, bookkeeper, auditor, tax |
| evidence.extract | Extract structured accounting facts | P | Source-linked proposed facts and confidence flags | accountant, bookkeeper, auditor, tax |
| evidence.validate | Validate source completeness | P | Missing-period and inconsistent-source exceptions | accountant, bookkeeper, auditor, tax |
| evidence.request | Prepare missing-document requests | P | Draft request for separate recipient review and sending | accountant, bookkeeper, auditor, tax |
| evidence.trace | Trace a balance to source | R | Balance-to-ledger-to-document evidence chain | accountant, bookkeeper, auditor, tax |
| evidence.package | Assemble an evidence package | W | Scoped workpaper bundle and file digest manifest | accountant, bookkeeper, auditor, tax |

## Cash and reconciliation

Inputs: Statements, ledger extracts, opening/closing balances and matching rules.

| Proposed ID | Tool | Mode | Output | Typical users |
|---|---|---|---|---|
| cash.import.preview | Preview statement normalization | P | Proposed normalized lines and import exceptions | accountant, bookkeeper, auditor, treasury |
| cash.match | Match cash activity | P | Suggested matches with reasons and unresolved items | accountant, bookkeeper, auditor, treasury |
| cash.reconcile | Prepare a cash reconciliation | P | Reconciliation workpaper and explained difference | accountant, bookkeeper, auditor, treasury |
| cash.exceptions | Review reconciliation exceptions | R | Aged unmatched items with source references | accountant, bookkeeper, auditor, treasury |
| cash.rollforward | Build a balance rollforward | P | Opening-to-closing movement schedule | accountant, bookkeeper, auditor, treasury |
| cash.signoff | Record reconciliation review | W | Reviewer decision and immutable evidence references | accountant, bookkeeper, auditor, treasury |

## Books and journals

Inputs: Trial balance, chart, journal population and period status.

| Proposed ID | Tool | Mode | Output | Typical users |
|---|---|---|---|---|
| books.trial_balance | Read the trial balance | R | Period trial balance with exact monetary values | accountant, bookkeeper, controller, auditor |
| books.classify | Suggest account classifications | P | Proposed coding with explanation and source links | accountant, bookkeeper, controller, auditor |
| books.journal.prepare | Prepare a balanced journal entry | P | Proposed debits/credits and supporting calculation | accountant, bookkeeper, controller, auditor |
| books.journal.validate | Validate a proposed journal | P | Balance, period, currency and reference exceptions | accountant, bookkeeper, controller, auditor |
| books.journal.post | Post an authorized journal | X | Domain posting receipt, subject to books.post and approval policy | accountant, bookkeeper, controller |
| books.adjustments.review | Review adjusting-entry proposals | W | Review notes and accepted/rejected proposal status | accountant, bookkeeper, controller, auditor |

## Payables

Inputs: Bills, orders, receiving evidence, vendor references and payment states.

| Proposed ID | Tool | Mode | Output | Typical users |
|---|---|---|---|---|
| ap.aging | Analyze payable aging | R | Aging buckets and overdue exceptions | accountant, bookkeeper, ap, controller, auditor |
| ap.duplicates | Find possible duplicate bills | P | Candidate duplicates with comparison evidence | accountant, bookkeeper, ap, controller, auditor |
| ap.match | Prepare two/three-way matching | P | Order/bill/receipt matching exceptions | accountant, bookkeeper, ap, controller, auditor |
| ap.accruals | Prepare payable accruals | P | Accrual schedule and proposed entries | accountant, bookkeeper, ap, controller, auditor |
| ap.payment_plan | Prepare a payment recommendation | P | Recommendation only; not a payment instruction | accountant, bookkeeper, ap, controller, auditor |
| ap.vendor_changes | Review vendor-data changes | R | Change evidence and independent-verification exceptions | accountant, bookkeeper, ap, controller, auditor |

## Receivables

Inputs: Invoices, receipts, customer balances, disputes and period cutoffs.

| Proposed ID | Tool | Mode | Output | Typical users |
|---|---|---|---|---|
| ar.aging | Analyze receivable aging | R | Aging and concentration schedules | accountant, bookkeeper, ar, controller, auditor |
| ar.receipts.match | Match receipts to invoices | P | Suggested allocations and unresolved differences | accountant, bookkeeper, ar, controller, auditor |
| ar.cutoff | Prepare revenue cutoff review | P | Period-boundary exceptions and source references | accountant, bookkeeper, ar, controller, auditor |
| ar.allowance | Prepare an allowance workpaper | P | Assumption-tagged estimate for professional review | accountant, bookkeeper, ar, controller, auditor |
| ar.confirmations | Prepare confirmation requests | P | Recipient-reviewed drafts; no automatic external sending | accountant, bookkeeper, ar, controller, auditor |
| ar.collections | Prepare a collections worklist | P | Prioritized review list and draft communications | accountant, bookkeeper, ar, controller, auditor |

## Close and reporting

Inputs: Period checklist, reconciliations, ledgers and report definitions.

| Proposed ID | Tool | Mode | Output | Typical users |
|---|---|---|---|---|
| close.checklist | Build the close checklist | W | Owned tasks, dependencies and review evidence | accountant, bookkeeper, controller, treasury, auditor |
| close.readiness | Review close readiness | P | Open exceptions and incomplete signoffs | accountant, bookkeeper, controller, treasury, auditor |
| close.fluctuations | Analyze period fluctuations | P | Explained variances and unresolved movements | accountant, bookkeeper, controller, treasury, auditor |
| close.reports | Prepare financial-report schedules | P | Draft schedules traceable to the trial balance | accountant, bookkeeper, controller, treasury, auditor |
| close.consolidation | Prepare consolidation mappings | P | Proposed mapping and intercompany differences | accountant, bookkeeper, controller, treasury, auditor |
| close.lock | Close an authorized accounting period | X | Domain receipt subject to books.close and period policy | accountant, bookkeeper, controller, treasury |

## Audit and assurance

Inputs: Approved engagement, scoped populations, evidence and reviewer criteria.

| Proposed ID | Tool | Mode | Output | Typical users |
|---|---|---|---|---|
| audit.population | Validate audit-population completeness | P | Population totals and reconciliation to source | auditor, accountant, controller |
| audit.sample | Prepare an audit sample | P | Reproducible selection and documented selection basis | auditor, accountant, controller |
| audit.journal_tests | Prepare journal-entry exception tests | P | Flagged entries with source evidence; no fraud conclusion | auditor, accountant, controller |
| audit.controls | Document control walkthroughs | W | Process, control, evidence and reviewer notes | auditor, accountant, controller |
| audit.findings | Prepare findings and evidence gaps | W | Draft findings distinguishing facts from interpretations | auditor, accountant, controller |
| audit.review | Record engagement review | W | Review trail; no automatically issued audit opinion | auditor, accountant, controller |

## Tax workpapers

Inputs: Engagement scope, source records, tax period and professional assumptions.

| Proposed ID | Tool | Mode | Output | Typical users |
|---|---|---|---|---|
| tax.organizer | Build a tax-document organizer | W | Missing-item checklist and source index | tax, accountant, controller, auditor |
| tax.mapping | Prepare book-to-tax mappings | P | Proposed mappings and unresolved classifications | tax, accountant, controller, auditor |
| tax.adjustments | Prepare book-to-tax adjustments | P | Adjustment schedule with source-linked calculations | tax, accountant, controller, auditor |
| tax.basis | Prepare basis rollforward workpapers | P | Rollforward with assumptions and missing evidence | tax, accountant, controller, auditor |
| tax.calendar | Prepare a sourced obligation calendar | P | Jurisdiction-tagged items requiring current-rule verification | tax, accountant, controller, auditor |
| tax.review | Record tax-workpaper review | W | Review notes; professional release requires separately verified credentials and authority | tax, accountant, controller, auditor |

## Treasury and management

Inputs: Balances, expected cash flows, scenarios and policy constraints.

| Proposed ID | Tool | Mode | Output | Typical users |
|---|---|---|---|---|
| treasury.position | Read a scoped cash position | R | Balances with source timestamps and currency separation | treasury, controller, accountant, owner, auditor |
| treasury.forecast | Prepare a cash-flow forecast | P | Assumption-tagged scenarios and source coverage | treasury, controller, accountant, owner, auditor |
| treasury.runway | Prepare liquidity sensitivity analysis | P | Scenario comparison without a financing commitment | treasury, controller, accountant, owner, auditor |
| treasury.exposure | Review currency and counterparty exposure | P | Exposure schedule and concentration flags | treasury, controller, accountant, owner, auditor |
| treasury.intercompany | Prepare intercompany netting review | P | Proposed offsets and unresolved legal-entity differences | treasury, controller, accountant, owner, auditor |
| treasury.funding | Prepare funding/transfer recommendations | P | Review package only; no money movement | treasury, controller, accountant, owner, auditor |

## Payroll and expense review

Inputs: Payroll reports, expense claims, receipts and scoped employee data.

| Proposed ID | Tool | Mode | Output | Typical users |
|---|---|---|---|---|
| payroll.reconcile | Reconcile payroll to the ledger | P | Gross-to-net and ledger differences with evidence | payroll, accountant, bookkeeper, controller, auditor |
| payroll.accrual | Prepare payroll accruals | P | Accrual schedule and proposed journal | payroll, accountant, bookkeeper, controller, auditor |
| payroll.variances | Review payroll-period variances | P | Employee-data-minimized exception report | payroll, accountant, bookkeeper, controller, auditor |
| expenses.receipts | Suggest receipt matches | P | Candidate transaction matches and missing receipts | payroll, accountant, bookkeeper, controller, auditor |
| expenses.policy | Review expense-policy exceptions | P | Policy-reference exceptions for human review | payroll, accountant, bookkeeper, controller, auditor |
| expenses.reimbursements | Prepare reimbursement review | P | Review workpaper; no approval or payout | payroll, accountant, bookkeeper, controller, auditor |

## Access boundaries

- A person's job title does not itself grant a capability.
- Every action resolves acting identity, organization, account scope and current membership.
- A firm member also needs an active engagement and client assignment. Effective permissions
  are the intersection of firm authority, engagement scope and allowed client capabilities.
- The reviewed firm-access evaluator excludes money-out, approvals, card management,
  recipients, API-key administration, policy changes and user/role administration.
- Auditors may write findings in their own review workspace; their client financial access
  remains read-only. An internal auditor does not inherit a platform administrator's powers.
- Preparation, review, approval, execution and reconciliation are separate stages.
- A requester cannot approve their own request through another key, agent or interface.
- Service principals and agents have narrowed delegated scopes, not independent human roles.
- Technical infrastructure credentials are not product permissions.
- A reviewer may record tax-workpaper notes within scope; professional release additionally
  requires verified credentials and named release authority. Auditor status does not supply it.

No accounts, memberships, roles or permissions are changed by this design package.

## Evidence design reference

The audit-workpaper design distinguishes relevance, reliability and completeness of evidence. PCAOB AS 1105 is one design reference, not a claim that every user or engagement is subject to PCAOB standards: https://pcaobus.org/oversight/standards/auditing-standards/details/AS1105
