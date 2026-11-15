# Architecture notes

RelayForge is a design proposal. Components and interfaces below are not implemented.

A gateway maps a user request to a structured task. The harness checks policy, selects a deterministic worker or an appropriate model, and records results and evidence. A chat model can then present the outcome. Memory and model lifecycles are separate concerns; unloading and reloading models must be measured on target hardware.

Tasks and results should be versioned, validated, traceable, and bounded by explicit permissions. The example is illustrative, not a finalized protocol. References to shared artifacts need access control and must remain resolvable across restarts.

Potential Parcimonia and Inception integrations are exploratory. No dependency or compatibility is implied. Benchmark actual task success and total resource use against a single-model baseline before drawing conclusions.
