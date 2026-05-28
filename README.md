# RunDrill AWS

Your personal **AWS cloud-certification coach** inside your AI agent — prep the whole ladder
(**Foundational → Associate → Professional → Specialty**) the way the exam actually demands it: by
**choosing the best service under real constraints** and **reviewing real AWS configs for the planted
flaw**, not by memorising service lists or watching the AI design your architecture. Short targeted
drills, an honest picture of your tier, mistake memory that resurfaces what you got wrong, and timed
mock exams. Your tier and progress live on the RunDrill MCP server (`mcp.rundrill.com`), synced across
machines — not in a local file.

**Why this course is different.** AWS exams don't reward recall — they hand you a scenario with
competing constraints (cost, latency, availability, security, operational overhead) and several
plausible services, and ask which fits BEST. The skill that matters is *discrimination under
constraints*: which service, and **why not** the near-neighbours. When an AI can draft any architecture
or template on demand, the real risk is the *illusion of competence* — accepting one that reads fine
and is quietly wrong: an over-broad IAM `*`, a single-AZ "highly available" design, a public subnet
that isn't, Multi-AZ used for read scaling. Every drill is **blended** — an exam-style scenario
decision paired with a hands-on console/CLI/IaC task you run in your own account — and the **signature
drill hands you a real AWS config with a planted flaw and asks you to find it, like a security
review.** Plus timed, domain-weighted **mock exams** as a per-cert boss battle (timed practice is the
strongest readiness signal).

The course mirrors the AWS certification ladder — **Foundational** (Cloud Practitioner, AI Practitioner)
→ **Associate** (Solutions Architect, Developer, SysOps/CloudOps, Data Engineer, ML Engineer) →
**Professional** (Solutions Architect, DevOps) → **Specialty** (Security, Advanced Networking). Pick the
certification you're aiming for; the shared Foundational base is always in scope, and a track can span
tiers (the architect path runs Associate → Professional).

> **Cost & safety.** Hands-on tasks run in **your own AWS account**. The coach flags anything billable,
> prefers the free tier, and reminds you to tear it down.

**Learn in your language.** The AWS exam and console are in English, but you don't have to study only in
English: set your native language and the coach explains in it while giving every AWS service and term
as *native (English original)* — so you reason naturally and still recognise the official terms on the
exam.

## One plugin, three hosts

The coaching skill (`skills/aws-coach/SKILL.md`) and `.mcp.json` are shared; each host reads its own
manifest and ignores the rest.

| Host | Reads |
|---|---|
| Claude Code / Claude Desktop | `.claude-plugin/plugin.json` + `.mcp.json` |
| OpenAI Codex | `.codex-plugin/plugin.json` + `.mcp.json` |
| Google Antigravity | `plugin.json` + `mcp_config.json` (+ `rules/`) |

The MCP endpoint is `https://mcp.rundrill.com/skills/aws` — the skills-course host, passing
`subject: "aws"`. The server routes on the `/skills` segment and ignores the course name; the name makes
AWS register as its own MCP server in your agent. On first use the host opens a browser tab for the
OAuth handshake, then closes it — no API key to paste.

## Install

- **Claude Code / Desktop** — via the RunDrill marketplace:
  ```
  /plugin marketplace add rundrill/rundrill
  /plugin install rundrill-aws@rundrill
  ```
  Then run `/aws-coach`.
- **OpenAI Codex** — `codex plugin marketplace add rundrill/rundrill`, then install `rundrill-aws`.
- **Google Antigravity** — drop this folder into `~/.gemini/config/plugins/rundrill-aws/` (global) or
  `<workspace>/.agents/plugins/rundrill-aws/` (workspace-scoped).

## A note on AWS®

This is an independent study aid for learning Amazon Web Services and preparing for AWS Certification
exams. It is **not** affiliated with, authorized, or endorsed by Amazon Web Services, Inc. *AWS®* and
the AWS certification names are trademarks of Amazon.com, Inc. or its affiliates. The course teaches the
publicly documented services and exam domains in our own words; it does not reproduce AWS exam content.
AWS changes services, limits, and certifications frequently — always confirm current details against
the official AWS documentation.

## License & attribution

© RunDrill. Licensed under **Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International
(CC BY-NC-ND 4.0)** — full text in [LICENSE](LICENSE). You may view, run, and share this plugin
unchanged, non-commercially, with attribution; you may not use it commercially or publish
modified/derivative versions. For other licensing, contact **hello@rundrill.com**.
