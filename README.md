# Kanban Lead-Time Demand & Card Sizing Model

This repository contains a planning model for estimating Kanban card counts and reorder points based on demand, lead time, and service level assumptions.

The model is designed to make the logic used in ERP replenishment systems transparent and auditable, rather than hiding it behind configuration screens.

---

## What the model does

The workbook estimates:

- Expected demand during lead time
- Variability of demand during lead time
- Safety stock using either:
  - A fixed percentage buffer, or
  - A statistical service-level (Z-score) approach
- The reorder point
- The required number of Kanban cards (containers)

It explicitly accounts for:
- Demand variability
- Lead-time variability
- Discrete container sizing

---

## Structure of the workbook

- **Data** — historical observations of demand and lead time
- **Model** — inputs, calculations, and outputs
- **Instructions** — explanation of purpose, method, and usage
- **Math (Reference)** — formulas, definitions, and a worked example

---

## Core logic

Let:

- D = demand per period  
- L = lead time (periods)  
- σ_D = std dev of demand  
- σ_L = std dev of lead time  
- Z = service level factor  
- C = container size  

Then:

- Lead-time demand: `LTD = D × L`
- Std dev during lead time:
- Safety stock (Z method): `SS = Z × σ_LT`
- Reorder point: `ROP = LTD + SS`
- Kanban cards: `N = ROUNDUP( ROP / C )`

---

## Assumptions

- Demand and lead time are treated as independent
- Periods are consistent (e.g., daily or weekly, not mixed)
- This is a planning model, not a real-time execution system
- Results depend on the quality and representativeness of historical data

---

## Intended use

This model is intended for:

- Educational purposes
- Scenario analysis
- Explaining replenishment logic
- Supporting inventory planning discussions

It is not intended to replace an ERP system, but to clarify how such systems operate under the hood.

---

## License

This project is provided for demonstration and learning purposes only and carries no warranty or guarantee of fitness for operational use.


