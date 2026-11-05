# Development Workflow: Spec Kit and Owner Review

The engineering method was part of the work, not just a documentation layer
added afterward. The owner supplied the operating definitions: what counts as
a shipped case, how invoice evidence differs, which gaps remain visible, and
what a number may support. Agent-assisted implementation worked within those
decisions; the owner retained specification, review, and release authority.

For a representative feature, the private development record followed this
sequence:

1. Write the operator decision and evidence requirements in a feature
   specification, including missing, conflicting, duplicate, signed, and
   period-boundary scenarios.
2. Review the specification and approve its business semantics before
   implementation.
3. Produce a technical plan, data and interface contracts, ordered tasks, and
   a consistency analysis.
4. Implement bounded slices with independent arithmetic checks and tests that
   exercise realistic import, persistence, and API behavior.
5. Compare the result with acceptance scenarios, resolve material review
   findings, and record release evidence and remaining limits.

One traceable private example is the canonical sales-checkpoint feature. Its
record contains a reviewed specification, plan, contracts, tasks, analysis,
tests, and verification notes. This public case study describes the process;
it does not copy the private artifacts or imply that every small fix used the
full sequence.

The same discipline shapes this case study: a local constitution, spec, plan,
tasks, claim ledger, and file-level disclosure review precede any public
transfer. The public narrative is shorter than the private engineering record
because company data and internal details remain private.
