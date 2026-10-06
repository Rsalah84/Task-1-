# PIZ SHOP – Impacted As-Planned Analysis (Delay Events DE-0010 → DE-0045)

**Basis:** Baseline `PIZSHOP-BL-2` (P6 XML, Data Date 29-Jul-26, Contract Completion MS-0070 = 16-Nov-26)
**Method:** Impacted As-Planned – AACE RP 29R-03 MIP 3.6 (Modeled / Additive / Single Base), fragnets per AACE RP 52R-06 principles
**Status date for open events:** 06-Oct-26
**Calendar:** KSA 6-Day 8h (Fri off, 23-Sep National Day holiday)

> The CPM engine used for this analysis reproduces all 83 baseline activity dates of BL-2 **exactly** (0 mismatches) before any change was made, so the results below can be reproduced by importing the XML into P6 and pressing F9.

---

## 1. Files

| File | Content |
|---|---|
| `PIZSHOP-IAP-01_Delay-Events.xml` | P6 XML ready to import (Project ID `PIZSHOP-IAP-01`, so it does not overwrite BL-2). Includes the new WBS, 5 delay-event activities, 18 new links, deleted waterproofing, recalculated dates. |
| `BL-vs-Impacted_Comparison.csv` | Activity-by-activity comparison: BL start/finish/TF vs impacted start/finish/TF and finish variance (calendar days). |

## 2. Changes made to the schedule

### 2.1 Scope omission
| Activity | Action | Reason |
|---|---|---|
| C1-1305 Waterproofing – Toilet, Wash & Kitchen Wet Areas | **Deleted** with its 4 links (C2-2310 →, → C1-1190 / C1-1310 / C1-1320) | No waterproofing item in the contract; ground floor, no basement. No open ends created: all successors keep other predecessors. Zero effect on dates (activity had 55d TF). |

### 2.2 New WBS
```
PIZ.4    DELAY EVENTS & ADDITIONAL WORKS - OUT OF CONTRACT SCOPE
PIZ.4.1    Late Approvals by Employer / Consultant
PIZ.4.2    Works by Others - HVAC (Out of Scope)
```

### 2.3 Delay-event fragnets
Each event is modelled as a task from the **date the contractor needed it** (constraint *Start On or After*) to the **actual / status date**. So the activity finish equals the real approval/completion date, and the bar shows the delay window.

| ID | Event | Need-by date (start) | Actual / status (finish) | Dur (wd) | Successors (FS 0) |
|---|---|---|---|---|---|
| DE-0010 | Late approval of CCTV & electrical drawings | 04-Aug-26 (per contract/submittal plan) | 26-Aug-26 | 20 | C2-2410, C2-2420, C2-2430, C2-2440 |
| DE-0020 | Late final approval of window openings | 18-Aug-26 *(assumed = day after BL C2-2020 approval of submittals)* | 20-Aug-26 | 3 | C2-2410, C2-2730 |
| DE-0030 | HVAC ductwork by others – late completion | 25-Aug-26 (BL early start of wall lining / seating ceiling) | 17-Sep-26 | 21 | C2-2410, C1-1400, C1-1410, C1-1420, C1-1430, C1-1450 |
| DE-0040 | Kitchen AC units & fresh-air units by others – not installed | 02-Sep-26 (BL early start of C2-2440) | 06-Oct-26 (status – still open) | 29 | DE-0045 |
| DE-0045 | Kitchen AC & FA units installation – **forecast** | 07-Oct-26 | 12-Oct-26 | 5 *(assumption, to be confirmed)* | C2-2440 |

All DE activities have MS-0000 as predecessor (no open starts).

## 3. Results

### 3.1 Key milestones
| Milestone | Baseline | Impacted | Variance |
|---|---|---|---|
| MS-0020 Substrate Ready for Tiling | 24-Aug-26 | 24-Aug-26 | 0 |
| MS-0050 MEP & Fire Systems Commissioned | 04-Oct-26 | **03-Nov-26** | **+30 cd** |
| MS-0010 C1 Long-Lead Materials on Site | 27-Oct-26 | 27-Oct-26 | 0 |
| MS-0030 Contract 1 Complete | 07-Nov-26 | 07-Nov-26 | 0 |
| MS-0040 Contract 2 Complete | 14-Nov-26 | 14-Nov-26 | 0 |
| **MS-0060 Handover / Substantial Completion** | **16-Nov-26** | **16-Nov-26** | **0** |
| MS-0070 Contractual Completion | 16-Nov-26 | 16-Nov-26 | 0 |

### 3.2 Event-by-event (each inserted alone)
| Event alone | Effect on MS-0060 |
|---|---|
| C1-1305 deletion only | 0 |
| DE-0010 only | 0 |
| DE-0020 only | 0 |
| DE-0030 only | 0 |
| DE-0040 + DE-0045 only | 0 |
| All combined | 0 |
| Sensitivity: DE-0030 also linked to C2-2420 & C2-2440 (ducts before closing ceilings) | 0 |

### 3.3 Why completion does not move
The BL-2 critical path is **C1-1100 Spanish porcelain (90 calendar-day import) → C1-1150 → C1-1300 → C1-1310 → C1-1440 → C1-1460 → C2-2920 → C2-2930 → C2-2940 → MS-0060**.
The entire Contract-2 fit-out stream (ceilings, wall lining, paint, MEP 2nd fix, T&C) had **~30–36 working days of float**. The four events consume that float but do not exceed it:

