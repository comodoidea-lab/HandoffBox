# HandoffBox Agent Guidelines

HandoffBox is a public project ledger. Treat everything written here as
world-readable.

The goal is to help any AI agent resume context from a URL without depending on
private GitHub access, local machine state, AI memory, or one specific editor.

## Core Rules

- Write only public-safe context.
- Keep records concise, factual, and useful for the next agent.
- Do not invent missing history, dates, commands, paths, decisions, or results.
  Write `Unknown / 不明` when the source material does not establish a fact.
- Treat AI memory as preferences and working conventions, not as evidence.
- Treat skills, prompts, and templates as procedures, not proof that work was
  completed.
- Link public evidence when available: public commits, public pull requests,
  public issues, release notes, or public documentation.
- Do not link private evidence unless the link text and surrounding context are
  safe to expose publicly.

## Never Commit Or Record

Never write these into this repository, including examples, templates,
screenshots, logs, comments, or copied command output:

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

If the source material contains sensitive details, summarize the useful context
at a safe level and omit the sensitive parts.

## Project Ledger Format

Each project ledger belongs under `projects/{project-id}/` and should use these
files:

- `PROJECT.md`: stable project overview and scope
- `NEXT.md`: smallest useful next actions
- `JOURNAL.md`: public-safe work log
- `DECISIONS.md`: decision records and rationale

Use the matching templates in `templates/` when creating a new ledger.

## Writing Style

- Put a short human summary first.
- Follow with precise context for AI agents.
- Prefer stable public identifiers over local state.
- Use relative repository paths only when paths are needed.
- Keep commands generic unless the exact command is safe to publish.
- Use `Unknown / 不明` instead of guessing.

## Approval Boundary

Creating or updating public-safe ledger files is allowed when the user asks for
it.

Changing repository visibility, deleting records, publishing sensitive-derived
summaries, or claiming that work is approved or verified requires explicit
human instruction or clear evidence.

AI-generated proposals must remain proposals until a human approves them. Do
not represent proposed work as completed, published, verified, or approved.
