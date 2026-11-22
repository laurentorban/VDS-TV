# VDS-TV

**Cisco Videoscape Distribution Suite — Operational Toolkit**

A collection of Bash scripts developed while working at the Cisco Technical Assistance Center (TAC) in Belgium, within the Video Team.

VDS-TV was created to assist with troubleshooting and operational diagnostics of Cisco's Arroyo / Videoscape Distribution Suite (VDS) video distribution platform.

This repository preserves some of the tooling developed during that period, approximately 2015.

## Background

The Cisco Videoscape ecosystem involved multiple components working together to deliver and manage video content across distributed infrastructure.

Working at the Cisco TAC meant troubleshooting complex customer environments across the Videoscape platform, with a particular specialisation in VDS-TV.

The scripts in this repository were written to automate repetitive diagnostic tasks, collect information from remote systems and make troubleshooting more efficient.

Rather than manually connecting to individual servers, retrieving logs and checking hardware or database status, the toolkit provided a way to gather operational information across multiple systems.

## What it does

The scripts cover several areas of VDS operational diagnostics:

| Area | Purpose |
|---|---|
| Evaluators | Remote evaluator availability, status and protocol-timing checks |
| Video assets | Asset-related information and diagnostic log collection |
| Database / NSD | Database content counts, NSD status and related log diagnostics |
| Hardware | RAID event logs, battery status, firmware information and machine-check exception (MCE) diagnostics |
| Remote operations | SSH-based command execution, information retrieval and file transfer |

## Scripts

| Script | Description |
|---|---|
| `check.sh` | General operational checks across evaluator systems, including protocol timing, content counts and selected hardware information |
| `checkAsset.sh` | Asset-related diagnostics, including content counts and relevant log information |
| `checkDatabase.sh` | Database and NSD diagnostics, including server status, backlog information and network checks |
| `checkEvaluator.sh` | Evaluator status and configuration information collected from protocol-timing logs |
| `checkHardware_1.0.sh` | Hardware diagnostics, including MegaRAID event logs, battery condition, firmware and MCE information |
| `expectTest.sh` | Small Expect-based test for retrieving a database content count through an interactive SSH session |
| `putonftp.sh` | Legacy FTP file-transfer helper |
| `256.sh` | Small terminal-colour experiment; the current script exits before reaching its palette output |

The scripts were designed around the operational environment and infrastructure available at the time.

## Implementation

The toolkit is primarily written in Bash and uses standard Unix/Linux utilities.

Remote diagnostics rely heavily on SSH, allowing commands and information retrieval to be performed across distributed evaluator systems.

Some scripts also use tools such as `expect`, hardware-management utilities and database-related commands.

The implementation reflects the practical requirements of production troubleshooting: remote access, command automation, timeouts, logging and quick access to diagnostic information.

## Historical archive and security warning

This is a historical engineering project, preserved in its original form.

The scripts date primarily from 2015 and reflect the infrastructure, software versions, operational practices and security assumptions of that period.

**They are not intended to be deployed as-is in modern environments.**

In particular:

- SSH access and privilege assumptions should be reviewed.
- Some scripts disable SSH host-key verification.
- FTP and other authentication/configuration assumptions are outdated and must be reviewed.
- Paths, server configurations and system dependencies are environment-specific.
- Some external utilities and commands may no longer be available.

Do not run these scripts against production systems without first reviewing every command and adapting the environment-specific settings.

The original scripts are intentionally preserved rather than rewritten simply to conform to modern conventions.

## Why this repository is preserved

VDS-TV represents a small part of the operational engineering work performed in the Cisco Video Team.

It documents practical troubleshooting techniques, automation patterns and the operational knowledge accumulated while supporting a complex distributed video delivery platform.

It also serves as a personal technical reference: a starting point for revisiting Bash-based operational automation when needed.

---

**Status:** Archived / Historical  
**Original environment:** Cisco TAC, Video Team, Belgium  
**Platform:** Arroyo / Cisco Videoscape Distribution Suite (VDS)  
**Language:** Bash  
**Approximate period:** 2015
