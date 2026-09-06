# State, Prototype, and Re-entry

## What to show and retain

Ordinary responses show only new, materially changed, or reopened F/U/D. Omit
empty tables. When an active U is resolved, show the resolved-U transition
once, then remove it from active U and absorb the result into F or D. Show a
consolidated snapshot only at a real plan/commitment/handoff boundary or when
the user explicitly requests one.

State is optional and conditional on multi-turn recovery value and write
access. Start from available task state or chat/handoff resume capsule when
either is provided; no fixed home path is required for a new run. Reuse the
same concise state file during a run when it is available. An existing run
that already uses `~/.codex/state/brainstorming` may reuse that legacy
namespace; do no bulk migration. The legacy namespace is reused only when an
existing run already uses it. If persistence is unavailable, use a concise
chat/handoff resume capsule containing the current frame, material F/U/D
delta, selected route, unresolved boundary, and next validation. Never store
raw transcripts, secrets, credentials, or unrelated private data.

## Prototype boundary

A prototype requires explicit user selection before construction. Once the
user explicitly selects a bounded prototype and has already granted that
scope, proceed in that turn; do not ask for approval again. If the selected
prototype names an artifact count and type, create exactly the selected
artifact count and type in the task scratch folder and no additional artifact.
A prototype must be local, bounded, reversible, observation-led, and
disposable, with a clear observation and stop condition. It cannot be used for
external sends/forms, auth or secrets, money, publication/deploy, or
destructive/irreversible effects. Return its material observation to the loop;
do not treat building it as approval or completion.

## Evidence-driven re-entry

On re-entry, compare expected versus found evidence, record only the material
delta F/U/D, and choose the next route. A changed observation can reopen a
resolved item or create a concrete U; absorb resolved items into F or D rather
than keeping duplicate U rows. Do not require an implementation notes file or
introduce a lifecycle manager. Preserve the smallest recovery capsule needed
to continue, and stop with the incomplete boundary when evidence or authority
is still insufficient.

The Skill excludes quiz, a mandatory explainer artifact, mandatory
`.agent/unknowns` files, Python harnesses, telemetry, evidence graphs, gates,
queues, and model launchers. The old approximately-three-question heuristic is
superseded and must not appear as a rule.
