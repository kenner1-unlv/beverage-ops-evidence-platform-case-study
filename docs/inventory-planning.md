# Inventory Planning — Historical-Rate Baseline

The current view compares a dated inventory observation with observed outbound
physical cases. It groups by supply location, product family, and bottle size.
Customer shipments and outbound warehouse transfers both deplete a location;
receipts, inbound transfer legs, and adjustments do not contribute to outbound
burn. Conflicting movements are withheld. A selected inventory snapshot is
shown separately and is not silently rolled forward to the end of the rate
window.

For a selected window of `D` days:

```text
weekly outbound rate = eligible outbound physical cases × 7 / D
estimated weeks of supply = available snapshot cases / weekly outbound rate
target cases = weekly outbound rate × configured target weeks
gap to target = available snapshot cases - target cases
```

When the weekly rate is zero or unavailable, weeks of supply is unavailable;
the display must not invent a stockout date.

## Fictional calculation

The following values are invented solely to demonstrate the method. Consider
one active product family at one main warehouse with **70 available physical
cases** and an operator-configured **8-week target**.

| Selected window | Customer shipment cases | Outbound transfer cases | Total outbound cases | Average cases/week | Estimated weeks of supply |
|---|---:|---:|---:|---:|---:|
| 30 days | 75 | 15 | 90 | 21.0 | 3.33 |
| 90 days | 150 | 30 | 180 | 14.0 | 5.00 |
| 180 days | 255 | 45 | 300 | 11.67 | 6.00 |

For the 90-day basis, `180 × 7 / 90 = 14` cases/week. Then `70 / 14 = 5`
weeks of supply. An 8-week target is `14 × 8 = 112` cases, so the warehouse
is 42 cases below that configured target. This comparison is a planning signal,
not an automatically generated order.

The application also highlights active items below a fixed **10-week** supply
threshold for inspection. Exactly 10 weeks does not trigger it. Cycling-out
stock remains visible but does not create replenishment pressure. A bailment
location may be informational because its control state initiates replenishment.

## What remains unvalidated

The selectable 30/90/180-day windows and fixed 10-week inspection threshold
were chosen as transparent baseline rules. They have not been calibrated by a
documented backtest against actual operating outcomes. Family target weeks are
operator configuration, not a universal optimum. The calculation does not
model seasonality, future inbound inventory, routing, safety stock, or an
expected inventory ledger. Before using it as a production purchasing policy,
the thresholds and rate windows need outcome review with the operator.
