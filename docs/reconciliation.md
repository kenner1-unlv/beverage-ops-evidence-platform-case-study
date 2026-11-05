# Reconciliation Walkthrough — Fictional Records

This example is newly invented for the case study. It is separate from the
synthetic screenshot dataset and contains no operational records.

| Source row | Reference | Product | Evidence date | Signed source cases | Interpretation |
|---|---|---|---|---:|---|
| Sales movement | DEMO-101 | SAMPLE-750 | Oct 1 | -10 | 10 physical cases shipped |
| Product invoice | DEMO-101 | SAMPLE-750 | Oct 2 | +10 | 10 cases invoiced |
| Sales movement | DEMO-102 | SAMPLE-750 | Oct 3 | -4 | 4 physical cases shipped; no invoice supplied |
| Product invoice | DEMO-103 | SAMPLE-750 | Oct 4 | +6 | 6 cases invoiced; no shipment supplied |

The first two rows match by the documented reference/product/quantity rules.
The other rows remain visible exceptions. For this selected evidence, physical
shipments total **14 cases** on movement dates; invoice evidence totals **16
cases** on invoice dates. Those totals answer different questions and should
not be silently forced to agree.

This toy set has two matched source rows among four eligible unique rows, so
its illustrative reconciliation rate is **50%**. It says nothing about whether
all relevant files were received. The missing counterpart is *unavailable
evidence*, not a measured zero. Real source versions, returns, transfers,
credits, period boundaries, and operator reviews require their own explicit
treatment in the application.

The operational system retains import, file, and row lineage so a reviewer can
trace a displayed fact or exception back to its source without changing the
raw observation. This public walkthrough illustrates the rule; it does not
publish that private evidence.

## Warehouse code variants and rounding

The warehouse may assign different source codes to units the business views as
one commercial product. Those codes serve a stock-handling purpose; they are
not errors to strip from raw evidence. Family and confirmed-size assignments
allow inventory to be summarized at a useful business grain. For **sales
reconciliation across source codes**, the operator must also record a separate
reviewed SKU-equivalence decision. Reconciliation clears exact-code matches
before comparing only the remaining cross-code quantity under a shared
transaction reference. Original SKU labels and source rows remain visible.
The rule does not fuzzy-match arbitrary suffixes.

A small documented physical-case tolerance handles a limited export-rounding
variance when comparing eligible shipment and invoice quantities. Both original
quantities and the variance remain visible. It does **not** reconcile a reported
inventory snapshot to a computed inventory ledger; that ledger is not part of
the current case-study claim.
