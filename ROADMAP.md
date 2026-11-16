# RelayForge roadmap

This roadmap records the direction and the current evidence. The public default branch contains the original design; the prototype and experiments described as local are not yet published on that branch.

## Current local prototype

- SQLite task records, deterministic file comparison, local-model chat routing, and Python code proposals with an experimental isolated test runner.
- Optional Parcimonia/Tesseract OCR with bounded image preprocessing and traceable reports. A sparse-text mode uses Tesseract PSM 11; it is not a separate learned region detector.
- Experimental chat selection of verbatim OCR excerpts, checked against text and word evidence. A single local model/document scenario returned the requested brand and date with source positions. OCR and semantic relevance still require review.
- Experimental ShardJEPA adapter: the tested mean-pool predictor is deterministic, not an evidenced trained model.

These items describe local work only. A successful task status does not prove OCR correctness, code correctness or production readiness.

## Priorities

1. **Scene OCR and layout.** Evaluate actual region detection and recognition on independent, fully annotated photographs; measure detection, transcription, reading order, false positives and runtime. In an exploratory 10-scene sample, sparse mode with upscaling matched 2/59 reference words, the same aggregate as the previous block mode. Compare other detectors before claiming improvement.
2. **Cited document answers.** Test multiple documents, languages and questions; cover missing and ambiguous answers, incorrect OCR, irrelevant but valid quotes, repeated excerpts and prompt injection. Preserve the original image hash, transformation, report hash and source coordinates. Add robust handling of tables and multipage documents.
3. **French chat and routing.** Expand real-model evaluations for ambiguous requests, multi-step tasks and failure reporting. Preserve the user's requested conditions and distinguish proposed, executed and verified results.
4. **Safe code workflow.** Improve multi-file context and candidate review, test broader languages and independently evaluate isolation boundaries. Keep source changes explicit and reviewable.
5. **ShardJEPA evaluation.** Compare a genuinely trained candidate against last-value and mean baselines on held-out sessions and machines, using only features known before execution. Initially keep placement recommendations advisory.
6. **Measurement and scheduling.** Record per-task queue and execution time, per-process CPU and memory, failures and model identity. Repeat varied loads on both machines; do not infer production readiness or end-to-end savings from component timings alone.
7. **Additional workers.** Consider local document search with citations, PDF and table extraction, folder comparison, speech transcription and local vision after the preceding contracts and evaluations are in place.

## Release gates

- Reconcile and review the existing local changes, publish a coherent candidate through the repository's normal review process and retain reproducible evidence.
- Specify supported inputs, limits, failure modes, dependencies and privacy boundaries for each worker.
- Run automated tests plus representative real end-to-end evaluations; report corpus limitations and failures.
- Compare with a single-model baseline before making efficiency, accuracy or resource-saving claims.
