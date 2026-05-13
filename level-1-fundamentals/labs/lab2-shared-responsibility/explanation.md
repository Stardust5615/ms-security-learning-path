# Lab 2: Shared Responsibility Diagram

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 1 — Security Fundamentals |
| **Certification Target** | SC-900 |
| **Estimated Duration** | ~45 minutes |
| **Environment** | diagrams.net (browser-based, no install needed) |
| **Difficulty** | Beginner |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Create a shared responsibility matrix covering SaaS, PaaS, and IaaS
- [ ] Colour-code responsibilities: Microsoft (green), Shared (orange), Customer (red)
- [ ] Map specific Microsoft products to each responsibility layer
- [ ] Export the diagram as PNG and SVG

## Diagram Specification

### Axes
- **X-axis:** SaaS (Microsoft 365), PaaS (Azure App Service), IaaS (Azure VMs)
- **Y-axis (layers, bottom to top):**
  1. Physical data centre
  2. Physical network
  3. Physical hosts
  4. Operating system
  5. Network controls
  6. Applications
  7. Identity & directory infrastructure
  8. Accounts & identities
  9. Devices (endpoints)
  10. Information & data

### Colour Key
- 🟢 **Green** — Microsoft's responsibility
- 🟠 **Orange** — Shared responsibility
- 🔴 **Red** — Customer's responsibility

## Microsoft Product Mapping

| Responsibility Layer | Microsoft Tool |
|----------------------|---------------|
| Identity & directory infrastructure | Microsoft Entra ID |
| Accounts & identities | Microsoft Entra ID, Identity Protection |
| Devices | Microsoft Intune, Defender for Endpoint |
| Applications | Defender for Cloud Apps |
| Information & data | Microsoft Purview |
| Network controls | Azure Firewall, Network Security Groups |
| Operating system (IaaS) | Defender for Servers (Defender for Cloud) |

## Steps

### Step 1: Open diagrams.net

<!-- Go to https://app.diagrams.net — use browser-based version, no account needed -->

### Step 2: Create the responsibility matrix

<!-- Build the grid: rows = 10 layers, columns = 3 cloud models + 1 label column -->
<!-- Colour each cell according to responsibility -->

### Step 3: Add product annotations

<!-- Next to each customer/shared row, add a text label for the Microsoft tool that helps -->

### Step 4: Export

<!-- File → Export as → PNG (save as shared-responsibility-diagram.png) -->
<!-- File → Export as → SVG (save as shared-responsibility-diagram.svg) -->

## Screenshots & Files

<!-- screenshot: shared-responsibility-diagram.png -->
<!-- file: shared-responsibility-diagram.svg -->
<!-- screenshot: diagrams-net-workspace.png -->

## Key Takeaways

- In SaaS (Microsoft 365), Microsoft manages everything below the data/identity layer
- In IaaS (Azure VMs), the customer manages OS, applications, data, and identity
- The shared responsibility model determines which Microsoft security tools YOU need to configure
- <!-- add your own insight -->

## Exam Relevance

<!-- SC-900: Describe the shared responsibility model -->
<!-- SC-900: Describe Azure services — IaaS/PaaS/SaaS -->
