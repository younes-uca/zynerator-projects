# Enterprise Software Projects Overview

This repository contains design specifications and detailed documentation for 5 enterprise-level software systems. Each project is tailored to solve specific domain problems ranging from retail management and port operations to supply chain execution and tax administration.

---

## Table of Contents

1. [Channel Inc - Store & Product Catalogue Management](#1-channel-inc---store--product-catalogue-management)
2. [OCP Group - Phosphate Supply Chain Management](#2-ocp-group---phosphate-supply-chain-management)
3. [Tanger Med Port - Incident Management System](#3-tanger-med-port---incident-management-system)
4. [Declaration Cotisation Mutuelle (CNSS) Management](#4-declaration-cotisation-mutuelle-cnss-management)
5. [Corporate Income Tax Management (IS)](#5-corporate-income-tax-management-is)

---

## 1. Channel Inc - Store & Product Catalogue Management

### 📌 Overview
The **Channel Inc Management System** is designed to streamline global boutique store orders, product cataloging, and inventory compliance. It allows store managers and corporate administrators to organize products by collections, looks, themes, and detailed specifications while tracking non-compliances and order statuses.

### 🛠️ Architecture & Tech Stack
* **Backend:** Spring Boot (Junior Template)
* **Frontend:** Angular (Senior Template)
* **Data Interchange:** YAML / REST APIs

### 🧩 Core Modules & Features
* **Purchase & Boutique Order Management:** Creation, tracking, and itemization of boutique store purchases (`OrderBoutique`, `OrderBoutiqueItem`, `OrderBoutiqueItemDetail`).
* **Catalog Management:** Cataloging products with looks, themes, and shape classifications (`ProduitCatalog`, `Produit`, `ProduitDetail`).
* **Referential Data:** Master data configuration for colors, materials, size grids, sub-departments, and product finishes.

### 🗂 Domain Entities
* **Order Domain:** `OrderBoutique`, `OrderBoutiqueItem`, `OrderBoutiqueItemDetail`, `OrderSatus`
* **Catalog Domain:** `ProduitCatalog`, `Produit`, `ProduitDetail`
* **Referential Domain:** `MatiereProduit`, `CouleurProduit`, `Theme`, `Look`, `SizeGrid`, `FinitionProduit`, `SubDepartement`, `ShapeProduit`, `ShapeProduitDetail`

---

## 2. OCP Group - Phosphate Supply Chain Management

### 📌 Overview
An end-to-end industrial supply chain management platform designed for OCP Group. It oversees the entire lifecycle of phosphate operations—from extraction at mine sites (Mzinda, Bouchane, Youssoufia) through processing (screening, washing, drying, calcination) to final local sales or port expedition.

### 🛠️ Architecture & Tech Stack
* **Backend:** NestJS (Junior Template)
* **Mobile / Frontend:** React Native (Junior Template)

### 🧩 Core Modules & Features
* **Production & Planning:** Management of production periods, exercises, and maintenance programs (`ProgrammeManutentionPeriode`, `ProductionPeriode`, `ProductionExercice`).
* **Supply Chain Execution:** Tracking core operations including Extraction, Screening (*Criblage*), Washing (*Lavage*), Drying (*Sechage*), Calcination, and Transport (*Expedition*).
* **Unplanned Incident & Hazard Management:** Tracking machinery downtime (*ArretNonPlanifie*) and product quality complaints (*Reclamation*).
* **Demand & Inventory Tracking:** Client demand handling, stock operations, store levels, and operational center capacity tracking.

### 🗂 Domain Entities
* **Planning & Production:** `Periode`, `Exercice`, `ProgrammeManutentionPeriode`, `ProductionPeriode`, `ProductionExercice`
* **Supply Chain:** `Extraction`, `Criblage`, `TransportSite`, `Lavage`, `CoutLavage`, `Sechage`, `Calcination`, `Expedition`
* **Hazards & Demands:** `Reclamation`, `ArretNonPlanifie`, `Demande`, `Client`
* **Stock & Center Management:** `Stock`, `OperationStock`, `Magasin`, `CentreOperatoire`, `ProduitSource`, `ProduitMarchand`

---

## 3. Tanger Med Port - Incident Management System

### 📌 Overview
A specialized maritime safety and incident tracking system for Tanger Med Port Authority (TMMS). It tracks real-time event reporting (vessel anomalies, weather conditions, emergency actions), monthly indicator consolidation, and continuous QSE (Quality, Safety, Environment) improvement logging.

### 🛠️ Architecture & Tech Stack
* **Backend:** .NET (Junior Template)
* **Mobile / Frontend:** React Native (Junior Template)

### 🧩 Core Modules & Features
* **Incident Event Reporting:** Real-time logging of vessel incidents with sea state indicators (wind force/direction, swell height, current) (`RapportEvenement`).
* **Monthly Indicator Analytics:** Aggregation of incidents by vessel category, operational sector (piloting, towing, mooring), and event types (`RapportEvenementMensuel`).
* **Improvement Journal (*Journal d'Amélioration*):** Action tracking, root-cause identification, and evaluation of QSE safety measures (`JournalAmelioaration`).
* **Process & Key Performance Indicators:** Process step monitoring and monthly target evaluation (`ProcessElement`, `IndicateurProcessElement`).

### 🗂 Domain Entities
* **Event Domain:** `RapportEvenement`, `Collaborator`, `Vessel`, `Port`, `Secteur`, `TypeEvenement`
* **Monthly Aggregation:** `RapportEvenementMensuel`, `RapportEvenementMensuelSecteur`, `RapportEvenementMensuelTypeEvenement`
* **QSE Improvement:** `JournalAmelioaration`, `SystemeManagement`, `Processus`, `CategorieEcrate`, `OrigineEcrate`, `TypeAction`
* **Indicators & Process:** `Process`, `ProcessElement`, `IndicateurProcessElement`, `ProcessStepElementMensualite`

---

## 4. Declaration Cotisation Mutuelle (CNSS) Management

### 📌 Overview
An enterprise compliance portal for managing employer social security and mutual healthcare contributions (CNSS declarations). It handles batch files, employer-insured agent mappings, audit history logging, data exchange protocols, and multi-channel notifications.

### 🛠️ Architecture & Tech Stack
* **Backend:** Spring Boot (Junior Template)
* **Frontend:** React (Senior Template)

### 🧩 Core Modules & Features
* **Core Cotisation Declaration:** Declaration synthesis and detailed employee contribution tracking (salary, patronal/salarial rates, AMO, regularizations) (`DeclarationCotisation`, `DeclarationCotisationSynthese`).
* **Audit & Historical Syntheses:** Complete audit trail of submission histories, status variations, and action logs (`DeclarationCotisationHistorique`).
* **Data Exchange (Echange):** Transmission logs between employer portals and back-office CNSS systems via automated batch/email channels (`HistoriqueEchangeDeclarationCotisation`).
* **Multi-Channel Notifications:** Status notification pipeline via Email, SMS, or System Alerts (`NotificationDeclarationCotisation`).

### 🗂 Domain Entities
* **Core Declaration:** `DeclarationCotisation`, `DeclarationCotisationSynthese`, `DeclarationCotisationPeriode`
* **Actors:** `Employeur`, `Mutuelle`, `Assure`, `StatutAgentDeclarationCotisation`
* **History & Exchange:** `DeclarationCotisationHistorique`, `HistoriqueEchangeDeclarationCotisation`, `PartieHistoriqueEchangeDeclarationCotisation`
* **Notifications:** `NotificationDeclarationCotisation`, `StatutNotificationDeclarationCotisation`, `CanalNotificationDeclarationCotisation`

---

## 5. Corporate Income Tax Management (IS)

### 📌 Overview
A corporate tax calculation and filing platform designed to manage Corporate Income Tax (*Impôt sur les Sociétés - IS*). It automatically computes tax brackets based on company scale, legal category, regional variations, arrears penalties, and cross-checks taxable bases against vendor/customer invoices.

### 🛠️ Architecture & Tech Stack
* **Backend:** Spring Boot (Senior Template)
* **Frontend:** Angular (Senior Template)

### 🧩 Core Modules & Features
* **Company & Region Management:** Maintenance of registered enterprise profiles, regional rates, and legal entity categories (`Company`, `Region`, `LegalCategory`).
* **Tax Rate Rules Engine:** Definition of progressive tax brackets, regional exemptions, and delay penalty multipliers (`TaxRate`).
* **Tax Filing Calculation:** Automated computing of annual income tax statements, arrears, and validation states (`CorporateIncomeTax`).
* **Invoice Cross-Verification:** Ingesting net, gross, and VAT amounts from customer and vendor invoices for audit trails (`CorporateIncomeTaxInvoice`).

### 🗂 Domain Entities
* **Company Domain:** `Company`, `LegalCategory`, `Region`
* **Tax Calculation Domain:** `TaxRate`, `CorporateIncomeTax`, `CorporateIncomeTaxState`
* **Invoice Domain:** `CorporateIncomeTaxInvoice`, `InvoiceType`

---

## 🚀 Getting Started

To explore or generate the underlying codebases for these designs:
1. Ensure the target framework runtime (Spring Boot, NestJS, or .NET) is configured for backend modules.
2. Setup the target frontend environment (Angular or React/React Native).
3. Import the corresponding domain models from the YAML design specifications into your code generation tool.
