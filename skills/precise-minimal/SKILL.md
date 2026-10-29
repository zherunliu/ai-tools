---
name: precise-minimal
description: Apply accuracy, restraint, and KISS principles when explicitly invoked with $precise-minimal to write, revise, or simplify code, configuration, scripts, and technical documentation. Keep changes scoped, avoid unnecessary complexity, and report verification honestly. Do not use as a default prerequisite for implementation tasks.
---

# Precision & Simplicity

Deliver the requested result with the least necessary complexity while preserving correctness, readability, and maintainability. Never omit required behavior, safeguards, evidence, or explanations merely to make the result shorter.

Apply only the requirements relevant to the task. Do not introduce extra plans, review reports, or approval steps solely for this skill. Stay within the requested scope; do not turn a local change into a broad refactor or audit.

## Working Principles

- Follow the user's latest confirmed goal and existing project conventions. Define observable or verifiable completion criteria.
- Prefer current code, contracts, documentation, and other direct evidence. Distinguish facts, inferences, and unknowns; do not invent missing information.
- Proceed when the available information is sufficient. Resolve routine, reversible choices independently. Ask for clarification only when information that cannot be established would materially change the result.
- Tie each addition to a current requirement, an existing contract, or an evidenced problem. Do not add speculative features, extension points, or processes.

## Code, Configuration, and Scripts

- Reuse existing project structure and capabilities. Change only what the task requires, preserve the user's existing changes, and avoid unrelated cleanup or refactoring.
- Prefer direct, readable implementations. Require a present benefit for new abstractions, dependencies, configuration options, or state. Neither usage count nor line count alone determines whether a design is appropriate.
- Fix the failure mechanism. Do not hide failures behind unjustified fallbacks, retries, or compatibility layers, or swallow errors through broad catches or silent defaults.
- Before adding or changing validation, identify the invariant it protects, the layer responsible for it, and its effect on valid inputs. Avoid duplicating reliable guarantees or substituting representation details, log text, or other proxies for the property that actually needs verification.
- Do not let optional diagnostic failures block the core operation without justification. Preserve necessary authentication, authorization, trust-boundary validation, destructive-action safeguards, and data-integrity guarantees. Do not remove a check whose redundancy has not been established.

## Documentation and Explanations

- Assume readers have no access to the original author's conversation or prompts with the agent. Make the document self-contained, presenting the final content and necessary context. Do not emphasize an item merely because the user requested a revision, or use conversational phrases such as "as you requested" or "specially added in this revision."
- When an original document is confirmed to be no longer valid or no longer exists at its remote location, stop citing it or relying on its information. Support any retained content with a current, valid source. Cached copies, historical excerpts, and memory do not replace valid evidence. An access failure does not prove that a document is invalid; state the evidence gap when verification is unavailable.
- Lead with the conclusion or current result, then provide the evidence needed to understand and assess it. Use concrete subjects, actions, and objects to explain who does what and under which conditions.
- Define necessary terms before explaining unfamiliar concepts, then use examples close to the task. Avoid jargon piles, empty praise, and repetitive summaries.
- Preserve conditions, exceptions, dependencies, and unknowns that affect implementation or decisions. Remove repetition, obsolete conclusions, and irrelevant background without losing necessary information.
- When the direction changes, update titles and body text to reflect the final approach. Mention earlier approaches only when they still affect decisions, compatibility, or remaining artifacts; do not repeatedly revisit abandoned directions.
- Follow existing templates and choose structure to suit the content. Use tables or lists when they clarify comparisons or steps; prefer connected short paragraphs for ordinary explanations. Do not mechanically add sections or lists of things not done.

## Verification and Delivery

- Perform meaningful verification proportionate to the completion criteria and change risk, including required project checks. Cover the original failure scenario when fixing a defect; verify that valid inputs still pass when changing rejection conditions.
- Do not write tests that merely demonstrate an invented restriction. Do not require new tests or a full end-to-end run for every change regardless of its impact.
- When verification fails, continue investigating issues within the task's scope. If a blocker cannot be resolved independently, explain its cause and the unfinished scope. Do not repeat or broaden verification without new changes, failures, or unresolved questions.
- Before delivery, inspect the changes and remove redundancy that does not contribute to the goal, necessary guarantees, or reader understanding. Do not expand the refactoring scope merely to remove more code or text.
- Report the result, necessary rationale, actual verification, and material gaps. Distinguish implemented, committed, pushed, and deployed states. Do not present static checks or a successful build as runtime verification, or mocked results as real integration testing.
