# The AI Hydra — Threat Capability Framework

**Live tracker:** [View the framework →](https://greycardinal45.github.io/ai-hydra-tracker/)

**CVE cross-correlation:** [CVE & AI capability analysis →](https://greycardinal45.github.io/ai-hydra-tracker/cve-analysis/)

**Whitepaper:** [The AI Hydra: When Worms Learn to Think (PDF) →](docs/AI-Hydra-Whitepaper.pdf)

A living intelligence tracker mapping the convergence of autonomous AI, offensive cyber tooling, and the engineering gaps that remain before fully autonomous AI-enabled offensive cyber operations become feasible.

## What This Is

The AI Hydra framework models a hypothetical semi-autonomous offensive cyber architecture comprising four layers:

- **Operator Control Plane** — human sets the target, objective, and risk tolerance
- **AI Orchestration Engine** — makes tactical decisions autonomously in the field
- **Hybrid C2 Backbone** — multi-channel command and control mimicking legitimate traffic
- **Tool & TTP Layer** — seven-phase kill chain continuously updated via an adversary SDLC (weapons foundry)

Each of the 32 capabilities required for this architecture is assessed as:

- 🟢 **Exists Today** — demonstrated in defensive tools, commodity malware, or documented APT TTPs
- 🟡 **Partially Exists** — proven in sandbox/research or partially demonstrated in the wild
- 🔴 **Engineering Gap** — not yet demonstrated; the remaining integration challenges

## Current Status

| Status | Count | Percentage |
|--------|-------|------------|
| Exists Today | 17 | 53% |
| Partially Exists | 11 | 34% |
| Engineering Gap | 4 | 13% |

The four remaining gaps are all orchestration / integration-layer problems: selective IP targeting, legitimate user traffic mimicry, automated field-to-foundry feedback loop, and full adaptive SOC evasion.

## How to Update

The tracker is data-driven. To add intelligence or update a gap status:

1. Edit the relevant JSON file in `/data/`
2. Commit and push
3. GitHub Pages rebuilds automatically

### Adding a new intelligence document

Edit `data/intel.json` and add an entry:

```json
{
  "id": "intel-unique-id",
  "date": "2026-06-15",
  "title": "Title of the finding",
  "source": "Source organisation",
  "type": "Category (e.g. Autonomous malware, Zero-day, Supply chain worm)",
  "severity": "critical|high|medium|low",
  "url": "https://source-url",
  "summary": "One-paragraph summary of the finding and its significance.",
  "gapsAffected": ["ia-1", "ao-3"]
}
```

### Updating a gap status

Edit `data/gaps.json`. To move an item from `gap` to `partial`:

```json
{
  "id": "ao-3",
  "status": "partial",
  "source": "Updated source description",
  "updated": "2026-06-15",
  "changed": "2026-06-15",
  "previousStatus": "gap",
  "evidence": "intel-unique-id"
}
```

### Adding a timeline entry

Edit `data/changelog.json` and add to the top of the array:

```json
{
  "date": "2026-06-15",
  "entry": "Description of the update."
}
```

## Data Files

| File | Purpose |
|------|---------|
| `data/gaps.json` | 32 capability assessments with status, source, and evidence links |
| `data/intel.json` | Intelligence document registry with severity, source URLs, and gap mappings |
| `data/changelog.json` | Timeline of framework updates |

## Origin

Framework created March 2026. Think tank working group established February 2026 to review the threat and viability of AI-enabled offensive cyber beyond phishing, deepfake, and malware engine evasion. Presented at Infosec Europe, June 2026.

## Author

**Darren Humphries** — Group CISO

## Licence

Data licensed [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Code licensed [MIT](https://opensource.org/licenses/MIT).
