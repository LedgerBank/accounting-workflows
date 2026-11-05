# accounting-workflows

## Technology layout and evaluated stack

- [Accounting architecture](docs/ARCHITECTURE.md)

Documentation updated November 5, 2026. This update adds architecture/evaluation documentation; source and runtime migration are separately scoped.

Evidence-based accounting workflow and workpaper designs.

**Status: presentation preview.** This repository contains scope and design documentation. It does not contain a released implementation or a live service.

## Role in the headless platform

LedgerBank is being organized around a common financial capability layer. Applications,
accounting workflows, SDKs, the CLI and agents are intended to consume that layer through
reviewed interfaces. Financial authority and permissions remain in the platform.

**Primary audience:** accountants. **Repository visibility:** public.

## Planned scope

- Specify cash reconciliation, accounts payable and receivable review workflows.
- Design proposed journal entries with source evidence and reviewer decisions.
- Describe month-end close checklists and exception resolution.
- Separate preparing a workpaper from posting entries or filing anything.

## Read next

- [Scope and boundaries](docs/SCOPE.md)
- [First implementation acceptance criteria](docs/ACCEPTANCE.md)
- [Current repository status](STATUS.md)
- [developers](https://github.com/LedgerBank/developers) for the proposed public architecture and integration map

## Preview boundary

This is a new presentation scaffold. Existing repositories, branches, services and
documents have not been migrated here. Package names, hosted endpoints, releases and
support commitments will be documented only when they exist and have been verified.
