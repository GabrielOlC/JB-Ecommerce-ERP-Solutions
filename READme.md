# JB Enterprise Resource Planning & Management (ERPM) Suite

**A custom-built, low-code ERP ecosystem that scaled a Shopee startup from manual chaos to automated precision.**

> **Status:** Production / Legacy (2021-2023)
> **Role:** Co-Founder & Lead Developer 

<div align="center">
  <!--<p align="left"><b>Tech Stack</b></p>-->
  <img src="https://img.shields.io/badge/Excel-217346?style=for-the-badge"  />
  <img src="https://img.shields.io/badge/VBA-gray?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Power_Query-F2C811?style=for-the-badge" />
  <img src="https://img.shields.io/badge/SQL-4479A1?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Access-9f3438?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Shopee-EE4D2D?style=for-the-badge&logo=shopee&logoColor=white" />
  <img src="https://img.shields.io/badge/Bling-2ea863?style=for-the-badge" />
</div>

## The Origin Story

When I joined JB Casa & Escritório, operations were manual and reactive. Orders were packed by memory, pricing was a guessing game (often leading to negative margins), and financial reconciliation was non-existent.

I architected **5 Integrated Applications** to solve these specific pillars of chaos, effectively building a modular **ERP** from scratch.



### 1. The "Fulfillment Engine" (FE)

*Solving the Dispatch Crisis & Data Integrity*

*** 

**Problem Statement**  

Our operations faced recurring inefficiencies: dispatch errors (wrong color/quantity), revenue leakage from pricing mistakes, and a manual invoicing bottleneck that delayed shipments by hours. These issues frustrated customers and blinded management to real-time performance.

<details>
  <summary><b>🎯 Key Challenges Addressed</b> <i>(Click to expand)</i></summary>
  <ul>
    <li><b>Customer Profiling:</b> Who are our customers, and what are their purchasing patterns?</li>
    <li><b>Process Automation:</b> How to bypass legacy ERP limitations to automate invoicing?</li>
    <li><b>Data Accuracy:</b> How can we guarantee that every product is sold at the correct price? </li>
    <li><b>Operational Velocity:</b> How to reduce packing time while eliminating human error?</li>
    <li><b>Financial Visibility:</b> How to provide real-time batch profitability insights?</li>
  </ul>
</details>

**The Solution:**  

I architected a **Scanner-Integrated Poka-Yoke Interface**, a module that seamlessly bridged gaps between our ERP and Shopee, ensuring error‑proof order processing and integration.

* **🟦 Blue Field Logic (Identification):** Instant retrieval order details data upon scan (e.g., SKU, Variation, Expected vs Real income, shipping fee/tax)
* **⬜ White Field Logic (Commit):** Transactional scanning that transitions order status (`Printed` → `ToPack`) and triggers order identification (blue field)
* **🔒 Audio-Visual Lock:** If the scanned item doesn't match the selected manifest, the system issues an audio error alert and a visual flash. If the item matches, the system confirms with a success beep.
  
  

**⚡Impact⚡**

Achieved **Zero dispatch errors**, Accelerated invoicing workflows, secured price accuracy, and delivered batch-level financial visibility—transforming shipping operations into a customer-trusted, data-informed process.



### 2. The "Revenue Recovery" System (RFS)

*Solving Financial Leakage & Compliance*

* * *

**Problem Statement**  

Shopee’s fragmented reporting system (separate files for Orders, Returns, and Anticipations) created "Phantom Returns"—items declared returned but never received, resulting in unrecovered revenue. We lacked a centralized mechanism to audit these discrepancies against our actual bank deposits.

<details>  
 <summary><b>🎯 Key Challenges Addressed</b> <i>(Click to expand)</i></summary>
 <ul>
   <li><b>Reconciliation Audit:</b> How to cross-reference the disparate data sources to find missing payments?</li>  
   <li><b>Revenue Leakage:</b> How to identify and recover funds from "Phantom Returns"?</li>  
   <li><b>Process Scalability:</b> How to audit 10K+ orders without manual spreadsheet checking?</li>  
    <li><b>Compliance:</b> How to robustly audit and track protocol disputes?</li>  
 </ul>  
</details>

**The Solution:**  

I engineered an **Automated Reconciliation Engine** using **Power Query (M)** for ETL and **VBA** for logic.

* **Data Ingestion (ETL):** Merges Orders, Anticipations, and Return reports into a Clean, Predictable and usuable datasets.

* **The "ErrorVBA" Algorithm:** Automatically flags 5 distinct payment error types (e.g., nPaid, null, N/A - RO...)

* **Protocol Management:** A dedicated interface to assign, track, and update dispute protocols directly within the system.

* **Multi‑Level Protocols:** Ability to open multple Shopee Requests Protocol without losing track. 

* **Group Analysis:** Ability to analyze multiple IDs simultaneously to detect error patterns.
  
  

**⚡Impact⚡**

Detected **500+ payment discrepancies**, enabling the recovery of significant lost revenue and establishing a reproducible financial audit process.

* * *

### 3. The "Dynamic Pricing" Calculator (GE)

*Solving Profitability & Market Competitiveness*

***

**Problem Statement**  

Operations lacked pricing discipline: campaign calculations were slow, manual, and inconsistent, delaying product launches. Static pricing exposed the business to selling at negative margins during aggressive sales events or losing market share due to overpriced listings. Without a centralized mechanism to validate costs or recommend competitive prices, profitability and market responsiveness were compromised.

