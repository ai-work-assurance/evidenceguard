# EvidenceGuard V0.1

**AI Work Assurance**  
*Skills and guardrails for trustworthy, traceable, and defensible AI-assisted work.*

EvidenceGuard audits whether factual claims in AI-assisted knowledge work are adequately supported by the evidence provided. It produces a structured, reviewable assessment without deciding whether the underlying work should be published, approved, or acted on.

EvidenceGuard is general-purpose. It can be used on executive briefs, policy summaries, consulting reports, product documents, operational analyses, research outputs, and other evidence-dependent work.

## What it detects

- unsupported factual claims;
- claims that are only partially supported;
- citation-role mismatch, such as using a forecast to support an observed fact;
- stale or otherwise insufficient sources;
- causal claims supported only by association, sequence, opinion, or uncontrolled comparison;
- numeric inconsistency across claims, evidence, tables, or calculations; and
- unclear population or timeframe.

EvidenceGuard does not verify facts against the open web by default, judge writing style, generate missing evidence, or replace domain, legal, compliance, or editorial review.

## Package contents

```text
evidenceguard/
├── README.md
├── SKILL.md
├── examples/
│   ├── 01-executive-market-brief.md
│   ├── 02-policy-change-summary.md
│   └── 03-customer-analytics-report.md
├── evals/
│   ├── benchmark_cases.json
│   └── expected_results.json
└── schemas/
    └── claim_evidence.schema.json
```

## Quick start

Provide:

1. the text or deliverable to audit;
2. the evidence pack, citations, or source excerpts available to the author; and
3. any known date, audience, jurisdiction, or decision context.

Then instruct the agent:

```text
Use EvidenceGuard to audit the attached deliverable against the supplied evidence.
Return a claim-level report conforming to schemas/claim_evidence.schema.json.
Do not infer missing support or browse for new evidence unless I explicitly ask.
```

The canonical instructions are in [`SKILL.md`](SKILL.md). The JSON Schema defines the machine-readable output contract. The examples show how findings should be reasoned and reported. The eval files contain five portable benchmark cases and their expected results.

## Use with Claude Code, Codex, and Gemini CLI

EvidenceGuard is file-based and does not depend on a proprietary runtime.

- **Claude Code:** place or link this directory within the working project, ask Claude Code to read `SKILL.md`, and provide the target material and evidence in the same task context.
- **Codex:** keep the directory in the workspace or an available skills location, then instruct Codex to use `SKILL.md` for the audit. If automatic skill discovery is not configured, reference the file explicitly.
- **Gemini CLI:** keep the directory in the working project and ask Gemini CLI to follow `SKILL.md` while auditing the supplied files. Use explicit file references where local skill discovery differs.

Exact discovery and installation conventions vary by tool and version. The portable baseline is manual, file-based use: make `SKILL.md`, the schema, the target material, and its evidence available in context. No tool-specific commands are required by EvidenceGuard V0.1.

## Output at a glance

An audit identifies each material factual claim, records its support status, links it to evidence, and reports any integrity findings. Each finding includes a type, severity, explanation, evidence basis, and a concrete remediation. Global limitations and escalation needs are reported separately.

EvidenceGuard uses four claim-level support statuses:

- `supported`
- `partially_supported`
- `unsupported`
- `indeterminate`

A clean audit means no material integrity issue was found in the supplied material. It does **not** prove that the claims are true, complete, current, or fit for every downstream use.

## Version boundary

V0.1 audits claim–evidence integrity from materials supplied in the task. It does not retrieve sources, score source reputation with a universal ranking, validate legal compliance, or authorize external release.