| Activity | BL finish | Impacted finish | Var (cd) | TF BL → Impacted |
|---|---|---|---|---|
| C2-2410 Gypsum wall lining | 30-Aug | 24-Sep | +25 | 45 → 24 |
| C2-2430 Toilet ceiling | 18-Aug | 30-Aug | +12 | 48 → 38 |
| C2-2420 Seating ceiling | 01-Sep | 03-Sep | +2 | 36 → 34 |
| C2-2440 Kitchen Armstrong ceiling | 05-Sep | 15-Oct | **+40** | 38 → **4** |
| C2-2500 Wall paint | 08-Sep | 01-Oct | +23 | 43 → 24 |
| C2-2620 Lighting | 14-Sep | 22-Oct | +38 | 36 → **4** |
| C2-2730 Kitchen windows | 26-Sep | 26-Oct | +30 | 30 → **4** |
| C2-2900 MEP T&C | 30-Sep | 31-Oct | +31 | 30 → **4** |
| C2-2910 Fire alarm / Civil Defence | 04-Oct | 03-Nov | +30 | 30 → **4** |
| C2-2960 Operating / Health licence | 12-Oct | 11-Nov | +30 | 30 → **4** |

**Governing event = DE-0040/0045 (kitchen AC & fresh-air units).** Path: DE-0045 → C2-2440 → C2-2620 → C2-2730 → C2-2900 → C2-2910 → C2-2960 → MS-0060 has only **3.9 working days** of float left.

### 3.4 Trigger date – kitchen AC units (the number to watch)
Latest installation date of the kitchen AC & FA units without delaying handover: **17-Oct-26**. After that, handover slips about day-for-day:

| Kitchen units installed by | MS-0050 | MS-0060 Handover | Slip |
|---|---|---|---|
| 12-Oct (5d) | 03-Nov | 16-Nov | 0 |
| 15-Oct (8d) | 07-Nov | 16-Nov | 0 |
| 18-Oct (10d) | 09-Nov | 17-Nov | +1 cd |
| 24-Oct (15d) | 15-Nov | 23-Nov | +7 cd |
| 29-Oct (20d) | 21-Nov | 29-Nov | +13 cd |
| 04-Nov (25d) | 26-Nov | 05-Dec | +19 cd |

## 4. Interpretation & recommendations

1. **On baseline logic alone, these events do not yet support a time EOT**: completion is driven by the Contract-1 porcelain import. They **do** support a claim for **loss of float (~26–32 wd on the fit-out stream)** and possible **disruption / prolongation of Contract-2 resources**. Whether float belongs to the project or the contractor depends on the contract (FIDIC 2017 cl. 8.5 / project-owned float vs. contractor-owned). Confirm the contract form.
2. **Send a notice now for DE-0040 (kitchen AC units)**: it is open, near-critical, and becomes critical after **17-Oct-26**. Under FIDIC-type contracts the notice period (e.g. 28 days) runs from when the contractor became aware. Cite this analysis as the contemporaneous forecast.
3. **Do a proper TIA (AACE 52R-06) on a statused update at DD 06-Oct-26.** This analysis is prospective on the un-progressed baseline. The overdue-work printout shows contractor-side slippage too (C1-1110, C1-1140, C1-1160, C1-1190, C1-1240, C1-1150, C2-2700/2800 etc.). If the Spanish porcelain (C1-1100) is ahead of plan or already delivered, the critical path may move to the Contract-2 stream. Then these same fragnets would produce a real EOT, and concurrency with contractor delays must be assessed.
4. **Logic observations to raise in the next revision:**
   - C2-2620 *Install Lighting* is one activity for the whole shop and waits for the kitchen ceiling. That is why one kitchen issue holds the whole T&C chain. Consider splitting lighting into Seating / Toilets / Kitchen.
   - The BL has no HVAC activities at all, not even as interface milestones by others. Add *HVAC by Others – Ready for Ceiling Closure* milestones to future updates.
   - Ducts physically precede ceiling closure. The sensitivity run (DE-0030 → C2-2420/C2-2440) does not change the result.

## 5. Assumptions to confirm
- DE-0020 need-by date taken as 18-Aug-26. It does not affect the result: the event has 48 d TF.
- DE-0045 forecast installation of kitchen units = 5 working days (7–12 Oct). Replace with the actual / committed date from the HVAC contractor.
- "الفرش" interpreted as Furniture & Fixtures Installation (WBS C1.5): C1-1400/1410/1420/1430/1450.
- Delay events are modelled with *Start On or After* constraints on their need-by dates. In a TIA on an update, replace them with actual start/finish dates.

## 6. How to use in P6
1. File → Import → Primavera P6 XML → `PIZSHOP-IAP-01_Delay-Events.xml` → **Create New Project** (keeps BL-2 untouched).
2. Assign BL-2 as Project Baseline (Project → Maintain Baselines / Assign), so the variance columns and baseline bars show.
3. F9 at DD 29-Jul-26 → dates should match the comparison CSV.
4. Suggested layout: group by WBS, columns *BL Finish, Finish, Variance – BL Finish Date, Total Float*, filter `Total Float ≤ 5d`.
