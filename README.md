---
name: "Tenable Process Inspector - Plugin 70329 "
author: "rafansmpj"
github_url: "https://github.com/rafansmpj/tenable-process-inspector"
description: "Win Process Inspector PlugIn 70329"
license: "MIT"
tier: "unreviewed"
integrations: ["Tenable"]
date_added: 2026-07-01
compatible_platforms: ["Claude Desktop"]
invocation: "tenable-process-inspector"
---

Generates an interactive Windows process analysis dashboard using Plugin 70329 (Microsoft Windows Process Information) via Hexa AI - Tenable MCP

## What it does

Generates an interactive Windows process analysis dashboard using Plugin 70329 (Microsoft Windows Process Information) via Tenable MCP. Use this skill whenever the user asks about: running processes, process lists, process inspection, suspicious processes, process anomalies, process-based threat hunting, process-based attack paths, process-based lateral movement, process enumeration, process auditing, process inventory, programs running on hosts, process security analysis, or process masquerading. The skill collects Plugin 70329 output from all Windows assets, parses the process tree, detects suspicious activity using heuristics (high-privilege SIDs, process masquerading, hacking tools, C2), maps MITRE ATT&CK techniques, and delivers a dashboard featuring a per-host Process Explorer, a cross-host suspicious process table, attack path analysis, and a threat hunting playbook.

## Quick Start (5 minutes)

### 1. Prerequisites

- Claude Code (or another Claude environment with skills support) installed locally.
- A Tenable One MCP server connected and authenticated, this is what provides live Exposure Score, vulnerability findings, Crown Jewels, and attack path chokepoint data. Without it, the skill falls back to a "DEMO — illustrative data" mock dashboard.
- The MCP connection needs read access to: Exposure View (score, domain notes, industry benchmark), Findings/Vulnerabilities (VPR, severity, affected assets), Crown Jewels list, and Attack Path graph (for chokepoint identification).
- An environment capable of rendering the resulting React/HTML artifact (Claude.ai or Claude Code's artifact viewer).

### 2. Installation

Copy the skill folder into the local Claude Code skills directory:

~/.claude/skills/tenable-process-inspector/

### 3. Configure

- Make sure the Tenable One HEXA AI MCP connector is set up and active in the same Claude environment (this is the one external dependency; everything else, like the color palette, phase logic, and scoring weights, is hardcoded in SKILL.md).
- Optionally, set organizational context the skill will use when invoked: industry/sector (for benchmark comparison), language preference (English/Portuguese), and any default filters (e.g., always focus on Crown Jewels, or always include regulatory mapping like LGPD/ISO 27001/NIST CSF/PCI-DSS).
- No API keys or .env files are needed inside the skill itself — credentials live entirely in the MCP connector configuration, not in the skill folder.
