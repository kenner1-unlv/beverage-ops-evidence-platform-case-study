# Regions, Product Mix, and Standard-Cost Analysis

The commercial views answer different questions from the same accepted source
evidence. They keep the unit, date basis, and missing-data limits visible so an
executive can compare markets and products without treating a plausible chart
as a complete accounting result.

## Configure geography, then drill down

An operator assigns states to named regions. Unassigned states remain visible;
the application does not guess a region. A shipment destination comes from a
supported matching product invoice. If a unique valid state cannot be
attributed, the activity stays under **Unknown destination**. A regional view
can then drill from region to state, observed warehouse, product family, and
source SKU.

The map can display **physical cases** (the flat cases shipped), **9L
equivalents**, or eligible **product-invoice revenue**. These are separate
measures. Physical cases come from dated outbound sales movements. A 9L
equivalent is calculated only when the pack conversion was confirmed; cases
without one remain in the physical total and are reported as missing from the
9L measure. Invoice revenue uses its own invoice date and is not cash received.

## Product mix can tell two different stories

Product mix compares each configured family's share of physical shipment cases
with its share of eligible product-invoice dollars. Those percentages can differ
because prices differ and because shipment and invoice dates need not land in
the same period. Selecting a family reveals region and state breakdowns.
Negative invoice amounts remain signed in totals; a pie slice uses positive
amounts only because a negative slice has no meaningful area.

The following table is **entirely fictional**. It assumes both source sides
are available, all pack conversions are confirmed, and the invoice cases happen
to equal shipped cases within this illustrative period.

| Fictional family | Shipped physical cases | Confirmed 9L factor per case | Shipment 9L equivalents | Product-invoice revenue |
|---|---:|---:|---:|---:|
| Sample Family A | 60 | 0.5 | 30 | $7,200 |
| Sample Family B | 40 | 1.0 | 40 | $2,800 |
| **Total** | **100** | — | **70** | **$10,000** |

Family A is **60% of physical cases** but **72% of invoice revenue**. Its 30
9L equivalents are about **42.9% of confirmed shipment 9L volume**. The three
shares answer different questions; none replaces the others.

## Standard cost and margin

The operator maintains a complete standard-cost profile per product family and
bottle size, expressed **per physical case**. Component costs distinguish an
explicit zero from an unknown amount. When the profile is complete, standard
COGS for an invoice line is its signed invoiced physical cases multiplied by
that family-and-size cost. Standard-cost gross profit is eligible invoice
revenue less standard COGS. A missing quantity, mapping, size, or cost makes
the affected aggregate cost and gross-profit measure unavailable, with
coverage disclosed; it is not silently treated as zero.

For a separate **fictional** illustration using the same two families, assume
60 invoiced cases of A with a complete $50 per-case standard cost, and 40
invoiced cases of B with a complete $35 per-case standard cost:

| Fictional family | Invoiced physical cases | Standard cost per case | Standard COGS | Product-invoice revenue | Standard-cost gross profit |
|---|---:|---:|---:|---:|---:|
| Sample Family A | 60 | $50 | $3,000 | $7,200 | $4,200 |
| Sample Family B | 40 | $35 | $1,400 | $2,800 | $1,400 |
| **Total** | **100** | — | **$4,400** | **$10,000** | **$5,600** |

The illustrative total standard-cost gross margin is **56%**
(`$5,600 / $10,000`). It is not operating income, audited profit, cash
collected, or a claim about actual company margin. The current saved cost
profile may be applied to a selected historical inventory snapshot, but that
does not reconstruct the cost profile that existed on the snapshot date.

The separate inventory-value view can estimate on-hand, allocated, or available
physical cases by warehouse and family. It does not add allocated and available
to on-hand, and it keeps bailment, unclassified, and excluded locations in
their distinct scopes. Per-case standard cost is applied to physical cases,
not to 9L equivalents.
