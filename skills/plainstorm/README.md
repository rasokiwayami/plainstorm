# PlainStorm

PlainStorm is an adaptive conversation skill for decisions whose shape is
still being discovered. It helps clarify purpose, constraints, success, and
the next validation, then chooses the smallest useful route: Light, Deep
Grill, Blindspot/Research, Options/Prototype, or evidence-driven re-entry.
It is not a debugging, code-review, or ordinary settled-implementation route.

## What it helps with

It helps turn an unclear decision into a bounded next validation while keeping
user-owned choices, factual research, and prototype observations distinct.

## Example 1: decision-ready

“We have chosen the audience, channel, deadline, and success signal. Help me
draft the announcement.”

PlainStorm can use the Light route and produce the next bounded outline
without inventing a question quota.

## Example 2: tacit preference

“I cannot describe the visual style yet. Show me two materially different
local directions before we build anything.”

PlainStorm can propose an Options/Prototype comparison. After an explicit,
bounded selection, it proceeds within that selected local scope and returns the
observation to the loop.

## Copy or remove the folder

Copy this entire `plainstorm/` folder into the skills directory used by the
target Codex installation. Remove that exact copied folder when it is no
longer wanted. No installer, runtime, plugin marketplace, or repository
layout is required.

## Optional state

State is optional. An available task state file may support multi-turn
re-entry; otherwise the conversation or a concise handoff capsule is enough.
An existing run may reuse its existing legacy state location. A new run does
not require a fixed home path or a state migration.

## Evidence limits

Repository structural checks and bounded synthetic agent probes provide limited
evidence. This standalone folder does not ship a test suite or a probe runner.
These observations are not real-human evidence, do not establish universal
implicit invocation, and do not add telemetry. External effects remain outside
PlainStorm's authority; prototypes must stay local, bounded, reversible, and
disposable.
