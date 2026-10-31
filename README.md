# 🏭 Industrial IoT Fleet OEE & Telemetry Command Center

An enterprise-grade, multi-plant operational intelligence and asset tracking suite built entirely in Google Sheets / Excel. Designed for industrial engineers, operations managers, and B2B stakeholders to monitor Real-Time Equipment Effectiveness (OEE), unplanned downtime hours, and maintenance expenditures across international manufacturing facilities.

---

## 🚀 Key Features & Architecture

* **`Control_Dashboard` (Sheet 1):** Executive command center featuring dynamic KPI summary cards, multi-plant performance rollups, and live interactive dropdown filtering (`All Plants`, specific facilities, and individual machine telemetry).
* **`Matrix_Machine_Uptime_Tracker` (Sheet 2):** 31-day operational log tracking daily asset status (Running, Unplanned Stoppage, Maintenance) across 9 industrial units spanning Detroit, Stuttgart, and Yokohama plants[cite: 6].
* **`Maintenance_Cost_Calculator` (Sheet 3):** Automated financial engine linking asset downtime hours directly to labor rates, parts replacement costs, and financial impact status[cite: 5].
* **`Master_Equipment_Registry` (Sheet 4):** Centralized asset metadata registry containing serial numbers, plant locations, production lines, assigned technicians, and maintenance tiers[cite: 4].

---

## 📊 Core Formulas & Interactivity

The command center utilizes robust spreadsheet logic combining `INDEX/MATCH`, `IF` conditional branching, and direct telemetry calculations:
* **Dynamic Fleet OEE:** `=IF(TRIM(E4)="All Machines", (SUM(Matrix_Machine_Uptime_Tracker!B35:H35) / (31 * 7)) * 100, IFERROR(INDEX(Matrix_Machine_Uptime_Tracker!B38:H38, MATCH(E4, Matrix_Machine_Uptime_Tracker!B1:H1, 0)), 0))`
* **Automated Spend Aggregation:** Links maintenance expenditure tables directly to operational downtime hours with automated error handling.

---

## 📂 Repository Structure
```text
├── Industrial_IoT_Fleet_OEE_Telemetry_Command_Center.xlsx
├── README.md
└── docs/
    └── architectural_blueprint.md
