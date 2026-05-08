# Open Standards as AI Governance Infrastructure

## Auditing, Measuring, and Taxing Digital Employees

*A scenario-based white paper on AI agent accountability — Version 2.1, May 2026*

Drafted by AI — Opus 4.7. Project lead and editor: Marshal J. Contact: Marshal J.

> **Source note.** This Markdown rendering was extracted from the canonical PDF (`Open Standards as AI Governance Infrastructure.pdf`) and lightly normalized. The PDF remains authoritative; if a passage differs, the PDF wins. Mathematical notation has been reconstructed from PDF text-extraction output and may have minor formatting differences from the original.

---

## Authorship and Verification Note

This paper was drafted by an AI system (Anthropic Claude — Opus 4.7) at the direction of Marshal J, who set the scope, requested specific edits, and owns the document for distribution and contact purposes. Marshal J is not an economist and has not independently verified the formal results cited (Falk and Tsoukalas 2026; Acemoglu and Restrepo; Autor; Korinek), the OECD Pillar Two architectural details, or the equation τ* ≈ ℓ(1 − 1/N) presented in Section 3.

The paper's recommendations should therefore be treated as a structured discussion document rather than as an authoritative scholarly contribution. Before acting on Recommendations 4 and 5 (sectoral Pigouvian pilots and OECD coordination), policymakers should commission independent peer review of:

1. The Falk and Tsoukalas (2026) result against asymmetric-firm and oligopolistic-input-market extensions;
2. The compatibility of the proposed agent-tax architecture with the Pillar Two implementation as it actually exists in 2026, including bilateral side-deals and QDMTT interpretations;
3. The empirical premises in Sections 2.3, 3.1, and Scenario A regarding labor-tax-base erosion magnitude and timing.

This note is included in the spirit of the paper's own argument: the substrate the paper advocates for rests on transparent attribution of work to the agent that performed it and the principal that directed it. Applying that standard to the paper itself is a precondition for credibility.

## Note to Reader

This paper presents two arguments at different levels of abstraction. Sections 1–6 develop a narrow, technically-grounded case: open standards plus mandates plus identity registration enable a specific Pigouvian instrument that corrects a specific labor-displacement externality. Section 7 reframes the same machinery more broadly: the standards stack is mechanism-design infrastructure, with the Pigouvian instrument as one application among many. Section 8 states the joint argument honestly.

Readers focused on the immediate policy mechanics may prefer Sections 1–6 first. Readers focused on the longer-run governance question — who controls the substrate that open standards are creating — may prefer to read Section 7 before working back through the specifics. The narrow argument is what is actionable in the 2026–2030 window; the broader argument is what is at stake.

## Executive Summary

AI agents — increasingly marketed as "digital employees" or "digital workers" — are being deployed at industrial scale across enterprises in 2026. Unlike previous waves of automation, these systems take autonomous, multi-step actions on behalf of principals: drafting filings, executing transactions, communicating with third parties, and coordinating with other agents.

A layered stack of open protocols has emerged to make these agents interoperable: the Model Context Protocol (MCP) for tool access, the Agent-to-Agent protocol (A2A) for inter-agent communication, the Agent Client Protocol (ACP) for editor integration, and AG-UI for frontend streaming. Governance bodies — the Linux Foundation's Agentic AI Foundation (AAIF) and NIST's Center for AI Standards and Innovation (CAISI) — have begun to coordinate the ecosystem.

These standards provide the technical plumbing required for three public-policy goals:

1. **Audit** — reconstructing what an agent did, on whose behalf, with what authority.
2. **Measurement** — accounting for agent work in units that policy can act on.
3. **Taxation** — capturing a share of the value agents generate, particularly where they substitute for human labor.

The standards are necessary for these goals. They are not sufficient. This paper presents five primary scenarios plus one pessimistic variant — six in total — for how the standards-governance relationship could evolve between 2026 and 2032, examines the gaps that must be filled by policy, and offers recommendations for governments and standards bodies.

The central finding: **open standards alone produce auditability in principle but not in practice.** Without mandates on adoption, identity registration, and standardized work-record reporting, the audit-measure-tax goals remain technically possible but operationally unreachable. Recent formal analysis (Falk and Tsoukalas, 2026) further establishes that the only policy instrument that corrects the over-automation externality created by competitive AI deployment — a Pigouvian automation tax — requires precisely the firm-level measurement infrastructure that mandated open standards would provide. The case for standards-based governance is therefore not merely normative but structural. The window to align standards with policy is 2026–2030.

## Table of Contents

