# GLPI Documenso Signer Plugin

![GLPI](https://img.shields.io/badge/GLPI-10.0+-v?color=005f9e)
![Documenso](https://img.shields.io/badge/Documenso-Compatible-black?logo=documenso)
![License](https://img.shields.io/badge/License-GPL%20v3-blue.svg)

An open-source plugin for GLPI that seamlessly integrates with **Documenso** to automate document signing workflows directly from GLPI Tickets using specific tags.

## Table of Contents
* [Features](#features)
* [Workflow Diagram](#workflow-diagram)
* [Prerequisites](#prerequisites)
* [Installation](#installation)
* [Configuration](#configuration)
* [Usage Guide](#usage-guide)
* [License](#license)

---

## Features

* **Tag-Driven Automation:** Trigger signing flows automatically by adding specific tags to ticket documents.
* **Dynamic Role Mapping:** Automatically detects and assigns signers based on GLPI Ticket roles (Observer or Requester).
* **Precise Signature Placement:** Configure exact X/Y coordinates for signature placement directly from the GLPI interface.
* **Secure API Integration:** Environment-isolated server credentials combined with encrypted GLPI database storage for API Keys.

---

## Workflow Diagram

```text
[ Document Uploaded ] ──► [ Check Tags ]
                                │
         ┌──────────────────────┴──────────────────────┐
         ▼ (Tag: Observer)                             ▼ (Tag: Requester)
  Fetch Observer Data                           Fetch Requester Data
         │                                             │
         └──────────────────────┬──────────────────────┘
                                ▼
                  [ Read Coordinates & API Key ]
                                │
                                ▼
               [ Call Documenso API via Server .env ]
                                │
                                ▼
               [ Document Sent for Digital Signature ]
