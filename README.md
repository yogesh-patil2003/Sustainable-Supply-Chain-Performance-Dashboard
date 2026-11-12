# Sustainable Supply Chain Performance Dashboard

End-to-end **Power BI** operations and logistics analytics solution built on a **9-table, 24,612-row Star Schema** tracking procurement, production quality, inventory safety stock, freight shipments, and commercial profitability.

---

## Overview

Supply chain teams need unified visibility across upstream supplier procurement, factory defect rates, warehouse reorder thresholds, carrier delays, and customer margins. This repository pairs an introductory SKU overview (`Yogesh Patil powerbi.pbix`) with the full **multi-fact Star Schema model** (`supply_chain_star_schema.pbix`) covering **23,852 fact records** and **760 dimension records**.

---

## Key Features

- **Procurement & Supplier Quality:** Tracks purchase order quantities, unit cost variance, supplier lead times (`lead_time_days`), and inspection `quality_score` across 7 suppliers.
- **Production & Defect Monitoring:** Analyzes batch quantities vs. `defective_units` and `defect_rate_pct` across 6 global facilities.
- **Inventory & Reorder Alerts:** Evaluates `stock_level` against `safety_stock_level` and `reorder_point` thresholds.
- **Logistics & Carrier Delays:** Monitors freight `shipping_cost`, carrier utilization, `total_weight_kg`, delivery status, and `delay_reason`.
- **Sales & Profit Margin Tracking:** Breaks down `gross_revenue`, discounts, `net_revenue`, `total_cost`, and `profit_margin_pct`.

---

## Technology Stack

- **Business Intelligence:** Power BI Desktop
- **Data Modeling:** Multi-Fact Star Schema (5 Fact tables, 4 Conformed Dimensions)
- **Analytics & Transformations:** DAX Calculated Measures, Power Query
- **Source Data:** Structured CSV tables (`24,612` total rows)

---

## Data Model & Schema (`24,612` Verified Rows)

| Table | Type | Rows | Primary Attributes |
| :--- | :--- | :---: | :--- |
| `fact_sales.csv` | Fact | `8,500` | `sales_id`, `date_key`, `product_id`, `customer_id`, `net_revenue`, `profit`, `profit_margin_pct` |
| `fact_shipment.csv` | Fact | `7,500` | `shipment_id`, `ship_date_key`, `delivery_date_key`, `carrier`, `status`, `shipping_cost`, `delay_reason` |
| `fact_production.csv` | Fact | `4,500` | `production_id`, `date_key`, `product_id`, `facility_id`, `quantity_produced`, `defective_units`, `defect_rate_pct` |
| `fact_procurement.csv` | Fact | `2,200` | `procurement_id`, `order_date_key`, `supplier_id`, `total_cost`, `lead_time_days`, `quality_score` |
| `fact_inventory.csv` | Fact | `1,152` | `inventory_id`, `date_key`, `product_id`, `facility_id`, `stock_level`, `safety_stock_level`, `reorder_point` |
| `dim_date.csv` | Dimension | `731` | `date_key`, `year`, `quarter`, `month_name`, `week`, `is_weekend` |
| `dim_product.csv` | Dimension | `16` | `product_id`, `product_name`, `category`, `product_line`, `unit_price`, `unit_cost`, `weight_kg` |
| `dim_supplier.csv` | Dimension | `7` | `supplier_id`, `supplier_name`, `country`, `city`, `specialty`, `tier`, `avg_quality_score` |
| `dim_facility.csv` | Dimension | `6` | `facility_id`, `facility_name`, `country`, `facility_type`, `specialization`, `annual_capacity` |

*(Also preserved: `Sustainable Supply Chain Performance.csv` [`100` rows] paired with `Yogesh Patil powerbi.pbix`.)*

---

## Project Structure

```text
Sustainable-Supply-Chain-Performance-Dashboard/
├── dataset/
│   ├── dim_date.csv
│   ├── dim_facility.csv
│   ├── dim_product.csv
│   ├── dim_supplier.csv
│   ├── fact_inventory.csv
│   ├── fact_procurement.csv
│   ├── fact_production.csv
│   ├── fact_sales.csv
│   └── fact_shipment.csv
├── supply_chain_star_schema.pbix             # 9-table Star Schema Power BI model
├── Yogesh Patil powerbi.pbix                 # Initial sustainability & carrier dashboard
├── Sustainable Supply Chain Performance.csv  # Initial 100-row overview CSV
├── LICENSE                                   # MIT License
└── README.md
```

---

## Dashboard Preview

<img width="1087" height="738" alt="Supply Chain Power BI Dashboard Overview" src="https://github.com/user-attachments/assets/aa83f23a-2719-4a4b-a5f6-1bddd07fe2cc" />

---

## How to Open

1. Download [`supply_chain_star_schema.pbix`](supply_chain_star_schema.pbix) (or [`Yogesh Patil powerbi.pbix`](Yogesh%20Patil%20powerbi.pbix)).
2. Open in **Power BI Desktop**.
3. If prompted to refresh CSV paths, point the Power Query data source parameter to your local `dataset/` directory.

---

## Analytical Insights Enabled

- Compare supplier quality scores vs. delivery lead times to isolate procurement bottlenecks.
- Pinpoint high-defect production batches and facilities approaching stockout thresholds.
- Track carrier cost vs. delay reasons to surface logistics optimization opportunities.

---

## License

MIT License — see [LICENSE](LICENSE).

## Author

**Yogesh Patil** — [@yogesh-patil2003](https://github.com/yogesh-patil2003) · [LinkedIn](https://www.linkedin.com/in/yogeshpatil2003/) · [Email](mailto:officialyogeshpatil0@gmail.com)
