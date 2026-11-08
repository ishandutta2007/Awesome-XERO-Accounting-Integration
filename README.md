# Awesome-XERO-Accounting-Integration

# Awesome Xero Accounting Integration

> A curated list of top Xero Accounting Integration platforms — both SaaS/Hosted commercial connectors and open-source tools, SDKs, and self-hosted alternatives for syncing financial data with Xero.  
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Chargebee](#chargebee)
  - [Zapier](#zapier)
  - [Make](#make)
  - [Celigo](#celigo)
  - [OneSaas](#onesaas)
  - [Dataddo](#dataddo)
  - [Fivetran](#fivetran)
  - [Stitch](#stitch)
  - [Workato](#workato)
- [Open-Source Software](#-open-source-software)
  - [Activepieces](#activepieces)
  - [LedgerSync](#ledgersync)
  - [dubbl](#dubbl)
  - [Bigcapital](#bigcapital)
  - [TPT OpenLedger](#tpt-openledger)
  - [baton-xero](#baton-xero)
  - [Xero Official SDKs](#xero-official-sdks)
  - [Airbyte Xero Source](#airbyte-xero-source)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Xero integration platforms. These are not open-source but are included as reference points for feature comparison.

### Chargebee
**Type:** Subscription billing and invoicing sync  
Chargebee's native Xero integration automates subscription accounting by syncing invoices and related details to Xero. It handles customers, plans, addons, coupons, discounts, multi-currency invoices, credit notes, payments, refunds, taxes, and one-time charges [citation:1]. Chart of Accounts mapping lets you map plans and addons to individual Xero accounts, including payments, refunds, round-offs, bad debts, and discounts. Sync can run automatically or on demand, and the integration supports tax rate mapping for New Zealand, Australia, UK, South Africa, and Singapore [citation:1].  
**Best for:** Subscription businesses using Chargebee for recurring billing that need automated invoice and payment sync to Xero.

### Zapier
**Type:** General-purpose automation platform  
Zapier connects Xero to 7,000+ apps with triggers and actions covering invoices, contacts, payments, credit notes, bank transactions, purchase orders, and reports [citation:2][citation:13]. Available triggers include New Payment, New Invoice, Updated Sales Invoice, and Overdue Sales Invoice. Actions include Create Invoice, Create Contact, Create Payment, and Create Bill [citation:2]. **Limitations:** Xero is a premium app requiring a paid Zapier plan; Xero API rate limits apply (60 calls/minute per tenant, 5,000/day per tenant); the Projects API is not directly supported [citation:2].  
**Best for:** Teams wanting no-code automation between Xero and arbitrary SaaS tools without dedicated integration development.

### Make
**Type:** Visual automation platform  
Make provides Xero modules covering accounts, bank transfers, bank transactions, contacts, credit notes, employees, invoices, items, journal manuals, payments, purchase orders, tax rates, and more [citation:3][citation:14]. Scenarios can be triggered by webhooks (instant) or scheduled watches on invoices, contacts, bank transactions, and other entities. **Note:** Xero enforces volume threshold limits on GET endpoints, which can slow high-volume searches [citation:3].  
**Best for:** Teams wanting visual, multi-step automation workflows with granular control over Xero data operations.

### Celigo
**Type:** Integration platform for SaaS and e-commerce  
Celigo's integrator.io supports Xero connections via OAuth2. Configuration requires setting up the OAuth2 connection with the correct Xero base URI for token acquisition [citation:4]. Celigo is positioned as a general-purpose iPaaS suitable for finance-specific workflows when configured carefully, though users must own the accuracy of edge cases like part payments, credit notes, and multi-currency [citation:15].  
**Best for:** NetSuite and e-commerce ecosystems needing Xero connections alongside broader SaaS integration workflows.

### OneSaas
**Type:** Accounting automation hub  
OneSaas provides a "hub and spoke" integration model connecting e-commerce platforms, point-of-sale systems, billing, CRM, and fulfillment tools with accounting systems including Xero [citation:5]. Designed for merchants who want automated financial data sharing between their online store and Xero without technical knowledge.  
**Best for:** E-commerce merchants wanting automated sales data sync to Xero through a managed integration hub.

### Dataddo
**Type:** Managed data pipeline to warehouses and BI  
Dataddo extracts the full Xero record model — invoices, transactions, payments, ledger and tax fields — and delivers it to Snowflake, BigQuery, BI dashboards, AI tools, and back to ERP/CRM systems [citation:7]. Features include incremental scheduled syncs (as often as hourly), full history backfill beyond Xero's export limits, currency/tax normalization, and a Data Quality Firewall. Data residency can be pinned to EU or US regions, or self-hosted when required [citation:7].  
**Best for:** Finance teams needing governed, scheduled Xero data delivery to a data warehouse for consolidated reporting and analytics.

### Fivetran
**Type:** Automated data pipeline connector  
Fivetran's Xero connector supports custom connection authentication (recommended for AU, NZ, GB, US organizations) and web app authentication for other regions. It syncs accounting settings, transactions, contacts, journals, budgets, payroll data, and assets [citation:8]. A webhook can be configured to capture invoice table updates. **Prerequisites:** Adviser or Standard user role; Advanced or Enterprise plan for Journals endpoint; Custom Connection subscription [citation:8].  
**Best for:** Organizations already using Fivetran for ELT pipelines wanting managed Xero data replication to a warehouse.

### Stitch
**Type:** Data pipeline with incremental replication  
Stitch replicates Xero data incrementally into a data warehouse, covering accounts, bank transactions, contacts, credit notes, invoices, journals, manual journals, organisation settings, payments, purchase orders, receipts, repeating invoices, tax rates, and tracking categories [citation:9]. Tables include nested structures for line items and contact details.  
**Best for:** Teams using Stitch for SaaS data ingestion wanting Xero financial data in their warehouse for analysis.

### Workato
**Type:** Enterprise automation with Xero connector  
Workato provides 150+ pre-built Xero triggers and actions covering credit notes, items, overpayments, prepayments, accounts, bills, contacts, employees, invoices, payments, bank transactions, manual journals, purchase orders, and more [citation:10]. Custom actions and batch operations (List/Search) are supported. Custom Connections are available via HTTP connector [citation:10].  
**Best for:** Enterprises wanting a mature automation platform with deep Xero action coverage and custom workflow capabilities.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Xero integration tools, SDKs, and open-source accounting alternatives. All listed projects offer source code you can deploy or build upon.

### Activepieces
**Stack:** TypeScript | **License:** MIT  
An open-source automation platform (self-hostable or cloud) with an open-source Xero piece included on every plan. Provides triggers for New Contact and New or Updated Contact via Xero webhooks [citation:23]. The Xero integration can be combined with 760+ other apps in flows, and recent PRs add AI actions, reports, and expanded invoice tools [citation:26]. Because the piece is MIT-licensed, you can audit, modify, and self-host the entire automation stack.  
**Best for:** Teams wanting open-source, self-hostable automation with Xero connectivity and no per-task pricing.

### LedgerSync
**Stack:** Ruby | **License:** Open Source (per repository)  
An open-source Ruby gem for syncing data to accounting systems including QuickBooks, Xero, and NetSuite [citation:22]. Provides a programmatic abstraction layer for financial data synchronization, useful for developers building custom integrations or embedded accounting workflows.  
**Best for:** Ruby developers building custom sync workflows between applications and Xero.

### dubbl
**Stack:** Next.js / PostgreSQL / TypeScript | **License:** Open Source (per GitHub)  
A full-featured, open-source alternative to Xero and QuickBooks with API-first architecture. Features include double-entry bookkeeping, invoicing, bills, bank reconciliation, expense management, inventory, payroll, projects, CRM, fixed assets, budgets, tax, 25+ financial reports, multi-currency, and a complete REST API [citation:16]. Includes an MCP Server (OAuth 2.1) for AI coding agent connectivity. Self-hosted via Docker with PostgreSQL. While not a Xero connector, it is a direct replacement for organizations wanting to own their financial data.  
**Best for:** Teams wanting to replace Xero entirely with a self-hosted, API-first accounting platform they control.

### Bigcapital
**Stack:** (Check repository) | **License:** Open Source (per GitHub)  
An open-source financial accounting platform with intelligent reporting, positioned as an alternative to QuickBooks and Xero [citation:27]. 2,591 GitHub stars with recent updates. Suited for organizations evaluating open-source accounting replacements.  
**Best for:** Teams exploring open-source accounting alternatives to Xero with active community development.

### TPT OpenLedger
**Stack:** Tauri / Rust / Node.js | **License:** MIT OR Apache-2.0  
A desktop-native, double-entry accounting application designed as a free replacement for SaaS platforms like Xero. All financial data stays on device, encrypted at rest with SQLCipher (256-bit AES). Features include CSV bank import, chart of accounts, audit logging, optional localhost REST/GraphQL API, and BYOK integrations [citation:20]. Actively developed with MIT/Apache dual licensing.  
**Best for:** Freelancers and privacy-conscious users wanting desktop-native accounting with no cloud dependency.

### baton-xero
**Stack:** Go | **License:** Open Source (per Go package)  
A connector built with the Baton SDK that communicates with the Xero Accounting API to sync data about organizations and their members [citation:18]. Supports Client Credentials Flow (custom connection apps) and Refresh Token Flow (web app apps). Installable via Homebrew, Docker, or Go.  
**Best for:** Developers building identity and access governance workflows that need Xero organization and user data.

### Xero Official SDKs
**Stack:** Multiple (Python, Node.js, PHP, Ruby, Java, C#, Go) | **License:** MIT  
Xero maintains official SDKs generated from its OpenAPI specification, covering OAuth 2.0 authentication and the full Accounting API surface [citation:28]. Available SDKs include `xero-python`, `xero-node`, `xero-php-oauth2`, `xero-ruby`, `Xero-Java`, `Xero-NetStandard`, and `xerogolang`. These are the foundation for building any custom Xero integration, with MIT licensing allowing commercial and open-source use [citation:28]. The `xero-python` SDK handles OAuth2 token storage, refresh (30-minute access tokens, 60-day refresh tokens), and API calls [citation:17].  
**Best for:** Developers building custom Xero integrations from scratch with official, maintained SDKs in their preferred language.

### Airbyte Xero Source
**Stack:** Python / Java | **License:** MIT  
An open-source data integration connector for Xero as part of the Airbyte ecosystem (16,891 GitHub stars, 4,242 forks). Provides ELT replication from Xero to warehouses and databases, self-hostable via Airbyte's open-source platform [citation:25].  
**Best for:** Teams already using Airbyte for data ingestion wanting open-source, self-hosted Xero replication.

---

## 📊 Comparison at a Glance

| Software | License | Type | Sync Direction | Self-Hosted | Best For |
|----------|---------|------|----------------|-------------|----------|
| **Chargebee** | Proprietary | Billing → Xero | Chargebee → Xero | ❌ | Subscription invoice sync |
| **Zapier** | Proprietary | Automation | Bidirectional | ❌ | No-code arbitrary app sync |
| **Make** | Proprietary | Automation | Bidirectional | ❌ | Visual multi-step workflows |
| **Celigo** | Proprietary | iPaaS | Bidirectional | ❌ | E-commerce + NetSuite |
| **OneSaas** | Proprietary | Accounting hub | Store → Xero | ❌ | E-commerce sales sync |
| **Dataddo** | Proprietary | Data pipeline | Xero → Warehouse | ❌ | Governed warehouse delivery |
| **Fivetran** | Proprietary | ELT | Xero → Warehouse | ❌ | Existing Fivetran pipelines |
| **Stitch** | Proprietary | ELT | Xero → Warehouse | ❌ | SaaS data ingestion |
| **Workato** | Proprietary | Enterprise automation | Bidirectional | ❌ | Deep action coverage |
| **Activepieces** | MIT | Automation | Bidirectional | ✅ | Open-source automation |
| **LedgerSync** | Open Source | Ruby sync gem | App ↔ Xero | ✅ (library) | Custom Ruby integrations |
| **dubbl** | Open Source | Accounting replacement | N/A (replaces Xero) | ✅ | Own your financial data |
| **baton-xero** | Open Source | Identity sync | Xero → Baton | ✅ | Access governance |
| **Xero SDKs** | MIT | Development libraries | Custom | ✅ (library) | Build custom integrations |
| **Airbyte Xero** | MIT | ELT connector | Xero → Warehouse | ✅ | Open-source data pipelines |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Xero integration tool, SDK, or self-hosted accounting alternative that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