<details>  
  <summary><b>🎯 Key Challenges Addressed</b> <i>(Click to expand)</i></summary>  
  <ul>  
    <li><b>Margin Protection:</b> How to ensure positive net profit after all fees (Platform, Tax, Shipping)?</li>  
    <li><b>Scenario Simulation:</b> If we offer a 10% coupon, what is the exact impact on the bottom line?</li>  
    <li><b>Reverse Engineering:</b> What price point achieves a target 15% ROI?</li>  
    <li><b>Logistics Optimization:</b> Which shipping box offers the best cost-to-protection ratio for this SKU?</li>  
  </ul>  
</details>

**The Solution:**  

A **Simulation Engine** that loads product data from a centralized database, calculates and saves margins, and determines optimal pricing values.

* **Reverse Engineering Logic:** User inputs desired Profit % or \$ → System outputs required Sell Price.

* **Campaign Simulator:** Simulates the net effect of stacked promotions (Coupons + Platform Sales) to prevent margin erosion.

* **Campaign Flexibility:** Not just simulating stacked promotions, but also reverse‑calculating required discounts to hit a target sell price, and showing “true discount %” when multiple promotions overlap.

* **Group Campaign Control:** Saving campaign setups and running group simulations to detect incoherence (e.g., store‑wide coupons that break margins for specific SKUs).

* **Box Optimization:** Automatically suggests the most cost-efficient packaging based on product dimensions and weight.

* **Cost Attribution & Management:** Ability to adjust box types, buying prices, loss %, and other cost variables dynamically.

* **Operational Insights:** Break down of the price distribution for transparency.
  
  

**⚡Impact⚡**  

Secured **consistent positive margins** across all SKUs, eliminated negative listings, accelerated campaign setup, and drastically reduced go‑to‑market for new product launches.

***

### 4. The "Strategic Cash Flow" (FC)

Solving Forecasting & Strategic Operations

* * *

**Problem Statement**  

We lacked visibility into future capital requirements. Traditional cash flow tracked the past but failed to predict future stock needs or identify day-to-day operational irregularities

<details>  
  <summary><b>🎯 Key Challenges Addressed</b> <i>(Click to expand)</i></summary>  
  <ul>  
    <li><b>Financial Forecasting:</b> Can we afford to restock next month based on current trends?</li>  
    <li><b>Scenario Planning:</b> What happens to our cash position during seasonality</li>  
    <li><b>Operational Transparency:</b> How to detect unauthorized capital outflows immediately?</li>  
    <li><b>Multi-Account View:</b> How to consolidate balances from multiple banks into a single truth source?</li>  
  </ul>  
</details>

**The Solution:** 

A predictive Cash Flow system featuring a novel **"Scenario Management Algorithm."**

* **Scenario Simulation:** A LET-formula based engine that simulates different financial realities across months (Optimistic/Pessimistic) to stress-test capital health.

* **Unified Dashboard:** Consolidates "Realized" (Actuals) vs. "Provisioned" (Expected) entries across all accounts.

* **Discrepancy Analysis:** Granular tracking highlighted discrepancies between provisioned operational costs and actual outflows.

* **Bank Integration:** Importing multi‑account data via Power Query (M).
  
  

**⚡Impact⚡**
Provided the **strategic visibility** required to identify operational mismanagement, leading to a necessary corporate restructuring and protecting the company's financial health.

* * *

### 5. Core Infrastructure (DB)

Solving Data Scalability & Integrity

* * *

**Problem Statment**  

Product data was fragmented and inconsistent: SKUs were created ad‑hoc without a standard template, variations were tracked manually, and supplier information lived in separate files. Without a centralized, user‑friendly mechanism to manage products and suppliers, data integrity and operational efficiency were compromised.

<details> 
  <summary><b>🎯 Key Challenges Addressed</b> <i>(Click to expand)</i></summary> 
  <ul> 
    <li><b>Data Consistency:</b> How to ensure every SKU follows the same creation template and avoids duplicate or inconsistent records across platforms? </li>
    <li><b>Variation Management:</b> How to easily add, edit, and validate product variations without directly manipulating Access tables?</li>
    <li><b>Supplier Integration:</b> How to connect product variations with supplier information for streamlined sourcing?</li>
    <li><b>Multi‑App Integration:</b> How to provide a single source of truth that feeds FE, GE, RFS and others simultaneously with multiple users?</li>
    <li><b>User Accessibility:</b> How to simplify database operations for multiple users with an intuitive interface?</li>
  </ul> 
</details>

**The solution:**

The development of an user-friendly Excel interface to manage a centralized database that support all applications.

* **Backend:** **MS Access (SQL)** stores the master data for 150+ SKUs and Suppliers.

* **Connector:** **ADODB** (VBA) manages all CRUD (Create, Read, Update, Delete) operations.

* **Data Integrity**:** Decoupled data from the interface allowing multiple tools (FE, GE, RFS) to query the same "Single Source of Truth." 

* **Variation Management:** Add or edit product variations directly, with validation logic to ensure data consistency

**⚡Impact⚡**

Ensured consistent SKU creation, simplified multi‑user data updates, and provided a reliable “single source of truth” for all applications — improving integrity and accelerating workflows across FE, GE, and RFS.

* * *

## 📂 Repository Structure

```textile
/JB-Ecommerce-ERP-Solutions
│── READme
|                                     
│── /Fulfillment-Engine (FE) 
|   │──   
|   └──          
├── /Revenue-Recovery-System (RFS)
|   │──    
|   └──
├── /Dynamic-Pricing-Calculator (GE)
|   │──   
|   └──
├── /Strategic-Cash-Flow (FC)
|   │──   
|   └──
└── /Core-Infrastructure (DB)
    │──   
    └──     
```




