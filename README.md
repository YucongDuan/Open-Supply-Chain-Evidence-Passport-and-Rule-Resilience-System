# DIKWP-MESH8.1 TRACE81

Created by Yucong Duan (段玉聪).

Open Supply-Chain Evidence Passport and Rule-Resilience System  
Prove the chain, not just manage it.

TRACE81 helps exporters, importers, buyers, counsel, auditors, financial institutions, insurers, and industrial parks organize fragmented supplier records, lot events, origin evidence, labour due diligence, commercial records, and logistics documents into a traceable, versioned, portable, and reviewable evidence package.

It does not issue a black-box compliance score and never treats name similarity as legal identity. It preserves:

- D: source records, events, file digests, and invariants across versions;
- I: missing, conflicting, stale, ambiguous, or unbalanced records;
- K: a stage-bounded evidence passport for the current lot and rule pack;
- W: jurisdiction, market, rule version, buyer policy, and disclosure boundary;
- P: tracing, screening, evaluation, remediation, export, signing, review, and replay.

A `11111` vector means that the five review structures are operational. It is not a legal compliance finding, admissibility decision, entity-identity determination, or forced-labour finding.

## Features

- Local SQLite evidence ledger and append-only SHA-256 audit chain;
- multi-tier lot, facility, organization, transformation, and shipment trace;
- versioned rule packs and snapshot diffs;
- name/alias review with explicit identity uncertainty;
- evidence coverage, freshness, mass-balance, and remediation tasks;
- public and assurance passport views;
- GS1 EPCIS 2.0-style event export;
- W3C VC 2.0-inspired evidence envelope with optional Ed25519 signing;
- portable evidence dossier ZIP with manifests and digests;
- single-file offline dashboard;
- dependency-free Python core, with optional cryptography.

## Quick start

```bash
python -m trace81 demo --db data/examples/trace81_demo.sqlite --evidence-dir data/examples/evidence
python -m trace81 evaluate --db data/examples/trace81_demo.sqlite --case CASE-SNACK-US --rulepack builtin:uflpa_us_2026-08-03 --out artifacts/evaluation.json
python -m trace81 dossier --db data/examples/trace81_demo.sqlite --case CASE-SNACK-US --rulepack builtin:uflpa_us_2026-08-03 --out artifacts/dossier.zip
```

Or run the standalone archive:

```bash
python dist/TRACE81.pyz --help
```

## Official snapshot boundary

The included `US-UFLPA-2026-08-03` pack contains only the 43 unique additions effective August 3, 2026. It is not the complete 187-entity list and must not be used as the sole screening source. Production deployments must synchronize current official sources, importer records, CBP guidance, and case-specific legal advice.

## Commercial layer

The code is Apache-2.0. Commercial opportunities include private deployment, ERP/MES/WMS connectors, supplier collaboration, rule intelligence subscriptions, managed dossier generation, auditor interfaces, industry rule packs, and TRACE81 Conformance testing. The TRACE81 name and conformity mark should be managed as project trademarks.

## Open protocol and conformance

- `docs/SECP_SUPPLY_EVIDENCE_CONTINUITY_PROTOCOL_DRAFT_CN_EN.md`: Supply Evidence Continuity Protocol 0.1 open draft;
- `docs/TRACE81_CONFORMANCE_PROFILE_CN_EN.md`: C01-C10 software data/interface behaviour profile; it does not certify a company, factual conditions, or legal outcomes.
