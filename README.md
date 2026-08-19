# Avela Runtime

> **The model proposes. The Runtime decides what becomes real.**

Avela Runtime is an independent AI systems project exploring a strict boundary between **probabilistic model decisions** and **authority over live system state**.

An AI model may reason, choose, refuse, fail, abstain, or propose an unsafe action. Those outputs remain proposals. They do not become authoritative state merely because the model produced them.

This public repository is intentionally an **evidence surface, not a source release**. Production implementation, evaluation harnesses, internal architecture, and infrastructure code are not published here.

---

## Recorded autonomous evaluation

A live language model was evaluated without receiving an expected action or expected Runtime decision.

```text
Provider: OpenAI
Model:    gpt-5.4-mini

Concurrency ladder: 1 -> 10 -> 25 -> 50 -> 100

Runtime attempts:               199
Model generation failures:      0
Internal errors:                0
Partial commits:                0
Integrity failures:             0
Rollback success:               100.000%

Autonomous boundary coverage:   7/7 PASS
Goal-pressure gauntlet:         6/6 PASS
Runtime regression invariants:  8/8 PASS
Shared-world contention:        PASS
                                1 committed / 4 stale rejected

OVERALL:                        PASSED
```

**Answer key sent to model:** NO  
**Expected Runtime decision sent:** NO

Coverage was counted only from authority boundaries actually reached by autonomous model choices. Separate deterministic probes could not fill missing autonomous coverage.

[Read the recorded autonomous run →](terminal_output.txt)

[Inspect the structured evidence →](summary.json)

---

## 20-second recorded proof

A compact recorded scenario shows the same system boundary in an immediately inspectable form:

- a model proposal is accepted;
- another proposal requests authority it does not possess and is rejected;
- authoritative state remains unchanged after the rejected attempt;
- a subsequent valid proposal is admitted.

[Read the recorded proof →](ATTENTION_PROOF_OUTPUT.txt)

---

## What the evidence supports

For the recorded provider, model, worlds, and concurrency, the published artifacts show autonomous model decisions remaining proposals subject to independent Runtime authority.

The recorded evaluation includes successful transitions, rejected actions, rollback cases, stale-state contention, abstention, and adversarially relevant proposals.

Across 199 Runtime attempts, the recorded run reported:

```text
0 internal errors
0 partial commits
0 integrity failures
100% rollback success
```

The structured evidence is published so the recorded results can be inspected directly rather than accepted as prose claims.

---

## Evidence boundary

This repository does **not** publish the production Runtime implementation.

It does **not** publish the autonomous or deterministic evaluation harnesses.

It does **not** publish internal state, transaction, concurrency, provider-integration, rollback, audit, optimization, or admission machinery.

The published artifacts are recorded evaluation evidence. They are not presented as production certification, universal AI-safety proof, or evidence about models, workloads, environments, or failure modes that were not executed.

---

## Public artifacts

### [`terminal_output.txt`](terminal_output.txt)

Human-readable output from the recorded autonomous LLM → Runtime stress evaluation.

### [`summary.json`](summary.json)

Machine-readable structured evidence from the same recorded run, including configuration, coverage, Runtime outcomes, contention results, and explicit claim boundaries.

### [`ATTENTION_PROOF_OUTPUT.txt`](ATTENTION_PROOF_OUTPUT.txt)

A compact recorded scenario showing accepted and rejected model proposals and their observed effect on authoritative state.

---

## Thesis

Avela does not require probabilistic intelligence to also be the authority that determines system reality.

The model can reason.  
The model can choose.  
The model can fail.  
The model can propose.

**The Runtime decides what becomes real.**
