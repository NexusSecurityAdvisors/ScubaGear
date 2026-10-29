# ScubaGear at Nexus Security Advisors

This is the Nexus Security Advisors fork of [cisagov/ScubaGear](https://github.com/cisagov/ScubaGear). ScubaGear is CISA's tool for assessing Microsoft 365 tenants against the SCuBA secure configuration baselines (CC0-1.0).

**The upstream code is unchanged.** This `nexus/` folder adds how we use ScubaGear in client engagements.

## Why it matters for SMBs

Most small and mid-sized businesses run on Microsoft 365, and most M365 breaches start with a misconfiguration: legacy authentication, weak MFA, permissive sharing, or missing audit logging. ScubaGear checks these against a **federal baseline**, which gives clients an objective, defensible benchmark.

## How Nexus uses it

| Engagement | Use |
|---|---|
| **Fractional vCISO** | Baseline and quarterly M365 configuration reviews |
| **Compliance readiness** | Evidence for CMMC / 800-171, HIPAA, SOC 2, and cyber-insurance questionnaires (MFA, logging, email security) |
| **Security posture assessment** | Automated evidence for the M365 portion of our NIST CSF 2.0 posture review |

## Contents

| File | Purpose |
|---|---|
| [`assessment-runbook.md`](assessment-runbook.md) | Step-by-step client assessment procedure |
| [`framework-mapping.md`](framework-mapping.md) | How ScubaGear results map to NIST CSF 2.0, CMMC / 800-171, HIPAA, and SOC 2 |
| [`client-report-checklist.md`](client-report-checklist.md) | Quality gate before a report goes to a client |

## Keeping this fork current

CISA updates the baselines regularly. Sync with upstream before every engagement (**Sync fork**) and record the ScubaGear and baseline versions used.

## Disclaimer

Results are a point-in-time view and do not constitute an audit opinion, certification, or legal advice. Not affiliated with or endorsed by CISA.

---

**Nexus Security Advisors** · Fractional CISO and AI governance for SMBs · SDVOSB
[nexussecurityadvisors.com](https://nexussecurityadvisors.com) · [info@nexussecurityadvisors.com](mailto:info@nexussecurityadvisors.com)
