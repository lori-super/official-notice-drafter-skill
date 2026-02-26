---
name: official-notice-drafter
description: Use when drafting Chinese formal organizational notices from rough requirements or bullet points, especially when a complete notice is needed with title, recipients, body, signature, and date in strict official tone.
---

# Official Notice Drafter

## Overview

Draft complete Chinese formal notices from rough user input. Ask follow-up questions first when required details are missing.

## Workflow

1. Parse input in either mode:
   - Natural language request
   - Structured fields (title/topic, time, scope, actions, deadline, etc.)
2. Normalize into one common field set.
3. Check required fields. If any required field is missing, ask concise follow-up questions before drafting.
4. Draft a full notice in strict official tone.
5. Run a final quality check before sending.

## Required Fields Before Drafting

Do not draft until all required fields are clear:
- Notice purpose/topic
- Time arrangement (start/end/deadline)
- Scope/affected units or audience
- Execution requirements (what each unit must do)
- Sending organization (default available)
- Date (default to current date unless user overrides)

Default recipients when the user does not provide any:
- `各分、支行，省行营业部：`

Default signature when the user does not override:
- `科技与产品管理部`

If contact details are missing:
- Do not add contact lines unless the user explicitly requests contacts.

## Output Contract

By default, return a complete notice with this structure:

1. Title (normally `关于XXX的通知`)
2. Recipients line
3. Opening paragraph (background + purpose)
4. Main sections (use Chinese numbering like "I, II, III" equivalent: "one, two, three") with clear actions and deadlines
5. Optional closing reminder sentence
6. Signature line
7. Date line in Chinese date format

## Style Rules

- Always write the final notice in Chinese.
- Use strict official circular tone; avoid colloquial language.
- Make responsibilities and deadlines explicit and verifiable.
- Keep numbering consistent and hierarchical.
- Keep wording concise but complete.

## References

- For intake prompts and missing-field questions, read `references/intake-checklist.md`.
- For reusable wording and section patterns, read `references/notice-style-guide.md`.

## Quick Start

When a user asks for a notice:
1. Extract known fields from the request.
2. Ask for any missing required fields.
3. Generate the complete notice in one pass.
4. Offer one revision pass focused on precision (time, scope, wording).
