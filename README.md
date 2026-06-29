# HandoffBox

HandoffBox is a public context ledger for AI agents and humans.

This repository is my AI shared context for personal projects. It is published
primarily for AI agent interoperability.

It stores project context that should be easy to read from a URL: what a
project is, why it exists, what should happen next, and which decisions have
already been made. It is not a place for application source code, private
customer data, credentials, or personal records.

## Why Public

HandoffBox is public so any AI agent can read the shared project context
without depending on a specific login session, private memory store, editor, or
orchestrator.

Private repositories created repeated friction: one agent could read a record,
another could not; one tool had GitHub credentials, another did not. A public
ledger removes that access problem. The tradeoff is strict discipline: only
publish context that is safe for anyone on the internet to read.

## What Belongs Here

- Project summaries
- Design intent
- Next actions
- Decision records
- Public-safe work logs
- Handoff notes for AI agents

Each project should live under `projects/{project-id}/` and use the same four
ledger files:

- `PROJECT.md`: project purpose, scope, audience, and links
- `NEXT.md`: the next concrete actions
- `JOURNAL.md`: public-safe work log
- `DECISIONS.md`: decisions and their reasons

Use `templates/` when starting a new project ledger.

## What Must Never Be Written

Do not write any of the following in this repository:

- Personal information
- Email addresses
- Phone numbers
- Physical addresses
- API keys
- Access tokens
- Passwords
- Local machine absolute paths
- Personal financial details, including income, expenses, or living costs
- Customer information
- Unpublished sourcing or purchasing candidates
- Screenshots that contain personal information
- Confidential information from private repositories

When recording work, summarize it at a public-safe level. If a detail would
only be safe inside a private project repository, keep it out of HandoffBox.

## Directory Layout

```text
HandoffBox/
├── README.md
├── AGENTS.md
├── projects/
│   └── example-project/
│       ├── PROJECT.md
│       ├── NEXT.md
│       ├── JOURNAL.md
│       └── DECISIONS.md
└── templates/
    ├── PROJECT.template.md
    ├── NEXT.template.md
    ├── JOURNAL.template.md
    └── DECISIONS.template.md
```

## Working Rule

HandoffBox is not a task manager. It is a shared memory surface.

Use it to preserve the reasoning around a project:

- Why are we building this?
- What is the current shape of the plan?
- What should the next agent do first?
- Which decisions are already settled?
- What public evidence supports the current state?

Keep implementation code, private details, credentials, and sensitive logs in
their proper repositories or systems.
