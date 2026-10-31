# Awesome-SAAS-Security-Posture-Management-SSPM

# Top SaaS Security Posture Management (SSPM) Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Configuration Hardening, Identity Risk & Self-Hosted Posture Auditing*  
**Last updated: November 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **SaaS Security Posture Management (SSPM)**. These tools enable security teams to continuously monitor SaaS application configurations, detect misconfigurations and identity risks, enforce least privilege, and maintain compliance—closing the visibility gap that traditional CASB, IdP, and endpoint tools leave inside third-party SaaS applications.

**Examples** include CrowdStrike Falcon Shield (with Adaptive Shield), AppOmni, Obsidian Security, Palo Alto SaaS Security, Wing Security, Valence Security, DoControl, Microsoft Defender for Cloud Apps, and Netskope SSPM (the category leaders).

**Open-source emphasis**: SSPM is a domain where open-source tooling is **severely limited and explicitly acknowledged as such**. A 2026 practitioner guide states plainly: **"There is no open-source SSPM"** . The closest active projects are **ElectricEye** (a multi-cloud, multi-SaaS Python CLI for posture management and attack surface monitoring with controls mapped to 20+ frameworks) , **ClosedSSPM** (a read-only SSPM CLI starting with ServiceNow coverage, Apache-2.0) , and **open-sspm** (a small "who has access to what" service syncing identities from Okta and permissions from GitHub, Datadog, and AWS Identity Center) . The critical caveat: **none match the 150–180+ app coverage, automated remediation, or unified identity-to-device correlation** of commercial SSPM platforms. Organizations requiring enterprise SSPM should evaluate commercial tools; those with narrow, specific needs (ServiceNow, multi-cloud config auditing) can use open-source CLIs as a starting point.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[CrowdStrike Falcon Shield (with Adaptive Shield)](https://www.crowdstrike.com/)**  
  The market-leading SSPM, formed by CrowdStrike's acquisition of Adaptive Shield (November 2024) and integration into Falcon Shield . Named the Leader in the 2024 Frost Radar SSPM report (Innovation 4.8/5, Growth 4.5/5) . Features: **3,500+ security checks across 180+ SaaS apps**, identity-first threat detection (ITDR) correlating SaaS activity with on-premises identity behavior via Falcon Identity Protection and Falcon Score, device-to-SaaS-user posture correlation, AI agent discovery and containment, shadow app detection, and automated remediation . **Best for organizations wanting the most complete SSPM** with endpoint-to-SaaS correlation—but it is a premium enterprise platform.

- **[AppOmni](https://appomni.com/)**  
  SSPM platform focused on deep configuration visibility across major SaaS apps (Salesforce, Workday, M365, NetSuite); Sprinklr case study reports remediation time reduced from weeks to hours with continuous monitoring and actionable findings . FedRAMP authorized for government use . **Best for organizations wanting deep, API-based posture management** for core enterprise SaaS.

- **[Obsidian Security](https://www.obsidiansecurity.com/)**  
  Next-gen SSPM with three modules: **Integration Risk Management** (maps interconnections between apps, permissions, and activity to reduce integration risk by 80%), **Obsidian Extend** (monitors niche and custom-built SaaS apps beyond the mainstream), and **Compliance Posture Management** (automates mapping to SOC 2, NIST 800-53, ISO 27001, CSA CCM) . **Best for organizations needing third-party integration risk visibility and niche app coverage**—the integration risk angle is a differentiator.

- **[Palo Alto SaaS Security](https://www.paloaltonetworks.com/)**  
  SSPM within Palo Alto's SASE platform; collaborates with NGFW administrators to create SaaS policy rule recommendations for blocking unsanctioned app activity, with tenant-level granularity for some apps (e.g., blocking downloads from Box for specific tenants) . **Best for organizations standardized on Palo Alto NGFW** wanting inline enforcement alongside posture management.

- **[Wing Security](https://wing.security/)**  
  SSPM focused on misconfiguration policies (SCuBA framework-based), identity access controls, UEBA, compliance audit trails, tailored threat intelligence, and remediation workflows including bulk OAuth revocation . **Best for mid-market organizations** wanting practical SSPM with remediation playbooks.

- **[Valence Security](https://www.valencesecurity.com/)**  
  SaaS and AI security platform covering SSPM, ITDR, SaaS discovery, and **AI security/governance** (shadow AI, AI integrations, built-in AI features) . **Best for organizations prioritizing AI-era SaaS risk** alongside traditional posture management.

- **[DoControl](https://www.docontrol.io/)**  
  SSPM expanding into comprehensive configuration drift management with **200+ SaaS integrations**, built-in compliance frameworks (NIST, ISO, SOC 2, CIS), and AI-powered custom framework/application support . **Best for organizations where configuration drift is the primary concern** and data access governance matters.

- **[Microsoft Defender for Cloud Apps](https://learn.microsoft.com/)**  
  SSPM within Microsoft's Defender suite; assesses discovered apps against **90+ risk indicators**, surfaces misconfigurations with recommended actions based on CIS benchmarks and app-provider best practices, and feeds SSPM data into **Microsoft Secure Score** . **Best for Microsoft 365-centric organizations** wanting SSPM without a separate vendor.

- **[Netskope SSPM](https://www.netskope.com/)**  
  SSPM integrated into Netskope's SASE/CASB platform; features **graph-based detection and visualization** with cross-app rules correlating context across SaaS applications to reveal hidden risks, guided remediation, custom rules, and API integrations with SIEM/SOAR and Snowflake/Jira . **Best for organizations standardized on Netskope** wanting SSPM within a unified SASE console.

## Open-Source GitHub Projects

### Multi-Cloud & Multi-SaaS Posture CLIs

- **[ElectricEye](https://github.com/jonrau1/ElectricEye)**  
  The **most established open-source posture management CLI** for multi-cloud and multi-SaaS environments (~1k GitHub stars, Python) . Features: **asset management, security posture management, and attack surface monitoring** across 100s of services; controls mapped to **20+ industry, regulatory, and best-practice frameworks**; CLI-driven for CI/CD integration . **Critical caveat**: a 2026 practitioner guide notes **ScoutSuite (a sibling tool) has been unmaintained since May 2024** while remaining on recommendation lists—**verify ElectricEye's maintenance cadence before relying on it** . **Best for teams wanting a scriptable, multi-framework posture scanner** as a starting point—not a turnkey SSPM platform.

### SaaS-Specific Posture Auditing

- **[ClosedSSPM](https://github.com/PiotrMackowski/ClosedSSPM)**  
  Open-source **SaaS Security Posture Management CLI** (Apache-2.0, Go) . **Read-only**—never writes to your SaaS platform; uses dedicated audit credentials (e.g., ServiceNow `itil` and `security_admin` read-only roles) . Features: **YAML-based custom policies** organized by platform; **SARIF output** importable into DefectDojo for centralized vulnerability management; **MCP server** (stdio transport only, no network exposure) for AI agent access to findings . **Current coverage**: **starts with ServiceNow**—coverage is being expanded platform by platform . **Best for ServiceNow administrators** wanting a focused, auditable posture check—but it is **not a broad SSPM platform** (no Salesforce, M365, or Workday coverage yet).

- **[open-sspm](https://github.com/open-sspm/open-sspm)**  
  Open-source **"who has access to what" service** (MIT, Go) . Syncs identities from **Okta (IdP)** and permissions from connected apps (**GitHub, Datadog, AWS Identity Center**) to surface access visibility. **Best for small teams** wanting a lightweight access-mapping tool—but it is **identity-access-focused**, not configuration posture management, and covers only a few integrations.

### Additional Strong Open-Source Options

- **ScoutSuite** — Multi-cloud security auditing tool; **unmaintained since May 2024** . **Do not adopt for new projects**—listed only to warn against outdated recommendation lists.
- **Steampipe** — Universal SQL interface to APIs (including SaaS); can query cloud and SaaS configurations for custom posture checks . **Infrastructure layer**—not an SSPM product, but useful for building custom checks.
- **forter/security-101-for-saas-startups** — Comprehensive guides and checklists for securing SaaS infrastructure and operations; not a tool, but **practical security guidance** for startups without dedicated security teams .

**Frameworks for building custom systems**: **ClosedSSPM** provides a read-only, auditable CLI for ServiceNow posture checks with SARIF/DefectDojo integration . **ElectricEye** provides a multi-cloud/multi-SaaS posture scanner with 20+ framework mappings (verify maintenance) . **open-sspm** provides Okta-to-app access visibility . **No open-source project provides the 150+ app coverage, automated remediation, or identity-to-device correlation** of CrowdStrike Falcon Shield, AppOmni, or Obsidian—organizations requiring enterprise SSPM should evaluate commercial platforms. A 2026 practitioner guide confirms: **"There is no open-source SSPM"** .

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- SSPM platforms handling SaaS configuration and identity data must comply with organizational security policies and privacy regulations; **audit credentials should be read-only and scoped to the minimum necessary permissions**—ClosedSSPM explicitly recommends read-only ServiceNow roles .
- **Open-source SSPM is explicitly acknowledged as non-existent**—a 2026 practitioner guide states **"There is no open-source SSPM"** and warns that **ScoutSuite has been unmaintained since May 2024** despite appearing on recommendation lists . **ClosedSSPM** provides a focused ServiceNow audit CLI , **ElectricEye** provides multi-cloud posture scanning (verify maintenance) , and **open-sspm** provides Okta-to-app access visibility . **None match the commercial platforms' app coverage, automated remediation, or unified identity-device correlation**—organizations requiring enterprise SSPM should evaluate CrowdStrike Falcon Shield, AppOmni, Obsidian, or other commercial tools.
- Verify license terms for commercial use; ClosedSSPM uses Apache-2.0 , open-sspm uses MIT , and ElectricEye is open-source (check repository) .

---

**Made for security architects, SaaS administrators, and teams building posture management capabilities.**  
Let's make SSPM more open, but with clear eyes about the explicit gap that practitioners acknowledge—there is no open-source SSPM today.