- [1. The Open Standards Stack](#1-the-open-standards-stack)
- [2. Three Public-Policy Goals](#2-three-public-policy-goals)
  - 2.1 Audit
  - 2.2 Measurement
  - 2.3 Taxation
- [3. Why Only One Instrument Works: The Pigouvian Case](#3-why-only-one-instrument-works-the-pigouvian-case)
  - 3.1 The Demand Externality
  - 3.2 The Policy Instrument Horse Race
  - 3.3 Implications for Open Standards
  - 3.4 Caveats
  - 3.5 Relation to the Broader Automation-Economics Literature
- [4. Six Scenarios (2026–2032)](#4-six-scenarios-20262032)
- [5. Cross-Cutting Issues](#5-cross-cutting-issues)
- [6. Recommendations](#6-recommendations)
- [7. Beyond the Pigouvian Frame: Open Standards as Mechanism-Design Infrastructure](#7-beyond-the-pigouvian-frame-open-standards-as-mechanism-design-infrastructure)
- [8. The Honest Frame](#8-the-honest-frame)
- [References](#references)
- [Appendix A: Specimen Agent Authority Card](#appendix-a-specimen-agent-authority-card)

---

## 1. The Open Standards Stack

Four protocol layers now define the agent infrastructure landscape:

**Tool access — MCP.** Released by Anthropic in November 2024 and donated to the Linux Foundation in December 2025, MCP standardizes how an agent connects to external tools, APIs, and data sources. Adoption has been rapid; SDK download metrics exceed 90 million per month and every major model provider has shipped MCP support.

**Agent-to-agent communication — A2A.** Released by Google in April 2025 and donated to the Linux Foundation in June 2025. IBM's competing Agent Communication Protocol merged into A2A in August 2025. Launch partners include Salesforce, SAP, ServiceNow, and approximately fifty other enterprise vendors.

**Editor integration — ACP.** Released by Zed in August 2025 for embedding agents inside code editors. Distinct from IBM's discontinued ACP.

**Frontend streaming — AG-UI.** Released by CopilotKit in early 2026. Standardizes the event stream from agent backends to user interfaces. AWS Bedrock AgentCore added native AG-UI support in March 2026.

Adjacent layers under development include AP2 and UCP for agent-mediated commerce and ANP for inter-organizational agent discovery.

**Governance overlay.** The Agentic AI Foundation (AAIF), co-founded by Anthropic, Block, and OpenAI with support from Google, AWS, Microsoft, Cloudflare, and Bloomberg, is the permanent home for both MCP and A2A. NIST's CAISI launched the AI Agent Standards Initiative on February 17, 2026, focused on industry-led interoperability and security standards. The NIST National Cybersecurity Center of Excellence (NCCoE) is separately developing standards-based approaches to agent identity and authorization.

**The identity gap.** Today's agents typically impersonate human users via OAuth tokens. This breaks audit at the most basic level: logs cannot reliably distinguish between a human user and an agent acting under that user's credentials. Closing this gap is the most active area of standards work in mid-2026, with proposals including DNSid (Identity Digital, April 2026), NCCoE's concept paper on software and AI agent identity, and OpenID Foundation extensions.

## 2. Three Public-Policy Goals

### 2.1 Audit

**The question:** Can a regulator, court, or internal compliance officer reconstruct what an agent did, in what order, on whose behalf, and under what authority?

The protocol stack already provides much of what is required. MCP tool calls are structured and loggable. A2A messages have task identifiers and lifecycle states. AG-UI emits typed event streams. The missing piece is verifiable identity binding the action to a specific agent and a specific principal. Without this, audit logs are unsigned text — useful for diagnostics, insufficient for accountability.

### 2.2 Measurement

**The question:** How much "work" did an agent do, in units that policy can use?

This is the least mature area. Available proxies — token consumption, tool-call counts, compute hours — measure inputs, not output. None of them map cleanly to concepts a regulator cares about: tasks completed, decisions made, value generated, full-time-equivalent hours displaced. A2A's task lifecycle primitives are designed for coordination, not for productivity accounting. No standardized "agent work record" exists.

### 2.3 Taxation

**The question:** How should the public capture a share of the value agents generate, particularly where they substitute for human labor?

Approximately three-quarters of U.S. federal tax revenue derives from labor. If agents substitute for labor at scale, this base erodes regardless of what governments do. Active proposals include excise taxes on automating technology (Sanders), AI-industry revenue taxes funding redistribution programs (Kelly), and capital-stock taxation of highly autonomous systems (Korinek and co-authors at Brookings, January 2026). The Tax Foundation and others contest whether the existing tax code already advantages automation or whether new agent-specific instruments are warranted. The debate is live and unresolved.

## 3. Why Only One Instrument Works: The Pigouvian Case

A working paper by Falk and Tsoukalas (March 2026) provides the formal economic argument that under-girds the policy goals identified in Section 2. The result is sharp enough to warrant separate treatment: of the six commonly proposed policy responses to AI-driven labor displacement, only one — a Pigouvian automation tax — operates on the margin where the externality resides.

### 3.1 The Demand Externality

Falk and Tsoukalas develop a task-based model in which symmetric firms in a competitive market each choose what fraction of their workforce to replace with AI. Displaced workers are also consumers; their forgone wage spending reduces every firm's revenue.

The central result is that this creates a Prisoner's Dilemma. Each firm captures the full cost saving from automating but bears only 1/N of the resulting aggregate demand destruction; the remainder falls on rivals. Automating is therefore a strictly dominant strategy, even when every firm has perfect foresight about every other firm's behavior. The over-automation wedge — the gap between equilibrium and the cooperatively efficient automation rate — is:

> α^NE − α^CO = ℓ(1 − 1/N) / k

where ℓ = (1−η)wλ is the demand lost per displaced worker, λ is workers' marginal propensity to consume the sector's output, η is the fraction of displaced wage income recovered through reemployment or transfers, w is the wage, and k is the convex integration friction.

Two comparative statics are counterintuitive and policy-relevant.

**More competition widens the wedge.** A monopolist (N = 1) fully internalizes the externality; fragmented markets externalize it onto rivals. As N → ∞, the wedge approaches its maximum of ℓ/k. This runs against the standard intuition that competition disciplines firms in consumers' interests: here, more competition dilutes each firm's share of the demand loss and weakens the private incentive to restrain.

**Higher AI productivity also widens the wedge.** This is a "Red Queen" effect: each firm perceives a market-share gain from automating beyond rivals, but in symmetric equilibrium those gains cancel, leaving only the additional distortion. Better AI does not resolve the demand problem — it amplifies the externality.

The over-automation outcome is not a transfer from workers to owners. It is a deadweight loss that harms both groups: workers lose wage income directly, and firm owners' equilibrium profit falls below the cooperative-optimum level because aggregate demand has been eroded. The Nash equilibrium is Pareto-dominated by the cooperative optimum.

### 3.2 The Policy Instrument Horse Race

Falk and Tsoukalas evaluate six candidate policy instruments against the externality margin. Five fail to fully correct the distortion:

- **Universal Basic Income** changes profit levels (the constant Π₀ in the firm's profit function) but not the per-task margin where the automation decision is made. UBI cushions displacement but does not alter the equilibrium automation rate.
- **Capital income taxation** scales the entire profit function by (1 − t) and cancels from the first-order condition. The equilibrium rate is unchanged. The authors note this is structurally distinct from per-unit "robot taxes," which operate on the right margin.
- **Coasian bargaining** cannot sustain the grand coalition required to close the wedge. Automation is strictly dominant, so any partial coalition leaves a residual wedge proportional to the fraction of firms outside the agreement. Worker-side bargaining cannot reach the cross-firm channel through which the externality flows.
- **Worker equity participation** narrows the wedge because shared profits recycle into worker spending, but cannot close it whenever workers' marginal propensity to consume the sector's good is below 1. Voluntary profit-sharing also fails to arise: the marginal cost to a firm of sharing exceeds the marginal demand benefit it captures.
- **Upskilling and retraining** raise the income-replacement parameter η, shrinking ℓ and the wedge. This is a partial fix; closing the wedge would require η = 1, full income replacement.

Only the **Pigouvian automation tax** fully corrects the externality. The optimal rate is:

> τ* = ℓ(1 − 1/N)

This is precisely the share of the demand loss the firm does not currently internalize — the demand loss imposed on rivals. For large N, τ* ≈ ℓ = (1−η)wλ, so setting the rate requires only sector-level observables. Levying the tax requires observing firm-level automation rates.

The result is robust to the model's main extensions. Endogenous wage adjustment raises the threshold at which the externality activates but cannot close the wedge once it does. Free entry, capital-income recycling, AI productivity gains, and richer product-market competition all preserve or amplify the distortion.

### 3.3 Implications for Open Standards

The Falk and Tsoukalas argument turns the case for open-standards-based measurement infrastructure from a normative preference into a structural necessity. Their model proves that the only policy instrument capable of correcting the demand externality requires firm-level observability of automation. They observe that "a tax authority can compel disclosure through mandatory reporting, payroll records, and procurement audits" — precisely the regime described in Scenario B (standardized work records, mandatory identity registration, sectoral mandates).

Without that infrastructure, governments are constrained to instruments that the formal model proves do not work: UBI, capital income taxes, voluntary bargaining. The choice between Scenario A (drift) and Scenario B (mandated standards) therefore becomes the choice between leaving the externality uncorrected and gaining access to the instrument that corrects it.

The model also offers a self-limiting feature relevant to policy design. If revenue from the automation tax funds retraining programs that raise η, the demand-loss parameter ℓ falls, and τ* declines in subsequent periods. The corrective instrument is potentially transitional rather than permanent — provided the underlying displacement is genuinely reabsorbed.

### 3.4 Caveats

Three qualifications. First, Falk and Tsoukalas is an arXiv preprint and has not yet completed peer review. Second, the model is deliberately parsimonious — symmetric firms, single sector, exogenous wages in the baseline. The authors test five extensions and the wedge survives each, but more elaborate game-theoretic structures (asymmetric firms, multi-sector demand linkages, dynamic learning) remain to be analyzed. Third, the analysis evaluates each instrument against a single margin; in practice, every instrument carries additional costs and benefits outside the model that a full welfare analysis would weigh.

These qualifications do not undermine the structural conclusion: under a broad class of competitive-market conditions, the only instrument that operates on the externality margin is a per-task automation tax, and levying it requires the measurement infrastructure that open standards make possible.

### 3.5 Relation to the Broader Automation-Economics Literature

The Falk and Tsoukalas (2026) result sits within a larger literature on automation, displacement, and tax policy. Three strands warrant explicit comparison.

**Acemoglu and Restrepo's task-based framework** (2018, 2020, 2022) decomposes the labor-market impact of automation into a *displacement effect* (tasks previously done by labor are now done by capital) and a *reinstatement effect* (new labor-intensive tasks emerge alongside automation). Their empirical work suggests that since approximately 1980 the displacement effect has dominated the reinstatement effect in the United States, and that "so-so automation" — automation that is just barely cheaper than labor while producing little productivity gain — is particularly damaging because it captures the displacement without delivering the offsetting growth. Falk and Tsoukalas's Pigouvian instrument operates on the displacement margin and is broadly compatible with the Acemoglu-Restrepo diagnosis: it raises the private cost of displacement to the social cost, leaving high-productivity automation profitable while disciplining so-so automation. The two literatures complement rather than conflict.

**Autor's polarization and skill-biased technical change framework** (Autor, Levy & Murnane 2003; Autor 2015, 2022) emphasizes that automation does not affect all labor uniformly; it particularly displaces routine cognitive and routine manual tasks while complementing both high-skill abstract work and low-skill personal-service work. The implication for AI agents is non-trivial: agent-driven automation is substantially less routine than the industrial robotics Autor's earlier work studied, and threatens to displace the high-skill cognitive work that previously appeared automation-proof. The Falk-Tsoukalas symmetric-firm model does not capture this — its single-task abstraction collapses skill heterogeneity into a single automation rate. A more elaborate model with skill-asymmetric tasks would likely increase the over-automation wedge for cognitive work, because the displaced workers in that segment have lower marginal propensity to substitute toward non-automatable jobs.

**Korinek's capital-stock framework** (Brookings, January 2026; cited in this paper's Scenario E) takes a different tack: in the presence of highly autonomous AI capital, the relevant policy instrument may shift from per-task taxation to taxation of the capital stock itself, on the grounds that the capital captures rents from accumulated training data, model weights, and deployment scope. The Falk-Tsoukalas analysis pushes back on capital-stock taxation as a primary corrective instrument, on the grounds that it scales the firm's profit function multiplicatively and cancels from the first-order condition that determines the automation rate. The two views are reconciled in this paper's Scenario E: the per-task Pigouvian tax remains the corrective instrument for the demand externality, while a capital-stock register and complementary capital-stock instruments address rent accumulation and concentration concerns. The instruments operate on different policy goals — efficiency at the margin versus distribution of accumulated returns — and a mature regime likely uses both.

The Falk and Tsoukalas formal result is therefore best read as supplying the missing piece in this literature: a clear case for which instrument operates on the demand externality margin and what rate it should be set at, given a tractable competitive-market model. It does not displace the Acemoglu-Restrepo, Autor, or Korinek frameworks; it identifies a specific argument those frameworks can build on.

A skeptical reader will note that Falk and Tsoukalas's symmetric-firm assumption is at odds with the empirical structure of the AI industry, in which roughly five hyperscalers control the foundation models on which downstream agent-deploying firms depend. In an oligopolistic input market, the hyperscalers may capture a larger share of the demand-loss externality than the symmetric model suggests, narrowing the wedge facing downstream firms. This is plausible but not yet formalized; the more elaborate models that would settle the question have not been published. For the purposes of this paper, the structural argument — that some corrective instrument is needed and that the corrective instrument requires firm-level measurement — survives any reasonable choice of model. The exact rate calibration may differ across models; the infrastructure prerequisite does not.

## 4. Six Scenarios (2026–2032)

The scenarios below vary along three axes: whether open standards adoption is mandatory, whether identity and reporting are standardized at policy level, and whether jurisdictions coordinate. They are not predictions; they are useful endpoints for thinking about which policy interventions matter when. The sequence is five primary scenarios (A, B, C, D, E) plus one pessimistic variant of B (B′, "Mandated Standards, Captured") that warrants separate treatment because the failure mode it describes is at least as plausible as B itself.

### Scenario A — Drift

**Standards posture:** Voluntary. AAIF stewards MCP and A2A. NIST publishes voluntary guidelines. Adoption is driven by enterprise interoperability needs, not regulatory compliance.

**Audit capability:** Possible but inconsistent. Logs exist where individual vendors choose to expose them. Forensic reconstruction is feasible inside a single enterprise; nearly impossible across organizational boundaries.

**Measurement:** No standardized work record. Token usage and tool-call counts serve as crude proxies. Comparisons across vendors are unreliable.

**Taxation:** No agent-specific framework. Revenue is captured indirectly through corporate income tax on AI vendors and on enterprises deploying agents. Labor's share of the federal tax base erodes meaningfully over a decade as agent substitution accelerates. Magnitude estimates vary widely across published projections and depend critically on substitution-rate assumptions, reabsorption dynamics, and tax-policy responses, none of which are settled. The qualitative direction is what matters: corporate income tax on AI vendors and on agent-deploying enterprises captures a smaller share of agent-generated value than payroll and income taxes capture from human-labor-generated value, by structural design rather than by enforcement gap.

**Outcomes:**
- *Winners (short-run):* AI platform vendors, agent-deploying enterprises, owners of capital that complements agent labor.
- *Losers:* The labor-dependent tax base, displaced workers without targeted support, small employers without the resources to deploy agents.
- *Note on the "winners" label:* Falk and Tsoukalas (2026) demonstrate that under competitive automation dynamics, agent-deploying firms are also net losers in equilibrium. Each firm captures the full cost saving from automating but bears only 1/N of the resulting demand destruction; aggregate profit falls below what coordinated restraint would produce. The label thus understates the deadweight loss: this scenario harms agent-deploying firms too, just less visibly than it harms displaced workers.

**Leading indicators we are in this scenario:** Voluntary adoption metrics dominate the conversation; no jurisdiction passes mandatory open-standards legislation by 2028; OECD does not initiate a coordinated agent-taxation working group.

**Assessment:** Moderate-to-high probability. This is the path of least resistance and reflects how digital infrastructure has historically been governed in the United States.

### Scenario B — Standards-Mandated Accountability

**Standards posture:** Open standards mandatory in regulated sectors (financial services, healthcare, government services) by 2027, broadening over time. Agent identity registration legally required, building on NCCoE and DNSid foundations. Standards bodies are effectively co-opted as quasi-regulatory infrastructure.

**Audit capability:** Strong. Verifiable agent identity combined with structured tool-call and message logs creates a forensic chain of custody. Regulators can subpoena and reconstruct agent activity with confidence.

**Measurement:** A new "agent work record" reporting standard emerges, modeled loosely on financial reporting standards such as XBRL. Reports normalize work units (tasks completed, decisions executed, principals served) across vendors. The Linux Foundation or an OECD-anchored body governs the schema.

**Taxation:** A Pigouvian automation tax is implemented at rate τ* ≈ ℓ(1 − 1/N) = (1−η)wλ(1 − 1/N) per automated task — the rate identified by Falk and Tsoukalas (2026) as the minimum required to correct the demand externality. The tax is levied on firm-level automation rates observable through the agent work record. Revenue is recycled into retraining programs that raise income-replacement rates η, shrinking ℓ and τ* in subsequent periods. Implementation is initially clumsy and contested, but the measurement infrastructure exists, and the welfare loss from imprecise targeting is second-order (the loss is quadratic in the wedge, so even an approximate rate yields a first-order gain).

**Outcomes:**
- *Winners:* Public revenue, displaced workers benefiting from redirected revenue, small AI vendors competing on a level playing field, civil society watchdogs.
- *Losers:* Hyperscalers facing initial compliance costs, agent operators that depended on opacity, jurisdictions that fail to participate.

**Leading indicators:** EU AI Act implementing regulations explicitly cite MCP/A2A by name; a major U.S. agency (likely Treasury or SEC) issues an agent-identity rule; a state passes an agent work-record reporting requirement.

**Assessment:** Moderate probability. Most likely to start in the EU, with U.S. sectoral adoption (financial services first) following. Requires sustained political will across multiple administrations.

### Scenario B′ — Mandated Standards, Captured

A pessimistic variant of Scenario B that warrants separate treatment because it is at least as plausible as B itself.

**Standards posture:** Open standards are mandated in regulated sectors as in Scenario B. But the standards-setting bodies (AAIF, OECD working groups, NIST committees) are colonized by the same hyperscalers whose behavior the standards are meant to discipline. The result is technically rigorous specifications that are operationally unhelpful for accountability — work-record schemas with optional fields where they should be required, conformance tests that vendors self-administer, identity registration that accepts shell-entity sponsors, opacity-preserving "trade secret" exemptions written into the standard.

**Audit capability:** Theatrical. Logs exist, identity records exist, work records are filed — and a determined regulator with substantial resources and litigation appetite can sometimes reconstruct what an agent did. The default state is opacity wrapped in compliance signaling. Enforcement actions are rare because building the evidentiary record is expensive and the legal standards favor the regulated parties.

**Measurement:** Technically standardized, substantively unreliable. Firms self-report into vendor-supplied schemas with vendor-supplied implementations. Cross-vendor comparison is possible in principle and unreliable in practice because each vendor's schema interpretations differ in ways that disadvantage the regulator's reconciliation effort.

**Taxation:** A Pigouvian tax is enacted but the rate is set at a fraction of τ* because the underlying measurement is too noisy to support the formal optimum. Effective collection is far below nominal — closer to a digital-services-tax-style political compromise than a corrective instrument. The deadweight loss from the externality remains; the public revenue gain is modest; the political legitimacy of the regime is contested because the formal welfare argument no longer matches the empirical implementation.

**Outcomes:**
- *Winners:* Hyperscaler legal and standards-affairs teams, regulatory consultancies, the appearance of governance.
- *Losers:* The actual welfare argument, civil society watchdogs, smaller AI vendors who lack the resources to navigate the captured standards process, displaced workers whose tax-funded transfers are smaller than the Pigouvian model envisioned.

**Leading indicators:** Standards-body chairs and rapporteurs are disproportionately drawn from hyperscaler employees and contractors; published schemas have many "should" clauses where "must" was needed; conformance testing is industry-self-administered without independent audit; the gap between nominal and effective tax collection in the first three years exceeds 60%.

**Assessment:** Moderate-to-high probability conditional on Scenario B being attempted. The structural conditions that produce capture in financial reporting (Big Four audit firm dominance, regulator resource constraints, industry expertise asymmetry) are all present in agent governance, plus an order of magnitude more technical complexity that compounds the asymmetry. The historical analog is the early-2000s financial-reporting standards process: Sarbanes-Oxley succeeded because it was preceded by an unambiguous corporate scandal (Enron, WorldCom) that mobilized political will. Agent governance does not yet have its Enron, and the standards-setting work is happening before the political pressure has accumulated.

The implication for the recommendations in Section 6 is that *which body governs the standards* matters as much as *whether they are mandated*. Recommendation 6's institutional safeguards are not optional — they are the difference between Scenario B and Scenario B′.

### Scenario C — Bifurcated Sovereign Stacks

**Standards posture:** Major economies diverge. The EU mandates open standards plus strict disclosure. The U.S. takes a light-touch, sectoral approach. China operates a parallel sovereign agent stack with state-aligned identity and surveillance characteristics. Russia, Gulf states, and others align with one bloc or maintain their own.

**Audit capability:** Jurisdictional. Strong inside compliant zones, opaque across borders. Cross-border agent activity becomes a forensic gray zone.

**Measurement:** Multiple competing frameworks. No global reconciliation. Multinational enterprises produce parallel reports for different jurisdictions, creating a compliance industry but limited substantive accountability.

**Taxation:** Each jurisdiction taxes differently. Massive arbitrage opportunities. Agents are incorporated in low-tax jurisdictions and called via API from anywhere. The problem resembles the digital services tax dispute of the late 2010s, but with an order of magnitude more economic activity at stake.

**Outcomes:**
- *Winners:* Tax havens, multi-jurisdiction agent operators, compliance consultancies.
- *Losers:* Coordination, predictability, small and middle-income economies without leverage to enforce their own rules.

**Leading indicators:** EU and China publish incompatible identity standards; OECD's pillar-style negotiations stall; a major hyperscaler announces a separate "China stack" product line.

**Assessment:** Moderate-to-high probability. Closely resembles the current trajectory of digital regulation more broadly. May be a transitional state toward either Scenario A or Scenario B over a longer horizon.

### Scenario D — Closed Vendor Capture

**Standards posture:** Open standards remain technically present but commercially marginal. Hyperscalers ship proprietary extensions to MCP and A2A that lock in dominant features. The AAIF continues to exist but its specifications lag the proprietary state of the art by 12–24 months. New entrants must build on hyperscaler stacks to remain competitive.

**Audit capability:** Mediated by vendors. Audit interfaces exist but are vendor-provided, vendor-priced, and vendor-redacted. Regulators see what vendors choose to show.

**Measurement:** Whatever the vendor reports. Cross-vendor comparison is impossible. Independent verification is impossible.

**Taxation:** Effectively impossible to tax agent activity directly. Governments fall back on corporate income tax of vendors, which gets minimized through transfer pricing and IP-routing structures. The labor tax base continues to erode with no compensating instrument.

**Outcomes:**
- *Winners:* Three to five dominant AI platform vendors. Possibly some governments that strike bilateral deals for privileged access.
- *Losers:* Public revenue, market competition, regulatory legitimacy, smaller AI vendors, civil society oversight.

**Leading indicators:** AAIF specifications stop being updated; hyperscaler-specific agent SDKs become the de facto enterprise standard; a major government issues an audit subpoena and is rebuffed on technical grounds.

**Assessment:** Low-to-moderate probability today, but rises sharply if governments fail to act during the 2026–2028 window. The proprietary alternative is always more featureful in the short run; only sustained policy preference for open standards prevents drift in this direction.

### Scenario E — Productive Capital Regime (Long-Horizon Successor)

**Standards posture:** Open standards remain mandatory, but the policy-relevant telemetry shifts. Identity registration extends to ownership chains and capital deployment. New reporting requirements focus on aggregate capital stock (model weights, fine-tuned variants, deployed instances), resource consumption (compute, energy, data), and economic output attributable to the capital — rather than task-by-task action logs alone.

**Audit capability:** Strong, but the focus changes. Audit becomes less about reconstructing individual agent actions — still possible, still required for liability purposes — and more about verifying capital ownership, deployment scope, and revenue attribution.

**Measurement:** A "capital stock register" emerges as the central reporting artifact, possibly housed under an OECD framework. Standardized units measure agent capital deployed, comparable across firms and jurisdictions. The agent work record from Scenario B persists for liability and consumer-protection purposes but is no longer the primary tax instrument.

**Taxation:** The per-task Pigouvian automation tax from Scenario B persists as the primary instrument. The Falk and Tsoukalas analysis suggests capital-stock taxation alone does not operate on the externality margin — it scales profits proportionally and cancels from the firm's first-order condition. However, a capital-stock register provides essential transparency for measurement, and capital-stock instruments may serve as complementary tools addressing rent accumulation and concentration concerns at very high autonomy levels (per the Brookings/Korinek line of argument). The combined regime taxes the marginal automation decision (Pigouvian) and the resulting capital concentration (capital-stock), recognizing that these instruments address different policy goals: efficiency at the margin versus distribution of accumulated returns. A transition-era labor-substitution levy may sunset as the capital regime matures.

**Outcomes:**
- *Winners:* Long-term fiscal stability, owners of complementary human skills, jurisdictions that successfully coordinate.
- *Losers:* AI capital owners (who bear a meaningful tax burden), arbitrage strategies that depended on labor/capital ambiguity.

**Leading indicators:** Agent autonomy benchmarks pass widely-recognized thresholds (multi-day autonomous operation, novel scientific work, sustained economic value generation without supervision); a major economy proposes a capital-stock register; OECD or G20 issues a coordinated framework on AI capital taxation.

**Assessment:** Low probability before 2030; moderate-to-high probability after 2032 if autonomy progress continues. This scenario is best understood as a successor to Scenario B rather than an alternative to it. The infrastructure built for Scenario B — open standards, identity registration, work records — remains the foundation; the tax instruments evolve as the underlying technology does. Jurisdictions that fail to build the Scenario B infrastructure will not be able to transition cleanly to Scenario E and will likely default to Scenario A or D outcomes.

## 5. Cross-Cutting Issues

### 5.1 The Taxable Unit Problem

Any agent-taxation regime must define what is taxed. Each option has distinct gaming surfaces:

- **Per-agent license fees** are simple but easily defeated by spawning many narrow agents instead of one general one.
- **Per-task taxation** requires a definition of "task" that is hard to standardize across domains.
- **Per-token taxation** taxes consumption, not output, and penalizes verbose models more than efficient ones.
- **Per-displaced-FTE taxation** is conceptually clean but requires counterfactual reasoning that is contested in court.
- **Per-revenue-attributable taxation** aligns with corporate income tax but requires apportionment between agent and human contributions to revenue.

No taxable unit is gaming-proof. A workable regime probably combines two or more, with anti-abuse rules.

### 5.2 Cross-Border Coordination

Agents are inherently borderless: model weights in one jurisdiction, inference compute in another, principal in a third, action target in a fourth. Without OECD-level coordination, jurisdiction shopping will dominate any unilateral agent tax. The lessons of the OECD's Pillar One and Pillar Two negotiations on digital taxation should be studied carefully — both for what worked and for the years lost to disagreement.

The Pillar Two architecture, which entered force across major jurisdictions in 2024–2025, offers a more useful template than Pillar One for agent governance. Pillar Two implements a 15% global minimum effective tax rate on multinational profits via a layered set of rules: the **Income Inclusion Rule (IIR)** requires the parent jurisdiction to top up tax on subsidiaries taxed below 15%; the **Undertaxed Profits Rule (UTPR)** lets jurisdictions tax the parent's residual profits when the IIR jurisdiction does not act; and the **Qualified Domestic Minimum Top-up Tax (QDMTT)** — a domestic top-up tax that meets OECD-defined criteria for "qualification" — lets the source jurisdiction collect the top-up before the parent jurisdiction can. The architecture is deliberately self-policing: a jurisdiction that fails to participate finds its multinational firms taxed by other jurisdictions instead, so the rational unilateral move is to participate at the minimum rate.

This architecture has three features that transfer well to a Pigouvian agent-tax regime.

**Layered enforcement that does not require unanimous adoption.** Pillar Two became operationally effective once a critical mass of jurisdictions adopted IIR and QDMTT (roughly 35 countries representing the bulk of multinational headquarters), even though many other jurisdictions remain nominal non-participants. An agent-tax regime can be designed similarly: if the EU, UK, U.S., Japan, and Korea adopt a common Pigouvian rate per automated task with a UTPR-equivalent backstop, jurisdictions that do not participate find their agent-deploying firms taxed elsewhere. The architecture works without the holdouts, which lowers the political bar for adoption.

**A negotiated rate with a defensible economic anchor.** Pillar Two's 15% rate is not optimized; it is a political compromise that survived because it was high enough to bite and low enough to sign. The Falk and Tsoukalas Pigouvian rate τ* ≈ ℓ(1 − 1/N) is more analytically defensible but politically harder to negotiate, because it varies by sector and over time. A workable hybrid is to adopt a fixed-rate floor (say, 5–10% of automated-task revenue, calibrated to a conservative ℓ estimate for the most automation-intensive sectors) and allow jurisdictions to top up to the formal τ* within their borders. This preserves the political simplicity of Pillar Two while leaving room for the Pigouvian welfare argument.

**Phased rollout starting with administratively tractable scope.** Pillar Two excluded firms below €750 million in global revenue, capturing the substantive base while avoiding compliance costs for small firms. An agent-tax regime can do the same: limit initial application to firms above a deployment threshold (e.g., agents handling more than 100,000 tasks per quarter, or substrate-level vendors above a stated annual-revenue floor), expanding scope as the measurement infrastructure matures.

Three features of the Pillar Two experience should be heeded as warnings.

**The negotiation took eight years.** OECD discussions on digital taxation began in 2015–2016 and the Pillar Two architecture was not finalized until 2021, with implementation continuing through 2024–2025. Cross-border agent-tax negotiations begun in 2026 should expect a 2032–2034 implementation horizon at the earliest. The Pigouvian instrument's effective deployment is therefore likely to lag the technological window by a half-decade or more — a meaningful concern given the leading-indicator timelines elsewhere in this paper.

**Pillar One stalled and may not recover.** The companion proposal — to reallocate taxing rights over the largest digital firms toward source jurisdictions — has been blocked repeatedly, most recently by U.S. Senate refusal in 2024–2025 to ratify the multilateral instrument. The lesson: arrangements that require ratification by jurisdictions whose tax base would shrink are durably hard. A Pigouvian agent tax that flows to source jurisdictions would face the same obstacle. Designing the revenue allocation to align with where the firms are headquartered, with side-payments to source jurisdictions through retraining funds or capacity-building grants, is more politically tractable than direct reallocation of taxing rights.

**Bilateral side-deals erode the architecture.** Pillar Two has been weakened in the implementation phase by bilateral exemptions, transitional safe harbors, and creative interpretations of "qualified" domestic top-up taxes (the QDMTT category). The OECD-coordinated regime is not what was negotiated; it is what survived implementation. Anticipating this in agent governance design — building anti-side-deal clauses into the multilateral instrument, requiring transparent disclosure of bilateral arrangements, vesting interpretation authority in a body insulated from individual-jurisdiction veto — is a prerequisite for the regime to function as intended over a decade or more.

The aggregate implication: cross-border coordination is not an afterthought to a domestic Pigouvian regime; it is a structural prerequisite. A jurisdiction that implements the Falk-Tsoukalas rate unilaterally without OECD coordination will see its agent-deploying firms reincorporate into low-tax jurisdictions while retaining access to the same downstream demand. The deadweight loss persists; the public-revenue gain evaporates. Recommendation 5 (OECD coordination) is therefore prior to Recommendation 4 (sectoral pilots) in dependency order, even though their nominal target dates overlap.

### 5.3 How Standards Get Gamed

Open standards can be implemented in ways that defeat audit:

- Encrypted payloads that pass through MCP servers without exposing content.
- Agents running on private infrastructure that exposes only summary telemetry.
- Identity registration that is technically compliant but practically opaque (e.g., shell entities, nested delegations).
- "Compliant" reporting that is truthful but uninformative.

Mandates must specify not just *that* standards are used, but *how* they are implemented for accountability purposes. This is closer to financial-reporting regulation than to traditional technical standards.

### 5.4 Identity as the Linchpin

If only one governance intervention is possible, mandatory verifiable agent identity is the highest-leverage choice. Audit is impossible without it. Measurement is unreliable without it. Taxation is unenforceable without it. The NCCoE concept paper, OpenID Foundation submissions, and DNSid proposal converge on this point. Governments that establish agent identity registration early will have policy options that those who delay will not.

For an illustrative specimen of what such an identity record could look like in practice — including primary identifier (UUID), W3C DID, DNSid, sponsor binding, sectoral authorization, capabilities, validity period, and the underlying JSON record — see [Appendix A](#appendix-a-specimen-agent-authority-card).

### 5.5 Drawing on Immigration Policy

Immigration policy provides the closest existing template for the audit-measure-tax-and-condition infrastructure this paper proposes for AI agents. The mechanisms involved — registration, sponsorship, sector-specific work authorization, quotas, revocation, and principal-side tax contributions — have been built, litigated, and refined over decades. Borrowing from that template is more efficient than designing analogous mechanisms from scratch.

Several specific mechanisms transfer well:

**Sponsorship and accountability binding.** Every visa-based work regime requires a sponsor who is legally accountable for the worker's compliance with the terms of admission. The agent identity work described in Section 5.4 maps directly onto this: every agent acting on behalf of a principal should have that principal as a verifiable sponsor, with attendant accountability — including for the agent's compliance with the Pigouvian tax regime, work-record reporting, and any sector-specific operating restrictions.

**Sector-specific work authorization.** Visa categories grant authorization to work in specific sectors, occupations, or even specific employers. The same approach can be applied to agents: an agent authorized to operate in financial services back-office is not automatically authorized to operate in healthcare clinical settings. This makes sectoral mandates (Recommendation 1) operationally tractable and gives regulators a fine-grained instrument that does not require shutting down agents wholesale to address sector-specific risks.

**Quotas calibrated to labor-market effects.** Immigration regimes routinely set numerical caps based on labor-market displacement concerns. The Falk and Tsoukalas framework gives a principled basis for analogous caps on agent deployment in domains where the demand externality is acute — though in most cases, a Pigouvian tax is preferable to a quota because it preserves flexibility for high-value uses while still correcting the externality. Quotas may serve as a backstop where measurement is insufficient to support precise taxation.

**Revocation and de-registration.** Visa-based regimes include mechanisms to revoke authorization for violations. The same logic applies to agent registration: agents that violate operating conditions — failing to report through the work record, exceeding authorized scope, operating without a registered principal — lose their authorization to operate. This gives the audit and identity infrastructure teeth.

**Principal-side tax contributions.** Immigration regimes often require employer-side contributions tied to the worker's presence (FICA-equivalents, training fund levies, healthcare contributions). The Pigouvian automation tax is naturally implemented as a principal-side obligation, structurally similar to employer-side payroll taxes — which makes it administrable through existing tax infrastructure rather than requiring a parallel system.

The point is structural: the legal infrastructure for governing the cross-border deployment of conditional, sponsored, sector-authorized, taxable workers already exists. Adapting it to agents is faster than building new infrastructure from scratch.

## 6. Recommendations

For governments and standards bodies seeking to align open standards with the audit-measure-tax goals:

1. **Mandate open-standards compliance for agents operating in sensitive domains by 2027.** Financial services, healthcare, and government services are natural starting points. Specify MCP and A2A by name in implementing regulations, with conformance testing.

2. **Establish mandatory agent identity registration by 2028.** Build on NIST NCCoE work, OpenID Foundation extensions, and DNSid-type DNS-anchored identifiers. Require that any agent acting on behalf of a principal be registered, with verifiable cryptographic credentials.

3. **Develop an "agent work record" reporting standard by 2029.** House the work in the Linux Foundation or a similar neutral body, with input from OECD tax authorities. Model the schema on financial reporting standards. Specify mandatory disclosure for agents operating above a size threshold. This is the measurement infrastructure that any Pigouvian instrument requires.

4. **Pilot a Pigouvian automation tax at the sectoral level by 2030, conditional on Recommendation 5 being underway.** Draw on the formal framework of Falk and Tsoukalas (2026), with rate τ* ≈ (1−η)wλ(1 − 1/N) set per automated task. Begin in highly automatable, well-measured sectors (customer support, software engineering, financial services back-office) where the agent work record is most tractable. Recycle revenue into retraining programs that raise income-replacement rates η, making the corrective instrument self-limiting. *Sequencing note:* unilateral piloting without cross-border coordination (Recommendation 5) leaks agent-deploying firms to non-participating jurisdictions and produces deadweight loss without revenue recovery. Pilots should land in jurisdictions that are also signatories to the multilateral instrument, or be designed with a UTPR-style backstop so non-coordinating jurisdictions face residual taxation by participating ones (see §5.2).

5. **Initiate OECD-level coordination on cross-border agent taxation by 2027.** Begin negotiations early; the Pillar Two experience suggests a five-to-eight-year timeline to consensus, so a 2027 start is the latest credible date for an operational regime by 2032–2034. Adopt the Pillar Two architecture (IIR + UTPR + QDMTT) as a template; design the agent-tax rate floor at 5–10% of automated-task revenue with jurisdictional top-ups to the formal Pigouvian τ*. Build anti-side-deal clauses into the multilateral instrument from the start; bilateral exemptions and creative interpretations have eroded Pillar Two and would erode an agent-tax regime faster. Recommendation 5 is prior to Recommendation 4 in dependency order even though their timelines overlap; the multilateral instrument does not need to be fully ratified before sectoral pilots begin, but it must be visibly underway.

6. **Build institutional safeguards before the technical mandates take effect.** Constitutional or legislative protections against behavior-conditional transfers; structural protections against single-vendor or single-government capture of the measurement and disbursement layers; federated administration of any household transfers; quasi-constitutional rate-setting rules analogous to central bank independence. The technical infrastructure to condition citizens on observed behavior will exist whether or not it is built deliberately; permissibility is a separate question from capability and must be decided in advance.

7. **Treat the 2026–2028 window as decisive.** The policy interventions described above are easier when standards are still being formed than after they have ossified. Governments that wait for AI-agent deployment to mature before regulating will find themselves in Scenario D — and, per the Falk and Tsoukalas analysis, will have foreclosed access to the only instrument capable of correcting the over-automation externality.

## 7. Beyond the Pigouvian Frame: Open Standards as Mechanism-Design Infrastructure

The argument developed across Sections 2–6 is narrow: a specific protocol stack enables specific accountability goals, and one specific instrument — a Pigouvian automation tax — formally corrects a specific externality. That narrow argument is technically defensible. But it underdescribes what is actually being built.

### 7.1 The Pattern: Strategic Interaction Becomes a Tradeable Object

The standards stack does not merely make agent activity auditable, measurable, and taxable. It makes *strategic positions observable in real time*. Once observable, those positions become priceable. Once priceable, they become marketable, taxable, hedgeable, and conditionable.

Game theory has always existed. What changes with agent identity, work records, and structured cross-firm telemetry is that the inputs to mechanism-design problems become routinely available rather than estimable. Falk and Tsoukalas wrote the recipe for one dish — corrective taxation of automation. The kitchen this paper has been describing serves a much larger menu: real-time externality correction across any measurable spillover, dynamic insurance and hedging for previously unbearable risks, faster market clearing because strategic positions are transparent, and inexpensive coordination of public goods that previously required costly negotiation.

In the optimistic frame, this is the operationalization of welfare economics: Pareto improvements that have been theoretically available since Pigou become practically tractable. The pessimistic frame is the same pattern from the other side — *whoever owns the measurement layer captures the meta-game*.

### 7.2 Three Asymmetries

Three structural asymmetries warrant explicit attention because they recur across applications of the substrate.

**Strategic-actor asymmetry.** Game theory works on strategic actors; citizens are not uniformly strategic actors. A system designed for profit-maximizing firms can produce perverse outcomes when extended to populations whose decision-making does not match the model. UBI recipients, voters, patients, students — treating them as expected-utility maximizers is often wrong, and the gap between the model and the population is where unintended consequences live. The Pigouvian tax targets firms, where the assumption is most defensible; extension of mechanism-design governance to other domains carries this risk.

**Measurement asymmetry.** What gets measured shapes what gets played. If the tax is on automation rates, firms optimize automation rates. If the metric becomes "agent productivity," firms optimize productivity. Goodhart's Law at industrial scale. The choice of *what* to measure is itself a policy choice with first-order welfare consequences, and is rarely subject to the same democratic scrutiny as the choice of *how much* to tax.

**Velocity asymmetry.** If the state can adjust the Pigouvian rate continuously based on observed equilibrium, but legislative scrutiny operates on multi-year cycles, operational rules drift away from legitimating rules. This is already contested in monetary policy; agent infrastructure extends the same dynamic across labor, public services, and potentially political behavior. The legitimacy properties of governance-by-mechanism-design at this speed are barely-thought-through.

### 7.3 The Distribution Layer and the Dependency Problem

A separate concern attaches to what is done with the proceeds. UBI funded by automation tax has been raised throughout this paper as one option for revenue allocation. The formal model treats this as a redistribution question — efficiency at the margin is settled by the tax rate; distribution is downstream — but the political economy is not separable in practice.

When a meaningful share of the population's livelihood depends on a government distribution, the citizen-state relationship inverts. Historically, the state extracted resources from citizens, and citizens used the threat of withdrawal as leverage. UBI funded by automation tax flips this: the state distributes resources, and the citizen's economic leverage shrinks because withdrawing labor is no longer economically meaningful. This is structural, not partisan.

Several cascading effects follow:

- **Voice and dissent.** Self-censorship attaches to the entity that pays you. When that entity is the state, political speech is affected — even without malign intent, simply through anticipated risk on the recipient's side.
- **Conditioning creep.** The infrastructure to deliver high-resolution UBI is the same infrastructure required to condition it. Today's universal transfer is one administrative rule from tomorrow's behavior-conditional one.
- **Intermediary collapse.** Mutual aid societies, unions, religious organizations, professional associations, and extended families have historically buffered the citizen-state relationship and provided alternative economic security. A society where the state is the primary economic intermediary has less of this connective tissue, which has historically been a precondition for democratic resilience.
- **Citizenship as financial asset.** If transfers are generous and citizenship-conditioned, citizenship gains a clear monetary value. Border politics and naturalization regimes intensify accordingly.
- **Capture risk.** Whoever controls disbursement holds enormous leverage; the disbursement authority becomes a high-value target for political capture, adversarial cyberattack, or legislative manipulation in narrow electoral windows.
- **Fiscal dependency.** The Pigouvian rate is partly self-limiting: as η rises, ℓ falls, τ* falls, revenue falls. Transfer programs that scale with the tax base inherit this dynamic, exposing recipients to structural revenue risk.
- **Identity and meaning effects.** Distinct from the economic argument: work provides structure, social ties, identity, and a sense of contribution. The evidence on whether transfer income substitutes adequately for these functions is contested.

The same infrastructure that enables the Pigouvian instrument enables a high-resolution conditional regime. The infrastructure itself is neutral; the policy choices around it determine which obtains.

### 7.4 Design Implications

These observations do not invalidate the white paper's argument. They sharpen what it is actually arguing for. *Open standards are not interchangeable with mandatory standards generally.* The case for *open* is much stronger under the mechanism-design framing than under the narrower audit-measure-tax framing.

Under the narrow framing, a hyperscaler-controlled accountability stack might be tolerable: the goal is just measurement, and the measurer's identity matters less than the existence of measurement. Under the mechanism-design framing, the measurer's identity is decisive. Closed, vendor-controlled stacks (Scenario D) cede control of the meta-game to whichever vendor or government holds the stack. The dependency concern is dramatically greater under D than under B.

Several design choices follow:

**Genuinely open governance.** Specifications, conformance tests, and identity registries should be governed by neutral bodies (Linux Foundation, OECD, ISO) with structural protections against single-vendor or single-government capture. The Agentic AI Foundation is a reasonable starting structure; mandates should specify it or its functional equivalents, not vendor-specific implementations.

**Federated administration.** Disbursement of any tax revenue, particularly when used for transfers to households, should be administered through multiple jurisdictions or institutions rather than concentrated in a single agency. Single-point-of-failure capture risk is real; redundancy reduces it.

**In-kind components.** Revenue allocation should include guaranteed access to housing, healthcare, education, and similar in-kind provisions alongside any cash component. In-kind provisions are harder to weaponize as political leverage than cash flow.

**Quasi-constitutional disbursement rules.** Where cash transfers form a substantial share of household income, the rate-setting and eligibility rules should be insulated from routine political adjustment, analogous to central bank independence. Not a panacea — central bank independence is itself contested — but it raises the cost of capture.

**Preserving exit options.** A population that could work has more leverage than one that structurally cannot. This argues for prioritizing retraining-into-real-jobs revenue allocation while reabsorption is plausible, and shifting to transfer-heavy allocation only as the share of structurally non-automatable work shrinks. The mix should be empirically calibrated to actual reabsorption rates rather than ideologically chosen in advance.

**Constitutional constraints on conditioning.** The legal and constitutional infrastructure to *prohibit* behavior-conditional transfers — to make conditioning illegal regardless of which government is in power — is more important than the technical infrastructure. The technical capability to condition will exist; the question is whether using it is permissible.

## 8. The Honest Frame

The argument of this paper, fully stated, is this: AI agent infrastructure enables an emerging mechanism-design substrate for governance and commerce. Open standards make this substrate accessible to public-interest applications, including the Pigouvian instrument that Falk and Tsoukalas formally justify. Closed standards cede the substrate to private rent extraction. Either way, the substrate is being built, and the choice is who controls it.

Within that substrate, the Pigouvian automation tax is the right corrective for the labor-displacement externality. But the proceeds of that tax — and more broadly, every governance decision the substrate enables — sit at the intersection of economic efficiency and political legitimacy. The formal models can settle the first; they cannot settle the second.

The recommendations in Section 6 should therefore be read as the floor of a much larger governance challenge. Mandating open standards, registering agent identity, building agent work records, levying the corrective tax — all of this is necessary; none of it is sufficient. The harder work, which this paper does not attempt to resolve, is constructing the political institutions that prevent the substrate from becoming an instrument of dependency, conditioning, or capture. That work belongs to constitutional law, democratic theory, and political economy more broadly.

What this paper claims is narrower: the technical and economic foundation for those harder questions is being laid right now, in standards bodies and AI labs, with little visibility from the institutions that will eventually have to govern its use. The 2026–2030 window is when those foundations get poured. After that, retrofit is much harder.

The core argument is narrow in its premise and broad in its consequence: the standards exist; the policy mandates do not; the political institutions that will govern what the standards make possible are not yet in view. Anchoring agent governance in open standards is the right instinct. Building the political institutions to govern the substrate that open standards create is the larger task — and the one this paper hopes to help start.

## References

- Acemoglu, D. & Restrepo, P. (2018). The Race Between Man and Machine: Implications of Technology for Growth, Factor Shares, and Employment. *American Economic Review*, 108(6), 1488–1542.
- Acemoglu, D. & Restrepo, P. (2019). The Wrong Kind of AI? Artificial Intelligence and the Future of Labor Demand. *NBER Working Paper No. 25682*.
- Acemoglu, D. & Restrepo, P. (2020). Robots and Jobs: Evidence from US Labor Markets. *Journal of Political Economy*, 128(6), 2188–2244.
- Acemoglu, D. & Restrepo, P. (2022). Tasks, Automation, and the Rise in U.S. Wage Inequality. *Econometrica*, 90(5), 1973–2016.
- Anthropic (2024). *Introducing the Model Context Protocol.* Anthropic.
- Anthropic (December 2025). *Donation of MCP to the Linux Foundation; co-founding of the Agentic AI Foundation.*
- Autor, D., Levy, F. & Murnane, R. J. (2003). The Skill Content of Recent Technological Change: An Empirical Exploration. *Quarterly Journal of Economics*, 118(4), 1279–1333.
- Autor, D. (2015). Why Are There Still So Many Jobs? The History and Future of Workplace Automation. *Journal of Economic Perspectives*, 29(3), 3–30.
- Autor, D. (2022). The Labor Market Impacts of Technological Change: From Unbridled Enthusiasm to Qualified Optimism to Vast Uncertainty. *NBER Working Paper No. 30074*.
- Brookings Institution / Korinek, A. et al. (January 2026). *The future of tax policy: A public finance framework for the age of AI.* Brookings working paper.
- *CIO Dive* (December 10, 2025). Big tech takes steps to build open standards for agentic AI.
- CopilotKit (early 2026). *AG-UI specification.*
- Falk, B. H. & Tsoukalas, G. (March 2026). *The AI Layoff Trap.* arXiv:2603.20617v1 [econ.TH]. University of Pennsylvania and Boston University.
- Google (April 2025). *The Agent-to-Agent Protocol specification.*
- Identity Digital (April 27, 2026). *DNSid: A neutral, DNS-anchored identity standard for AI agents.*
- Kelly, M. (2025). *AI for America proposal.*
- Linux Foundation (December 2025). *Agentic AI Foundation launch announcement.*
- NIST CAISI (February 17, 2026). *AI Agent Standards Initiative announcement.*
- NIST NCCoE (February 2026). *Concept paper: Accelerating the Adoption of Software and AI Agent Identity and Authorization.*
- OECD (2021). *Statement on a Two-Pillar Solution to Address the Tax Challenges Arising from the Digitalisation of the Economy.* OECD/G20 Inclusive Framework on BEPS.
- OECD (2023). *Pillar Two GloBE Rules: Administrative Guidance.* OECD/G20 Inclusive Framework on BEPS.
- Sanders, B. (2025). *Report on automation and the U.S. labor market.*
- Tax Foundation (February 2026). *AI tax policy considerations.*
- Zed (August 2025). *Agent Client Protocol specification.*

*This white paper is intended as a discussion document for policy, standards, and enterprise audiences. Scenarios are analytic constructs, not predictions.*

## Appendix A: Specimen Agent Authority Card

The following two pages illustrate what a verifiable agent identity record could look like in practice. The form is illustrative — no authority called "AAIF" issues real agent credentials, and the cryptographic values shown are placeholders. The structure follows the proposals catalogued in Sections 5.4 and 5.5: a primary UUID identifier, alternative formats (W3C DID, DNSid), sponsor binding, sectoral authorization, explicit capabilities, validity period, machine-readable identification strip, and a complete JSON identity record suitable for programmatic verification.

Two specimens are shown. The first demonstrates a financial-services agent with a one-year validity and three authorized capabilities (read, execute-tools, agent-to-agent communication). The second demonstrates how the same form supports sector-specific restriction: a healthcare agent with a 90-day validity authorized for read-only access. The contrast shows how the same registration infrastructure expresses very different operating scopes.

The visual aesthetic is deliberately document-like — drawing on the rhetorical machinery of immigration policy (sponsorship, sectoral authorization, validity dating, revocability) per the discussion in Section 5.5.

**Companion artifact.** An interactive React component generating these specimens is available alongside the white paper. It allows arbitrary principal, sector, capability, and validity combinations and outputs the full JSON identity record for any configuration.

*[Specimen pages follow — see attached PDF (`agent-authority-card-specimen.pdf`).]*
