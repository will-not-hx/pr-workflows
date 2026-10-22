---
name: reading-pr-comments
description: Use when asked to read, explain, discuss, or walk through comments or review threads on a pull request, such as "read the comments on PR #123". Explain each concern in junior-friendly language, assess it against the current code, and suggest a solution one thread at a time. Reading comments does not authorize replies or PR changes.
---

# Reading PR Comments

Help the user understand review feedback and make their own decision before anyone acts on it.

## Read the current conversation

- Fetch the live PR head, review threads, review summaries, and relevant general comments. Group replies with their parent comment. Distinguish a new finding from a reply to an old one, and note resolved or outdated threads when that affects the answer.
- Read the changed code and nearby callers, schema, tests, or documentation needed to judge the specific claim. A comment may describe an older commit; check whether the current head already addresses it. Do not treat a bot finding or reviewer suggestion as established fact.
- Say what you could not check. When the concern depends on runtime data, a database plan, or an external contract, distinguish what the code proves from what still needs measurement or confirmation.

## Explain one thread at a time

When several threads are available, give a short index of the topics, then explain the first relevant thread and stop. Continue with the next only when the user asks. If the user names a thread or asks for all threads together, follow that choice.

For each thread, link the comment and explain:

1. What the reviewer noticed, in plain words. Define any technical term that matters to the decision.
2. Why it might matter, using a small concrete example or mental model when useful.
3. Whether the concern holds for the current code, with the evidence and any uncertainty.
4. A suggested solution or next check, including its practical tradeoff. Say when no code change is justified.

Keep the explanation useful to a junior engineer. Do not merely translate jargon into different jargon, and do not frame a possible issue as a confirmed defect.

At the end of each analysis, ask whether the user accepts or rejects the suggested solution or next check. Then offer to move on to the next comment when they are ready, and wait for their response before continuing. For example: “Do you accept or reject this suggestion? When you’re ready, I can move on to the next comment.”

## Keep discussion read-only

Requests such as "read the comments", "the bot commented", or "let's go through them" authorize reading and discussion only. Do not post replies, resolve threads, react, edit PR descriptions, push code, or change files as part of that request. Previous permission to reply to different threads does not authorize replies to new ones.

If the user later asks for a code change, make that change within its requested scope; it still does not authorize a review reply. If the user wants a reply posted, prepare the exact proposed text, ask for approval to post it, and send it only after approval for that thread. The user may instead choose to reply themselves.
