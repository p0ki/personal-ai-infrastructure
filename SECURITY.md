# Security and Publication Boundary

This repository is designed to be safe to share as an **architecture case study**.

It explains how the system is structured without publishing the information required to access, reproduce or attack the private environment behind it.

## Public by design

The following kinds of information are appropriate for this repository:

- high-level architecture,
- agent responsibilities,
- routing concepts,
- deterministic vs agentic workflow design,
- generic tool categories,
- model-selection strategy,
- human-in-the-loop principles,
- representative workflows,
- lessons learned,
- non-sensitive diagrams.

These details show how the system is designed without exposing operational access.

## Intentionally private

The following information must not be committed here.

### Credentials and secrets

Never publish:

- API keys,
- access tokens,
- passwords,
- private keys,
- session cookies,
- webhook secrets,
- OAuth credentials,
- recovery codes,
- environment files containing secrets.

### Network and infrastructure details

Keep private:

- internal IP addresses,
- private DNS names,
- remote-access configuration,
- VPN configuration,
- firewall rules that reveal the private topology,
- exposed management ports,
- exact host mappings,
- credentials or connection strings,
- backup locations that reveal sensitive structure.

Architecture can be described conceptually without exposing the real network map.

### Agent internals

Keep private:

- full system prompts,
- private SOUL/personality files,
- hidden policy files,
- exact authorization rules,
- private memory stores,
- internal tool credentials,
- instructions containing personal or business context.

Agent roles can be explained publicly at the level of purpose and behavior.

### Personal knowledge

Do not publish:

- private Obsidian notes,
- email content,
- calendar data,
- family information,
- personal documents,
- private conversations,
- account identifiers.

Examples in this repository should remain generic or deliberately sanitized.

### Business information

Do not publish information that belongs to an employer, customer or partner, including:

- customer data,
- internal processes that are confidential,
- contracts,
- pricing,
- credentials,
- private repositories,
- unpublished commercial information,
- internal support cases.

Case studies should describe the problem-solving approach without exposing confidential data.

## Human approval boundary

The system uses a simple security principle:

> The ability to reason about an action does not automatically grant permission to perform that action.

A model may be allowed to:

- inspect information,
- summarize,
- diagnose,
- draft a change,
- recommend a command,
- prepare a message,

without automatically being allowed to:

- delete data,
- change production configuration,
- publish externally,
- send a message,
- modify security settings,
- perform financial actions.

This separation limits the consequences of an incorrect model decision.

## Least necessary access

Each integration should receive only the permissions it actually needs.

Where practical:

- read and write capabilities are separated,
- credentials are scoped,
- write actions are approval-gated,
- reversible actions are preferred,
- Git/version history is preserved,
- logs are retained for troubleshooting.

## Local vs cloud privacy

Local models can be useful when information should stay close to the source.

Cloud models can provide stronger capabilities, but data sent to them should be deliberately selected.

The routing layer should therefore consider not only model quality, but also:

- sensitivity of the input,
- required capability,
- latency,
- cost,
- and whether external processing is necessary.

## Before making this repository public

Use this checklist:

- [ ] Search all files for API keys, tokens and passwords.
- [ ] Search for private IP addresses and internal hostnames.
- [ ] Check diagrams for real network topology.
- [ ] Remove personal data and account identifiers.
- [ ] Remove employer/customer confidential information.
- [ ] Confirm that examples are generic or sanitized.
- [ ] Confirm no prompt/SOUL files were copied in.
- [ ] Confirm no real configuration or environment files are present.
- [ ] Review Git history, not only the current files.
- [ ] Review rendered Mermaid diagrams.
- [ ] Open every external link before publication.
- [ ] Read the repository once as if you were an attacker or recruiter.

## Repository rule

If a detail makes the architecture easier to understand but also makes the private environment easier to access, the detail stays private.

The public repository should demonstrate **how I think about AI systems**, not expose the system itself.
