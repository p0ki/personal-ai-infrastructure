# Security and Publication Boundary

This repo is meant to be safe enough to publish without publishing the keys to the castle.

It shows the architecture and the thinking behind the system.

It does **not** show the operational details someone would need to reproduce, access or attack the real environment.

## Safe to show

Things that are fine to publish:

- high-level architecture,
- agent roles,
- routing logic,
- local vs cloud strategy,
- generic integrations,
- workflow patterns,
- approval philosophy,
- sanitized diagrams,
- lessons learned.

That is enough to show how the system works without leaking the system itself.

## Keep private

### Secrets

Never commit:

- API keys,
- tokens,
- passwords,
- private keys,
- cookies,
- OAuth secrets,
- webhook secrets,
- recovery codes,
- secret-filled environment files.

Obvious rule, still worth writing down.

### Real infrastructure details

Keep private:

- internal IPs,
- private DNS names,
- remote-access config,
- VPN config,
- firewall rules that expose topology,
- management ports,
- host mappings,
- connection strings,
- backup locations that reveal too much,
- exact service-to-service paths.

A diagram should explain the architecture, not double as recon material.

### Agent internals

Keep private:

- full system prompts,
- SOUL/personality files,
- hidden policies,
- exact internal authorization rules,
- private memory stores,
- tool credentials,
- prompts containing personal or business context.

The public repo explains what the agents do.

It does not publish their full brains.

### Personal data

Do not publish:

- private notes,
- email content,
- calendar data,
- family information,
- private documents,
- private conversations,
- account identifiers.

### Business data

Do not publish:

- customer data,
- private employer information,
- contracts,
- pricing,
- unpublished commercial data,
- support cases,
- private repositories,
- confidential internal processes.

Public case studies should explain the engineering problem, not leak somebody else's business.

## Autonomy model

The system is **autonomous by default**.

That means routine work should not stop and ask for permission every five minutes.

Safe examples:

- read logs,
- run diagnostics,
- check service state,
- research,
- summarize,
- update low-risk documentation,
- run normal API workflows,
- perform reversible routine fixes.

Approval kicks in when the blast radius becomes meaningful.

Examples:

- deleting important data,
- major firewall/network changes,
- destructive storage operations,
- risky production changes,
- publishing externally,
- external communication with consequences,
- financial or account actions.

The principle is simple:

> Autonomy for normal work. Approval for actions that can actually hurt.

## Least necessary access

Agents should get the tools they need, not god mode.

Where practical:

- read and write scopes are separated,
- credentials are narrow,
- high-impact writes are gated,
- version history is preserved,
- reversible actions are preferred,
- logs exist,
- backups exist.

A smart model with narrow permissions is usually safer than a mediocre model with root.

## Local vs cloud privacy

Local models are useful when data should stay local.

Cloud models are useful when stronger capabilities matter.

Routing should consider:

- sensitivity,
- task difficulty,
- latency,
- cost,
- whether external processing is necessary.

The best model is not automatically the right model.

## Before making the repo public

Run this checklist:

- [ ] Search every file for API keys and tokens.
- [ ] Search for emails and account IDs.
- [ ] Search for private IPs and hostnames.
- [ ] Check diagrams for real network topology.
- [ ] Check examples for personal information.
- [ ] Check examples for employer/customer information.
- [ ] Confirm no prompt or SOUL files slipped in.
- [ ] Confirm no production config is present.
- [ ] Review the full Git history.
- [ ] Check rendered Mermaid diagrams.
- [ ] Review external links.
- [ ] Read the repo once like a recruiter.
- [ ] Read it again like an attacker.

## One rule that covers most of this

If a detail makes the system easier to understand **and** makes the real environment easier to attack, it stays private.

This repo should show how I think.

It should not show how to get in.
