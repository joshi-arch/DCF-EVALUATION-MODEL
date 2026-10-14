# Amazon DCF Valuation Model

**Financial Statement Forecast, Scenario Analysis & Discounted Cash Flow Evaluation**

> All monetary values are presented in **USD millions**, unless stated otherwise.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Data & Methodology](#data--methodology)
- [Inflation & Operating Assumptions](#inflation--operating-assumptions)
- [Interlinked Financial Statements](#interlinked-financial-statements)
- [Working Capital](#working-capital)
- [Capital Expenditure & Depreciation](#capital-expenditure--depreciation)
- [Debt, Interest & Cash](#debt-interest--cash)
- [Scenario Switches](#scenario-switches)
- [DCF Evaluation: FCFF, WACC & Enterprise Value](#dcf-evaluation-fcff-wacc--enterprise-value)
- [Output Page](#output-page)
- [Key Findings](#key-findings)
- [Model Review & Rectification](#model-review--rectification)
- [Conclusion](#conclusion)

---

## Project Overview

This project analyses Amazon's historical financial statements and develops a **five-year forecast for 2026–2030** before estimating the value of the operating business using a **Discounted Cash Flow (DCF)** model.

The objective was to:

- Understand Amazon's historical financial position
- Use historical results as the starting point for forecasts
- Link the Income Statement, Cash Flow Statement and Balance Sheet
- Estimate future free cash flow to the firm (FCFF)

The DCF section then discounts forecast cash flows and a terminal value to estimate enterprise value.

The workbook is designed to be **interactive**. Users can change selected scenario switches and assumptions, including sales growth, pricing increases and capital expenditure. These changes are intended to flow through the forecast model and affect FCFF and the valuation summary.

### Workbook Structure

The model contains five worksheets:

| Worksheet | Purpose |
|---|---|
| **Cover** | Title page |
| **Output** | Simple navigation / summary page |
| **Input** | Assumptions and scenario settings |
| **DCF Evaluation** | Calculates FCFF, WACC, terminal value and enterprise value |
| **Model** | Linked statements and supporting schedules |

---

## Data & Methodology

The model uses historical financial information for **2021–2025**. Forecasts for **2026–2030** are generated using a combination of historical results and forward-looking assumptions. Historical data provides the starting point; forecast values are model estimates rather than reported company results.

**Key assumptions and drivers:**

- Sales growth
- Pricing increases
- Capital expenditure
- Working-capital days (receivables, inventory and payables)
- Inflation
- Common equity and term-debt assumptions
- Terminal growth
- Depreciation and useful-life assumptions
- Tax assumptions
- Interest-rate assumptions for cash, credit lines and long-term debt
- Payout ratio

The purpose of these assumptions is to create a **connected model** rather than forecast every statement independently. A change to an operating assumption can affect revenue, costs, profit, working capital, cash flow, asset balances and ultimately the DCF valuation.

The model includes scenario options labelled **Best Case**, **Base Case**, **Worst Case** and **Off** for selected drivers. These settings are useful for comparing different possible outcomes. They are not predictions: they are alternative cases based on assumptions selected by the model builder.

---

## Inflation & Operating Assumptions

Inflation is included as a general operating assumption because changes in prices can affect the costs of running a business and the assumptions used in a forecast. Depending on how the workbook links the inflation input to other drivers, inflation may affect forecast costs, capital spending or pricing-related assumptions.

Sales growth and pricing increases are separated in the Input tab. This helps the model represent different drivers of revenue rather than relying on a single growth percentage. However, the assumptions should be applied consistently so the same price effect is not counted twice.

The main chain of impact being modelled is:

```text
Operating Assumptions → Revenue & Costs → Profit → Tax → Cash Flow → Balance Sheet → FCFF → DCF Valuation
```

The Input tab is the place to review the assumptions and selected cases before interpreting the output. Any assumption that is not directly sourced from Amazon's reported historical statements or a documented market source should be identified as a modelling assumption.

---

## Interlinked Financial Statements

One of the main objectives of the project was to connect the three financial statements. This is important because a business decision usually affects more than one statement at a time.

### Income Statement

The Income Statement calculates revenue, operating expenses, operating profit, financing costs, tax and net income. Revenue and cost assumptions influence operating profit, while financing costs and tax affect the movement from operating profit to net income.

Net income is important to the rest of the model: it flows into cash-flow calculations and, where included in the equity schedule, contributes to retained earnings.

### Cash Flow Statement

The Cash Flow Statement explains why the company's cash balance changes from one period to the next. It includes:

- Operating cash flow
- Changes in working capital
- Capital expenditure
- Debt and other financing movements
- Interest and tax effects, where modelled
- Dividends or other equity-related cash movements, where included

The resulting cash movement feeds the cash schedule and ending cash balance, which then links to the Balance Sheet. This link prevents cash from being forecast as an unrelated number.

### Balance Sheet

The Balance Sheet shows the company's assets, liabilities and shareholders' equity at the end of each period. It reflects the cumulative effect of the Income Statement, Cash Flow Statement and supporting schedules.

- **Cash** is linked to the cash-flow / cash schedule.
- **Fixed assets** are affected by capital expenditure and depreciation.
- **Debt balances** are affected by financing assumptions and debt movements.
- **Equity and retained earnings** are affected by profit and any equity or distribution movements included in the model.

The accounting relationship used to check the Balance Sheet is:

```text
Total Assets = Total Liabilities + Shareholders' Equity
```

A balance-check row is included in the Model tab. A near-zero difference indicates that the statement adds up mathematically, but it does not by itself prove that every assumption or formula is economically correct.

---

## Working Capital

Working capital represents cash tied up in day-to-day operations. The Input tab includes assumptions for receivables, inventory and accounts payable expressed in **days**. These assumptions help estimate the balances required to support forecast sales and operating activity.

- **Accounts receivable** represents amounts customers owe the business.
- **Inventory** represents goods held before they are sold.
- **Accounts payable** represents amounts owed to suppliers.

For example, an increase in inventory generally means more cash is tied up in stock. This can reduce operating cash flow even though inventory is recorded as an asset on the Balance Sheet.

```text
Higher Inventory → More Cash Tied Up → Lower Operating Cash Flow
```

Working-capital movements also affect FCFF. An increase in operating working capital is normally a use of cash and reduces FCFF; a decrease can release cash and increase FCFF. The sign convention in the existing formulas should be checked to make sure the movement is not subtracted twice or treated in the wrong direction.

---

## Capital Expenditure & Depreciation

Capital expenditure (capex) represents cash spent on long-term assets. It has two main effects in the model: it reduces cash in the period when the investment is made and increases the fixed-asset balance on the Balance Sheet.

Depreciation recognises the cost of those assets over their useful lives. It is an expense in the Income Statement and reduces the carrying value of fixed assets. However, depreciation is not itself a current-period cash payment, so it is added back when calculating FCFF.

```text
Capex → Fixed Assets → Depreciation → Operating Profit → FCFF → Balance Sheet
```

The workbook contains assumptions for the first year of depreciation and useful lives for existing and new assets. These inputs are used by the depreciation schedule to estimate the timing of depreciation expense.

> [!NOTE]
> The depreciation schedule needs particular attention: the previous workbook review identified potential incorrect cohort references in **Model rows 233–239**. Each new asset/capex year should be linked to the correct depreciation cohort. An incorrect reference can affect depreciation, fixed assets, operating profit, FCFF and enterprise value. This issue should be corrected in the existing schedule; a new schedule is not necessary.

---

## Debt, Interest & Cash

Debt assumptions influence financing balances and the cost of borrowing. The workbook includes assumptions for common equity and term debt, as well as interest-rate assumptions for cash, credit lines and long-term debt.

Financing costs affect profit before tax and net income. The debt schedule and Balance Sheet should therefore be consistent with the financing assumptions. When calculating the cost of debt for WACC, the selected finance-cost figure and debt balance need to be defined consistently. If finance costs are used as a proxy for interest expense, that should be stated as a modelling choice.

```text
Debt → Finance Costs → Profit Before Tax → Tax → Net Income
```

Cash is rolled forward through the cash schedule based on the modelled cash movements. The ending balance should link to the Balance Sheet and should not be independently hardcoded in the forecast years.

---

## Scenario Switches

A key feature of the model is its scenario-switch system. The Input tab includes **Best Case**, **Base Case**, **Worst Case** and **Off** settings for selected drivers. These switches allow the user to change the assumptions used by the forecast rather than manually editing individual forecast cells.

**Documented switch categories:**

- Sales growth
- Pricing increases
- Capital expenditure

The Input tab also contains other assumptions, such as inflation and working-capital days, which can be reviewed as part of scenario analysis. The extent to which each assumption changes automatically depends on the formulas already linked to that input.

The switches can be used to ask questions such as:

- What happens to forecast revenue if sales growth is lower?
- How does a different pricing assumption affect operating performance?
- How does higher or lower capex affect FCFF and the fixed-asset balance?
- How sensitive is enterprise value to the assumptions used in the forecast?

This turns the model into a scenario-analysis tool rather than a static forecast. After changing a switch, the user should verify that the intended forecasts, statements and valuation outputs update correctly.

---

## DCF Evaluation: FCFF, WACC & Enterprise Value

The DCF Evaluation tab converts the forecast operating results into an estimated enterprise value. The process starts with EBIT, calculates NOPAT, adjusts for depreciation, capital expenditure and working-capital movements to calculate FCFF, then discounts the cash flows to the valuation date.

### NOPAT and FCFF

**NOPAT** (Net Operating Profit After Tax) is calculated as EBIT multiplied by one minus the tax rate. It represents operating profit after estimated operating tax, before financing costs.

```text
NOPAT = EBIT × (1 − Tax Rate)
```

**FCFF** (Free Cash Flow to the Firm) estimates cash generated by the operating business after operating taxes and reinvestment needs, available to both debt and equity providers.

```text
FCFF = NOPAT + D&A − Capex − Change in Operating Working Capital
```

The workbook's actual formula uses the sign convention of its linked capex and working-capital cells. Because capex may already be represented as a negative cash-flow number, the signs should be checked rather than blindly subtracting the displayed value.

### WACC

**WACC** (Weighted Average Cost of Capital) is the discount rate used to convert future FCFF into present value. It combines the return required by shareholders and the after-tax cost of debt, weighted by the assumed proportions of equity and debt.

- **Cost of equity** is calculated using CAPM: `Risk-free rate + Beta × Equity Risk Premium`
- **Cost of debt** is estimated using finance costs relative to an appropriate debt balance, then adjusted for tax.
- **WACC** combines the cost of equity and after-tax cost of debt using their capital weights.

The risk-free rate, beta and equity risk premium shown in the workbook are **assumptions**, not values calculated from Amazon's operating statements. The model uses **book shareholders' equity** as part of the capital weighting because a market-capitalisation input is not included. This is a limitation to disclose; a market-based valuation would generally consider market equity value.

### Terminal Value and Enterprise Value

The terminal value estimates the value of cash flows after the detailed forecast ends in 2030. The workbook uses the **Gordon Growth Method**, which assumes that FCFF grows at a constant long-term rate after the forecast period.

```text
Terminal Value = 2030 FCFF × (1 + Terminal Growth) ÷ (WACC − Terminal Growth)
```

The terminal value is then discounted to the valuation date. Enterprise value is calculated by adding the present value of forecast FCFF to the present value of terminal value. Enterprise value represents the operating business value; it is not automatically the same as shareholders' equity value.

```text
Enterprise Value = PV of Forecast FCFF + PV of Terminal Value
```

---

## Output Page

The Output page is intended to give the reviewer a quick view of the workbook and direct them to the Input, DCF Evaluation and Model tabs. It should provide a concise summary rather than repeat every calculation.

For a stronger final presentation, the Output page can display:

- Enterprise value from the final recalculated DCF
- Forecast FCFF for 2026–2030
- WACC and terminal growth rate
- Selected scenario or switch settings
- A short interpretation of forecast cash-flow trends
- A note identifying the valuation as assumption-driven and educational

The Output page should only show figures that match the DCF Evaluation tab after the formula checks have been completed. It is useful to include a brief note that the valuation depends on the assumptions and is not a guaranteed prediction of Amazon's future value.

---

## Key Findings

> [!WARNING]
> The reviewed workbook currently calculates the following **preliminary** figures. They are included to explain the current model output and should not be presented as final until the formula and discounting issues described in [Model Review & Rectification](#model-review--rectification) have been corrected and the workbook recalculated.

| Metric | Current workbook result | Interpretation |
|---|---|---|
| 2025 WACC | ~8.96% | Calculated using the 2025 cost assumptions and capital weights in the workbook. |
| 2030 WACC | ~9.75% | Different from the 2025 WACC; the reason should be traced and the discount-rate approach made consistent or explicitly justified. |
| 2026 FCFF | ~−$4,577.5M | Negative FCFF can indicate that capex and working-capital needs exceed operating cash generation in that year; signs and drivers should be checked. |
| 2027 FCFF | ~$24,407.5M | The forecast produces positive cash flow under the selected assumptions. |
| 2028 FCFF | ~$10,932.2M | FCFF decreases compared with 2027, so the underlying operating, capex and working-capital drivers should explain the change. |
| 2029 FCFF | ~$24,375.8M | FCFF increases again under the model assumptions. |
| 2030 FCFF | ~$33,548.1M | Higher final-year FCFF increases the calculated terminal value. |
| PV of forecast FCFF | ~$62,223.7M | Present value of the detailed forecast cash flows under the workbook's current discounting approach. |
| Terminal value | ~$532,277.8M | Estimate of the operating cash flows beyond 2030, not cash received in 2030 alone. |
| PV of terminal value | ~$334,219.6M | Terminal value after discounting back to the valuation date. |
| **Enterprise value** | **~$396,443.2M** | Current DCF output; preliminary pending formula, discount-period and WACC consistency checks. |

Overall, the current calculation indicates that the terminal value makes a substantial contribution to enterprise value. This is common in DCF models because the business is assumed to continue operating after the explicit forecast period. It also means that the result is sensitive to **terminal growth**, **WACC** and the **FCFF forecast for 2030**.

The FCFF forecast varies considerably from year to year. That does not automatically mean the model is wrong, but the changes should be traceable to revenue, operating profit, capital expenditure, depreciation and working-capital movements. A reviewer should be able to follow those drivers through the workbook.

---

## Model Review & Rectification

The review identified several points to check before the valuation is described as complete:

1. **Depreciation cohort references:** formulas in Model rows 233–239 appear to reference the wrong rows/cohorts. Correct the links in the existing depreciation schedule and confirm the effect on depreciation, fixed assets, FCFF and valuation.
2. **WACC consistency:** the terminal value calculation appears to use the 2025 WACC, while forecast FCFF present values use the 2030 WACC. Decide on a consistent discount-rate method and document it.
3. **Discount period:** the 2030 discount period appeared to be 6. If the valuation date is the end of 2025, the periods should normally be 1 for 2026 through 5 for 2030. Confirm the valuation date and timing convention.
4. **FCFF signs:** confirm whether capex is stored as a negative number and whether the working-capital change is signed consistently. Incorrect signs can materially distort FCFF.
5. **Auxiliary enterprise-value formulas:** some supporting EV formulas appear inconsistent with the main DCF summary. The main summary calculates enterprise value as PV of forecast FCFF plus PV of terminal value; auxiliary calculations should be checked before use.
6. **Assumption sources:** label risk-free rate, beta, equity risk premium, tax and terminal growth as sourced inputs or assumptions. Add source and date where available if the model is used for a formal valuation.

The balance-sheet check in the reviewed workbook was reported as balancing across the forecast years, with only a negligible rounding difference in 2030. This is a positive internal consistency check, but the other formula checks are still necessary. No new schedules are required to address these issues; the priority is to correct and validate the existing calculations.

---

## Conclusion

This project demonstrates how historical financial data can be used to build a linked financial model and then estimate enterprise value through a DCF. The workbook combines historical statements, operating and financing assumptions, scenario switches, supporting schedules, forecast FCFF, WACC and terminal value.

```text
Historical Data → Assumptions & Scenarios → Linked Financial Statements → FCFF → WACC & Terminal Value → Enterprise Value
```

The main finding from the current version is that the model forecasts uneven FCFF across 2026–2030 and assigns a substantial portion of enterprise value to cash flows beyond 2030. This means that the result depends heavily on the final forecast-year cash flow, terminal growth and discount rate. The enterprise value should therefore always be presented alongside the assumptions that produce it.

The workbook is a useful educational modelling project because it demonstrates statement linking, scenario analysis and DCF valuation logic. However, the current valuation should be treated as **preliminary** until the depreciation cohort formulas, discount periods and WACC consistency have been checked and the workbook recalculated. The final Output page should then use the updated valuation and include the key assumptions, FCFF trend and a clear limitation note.

---

## Disclaimer

This model is a scenario-analysis and valuation exercise for educational purposes. It is **not** a guaranteed prediction of Amazon's future performance or an investment recommendation.
