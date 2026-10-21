---
name: explaining-pr-changes
description: Use when an engineer asks to understand or walk through code changes in a PR. Trace the current diff and relevant code in runtime order, define unfamiliar terms, and explain follow-ups plainly. Use reading-pr-comments for reviewer feedback.
---

# Explaining PR Changes

Help the engineer build an accurate mental model of the changed code. Treat this as a code walkthrough, not an unsolicited review or a request to change the PR.

## Read the current change

- For a PR link or number, inspect its current head, base, changed files, and diff. Do not rely on the PR description or an old local checkout as proof of current behavior.
- Read changed code and only the surrounding callers, callees, types, and tests needed to trace the behavior. Identify what the change does itself and what it delegates to another module or library.
- If the PR or source is unavailable, say what you can see and explain from the material provided without presenting assumptions as facts.

## Explain progressively

- Begin with a short mental model of the change and a simple flow from the caller through the changed code to its outcome.
- Walk through behavior in runtime order. Explain setup separately from what happens when a request or function is later used. For each important function or callback, say who calls it, when it runs, what it receives, and what it returns or changes.
- Use the actual names and expressions in the code. Define unfamiliar terms before relying on them. Distinguish concepts that share a name but live at different layers, such as an incoming framework request and a separate outgoing HTTP request, or a service acting as a network client and a client-library object.
- When asked about a line, first explain what that line does literally, including relevant branches, operators, promise behavior, or error flow. Use an analogy only as a supplement.
- For asynchronous or concurrent code, identify which promise or timer belongs to each caller, whether underlying work is cancelled or continues, and what cleanup changes. Use a short fictional timeline when it makes the sequence clearer.
- Answer follow-up questions directly and carry forward the mental model already established. If the explanation is still confusing, restate the roles with a concrete, fictional example instead of repeating the same phrasing or restarting the full walkthrough.

## Evidence and boundaries

- Link to the current PR files and relevant lines when available. Separate behavior visible in code from inference and from anything that remains unverified.
- Keep the explanation read-only. Do not edit code or PR text, post comments, or run tests unless the user asks.
- Do not turn a request to understand a PR into an unsolicited review. If the user asks about reviewer feedback, use the review-comment workflow.
