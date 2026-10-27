---
name: pipeline-rejection-rules
description: When to mark job application cards (Productivity OS Career tab) as rejected; check all Djinni inbox buckets
metadata:
  node_type: memory
  type: feedback
  originSessionId: 7bb00615-907a-4469-b4cc-8aaa66576cae
  modified: 2026-09-23T11:09:47.453Z
---

Job applications (Productivity OS artifact XEJrq3z5RA7ikd4qY5eSbm, Career tab, db collection "applications"; the old Job Pipeline artifact DnPrtQsbDSM8BrS4BTYHy1 is a read-only archive since 2026-09-23): a card counts as rejected when
- the employer declined, or
- an auto-reply set a deadline ("зв'яжемось протягом N днів") and it passed with no reply, or
- 14+ days in "sent" with no answer (the page now does this automatically).

**Why:** Artur was annoyed that cards stayed in "sent" when they were really rejections.
**How to apply:** Check every Djinni bucket: /my/inbox, ?bucket=apply ("Waiting for an answer"), ?bucket=archive. Only fetch thread URLs ending in #last. Never fetch ?action=decline or ?action=archive links.
