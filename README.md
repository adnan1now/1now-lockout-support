# 1Now Lockout Support — Prototype

A small working prototype built for the 1Now Client Success & Support assessment.

## The Problem

A 1Now operator has a customer who gets locked out of a rental vehicle during an
active rental. The support agent needs to quickly collect the right details,
figure out how urgent the situation is, and know exactly what to do next —
including cases that don't fit a simple pattern (e.g. a lockout caused by
something unusual, not just a lost or locked-in key).

## The Solution

A single-page web tool that walks a support agent through:

1. **Intake** — collect renter, booking, and situation details.
2. **Triage** — simple rule-based logic decides priority (Urgent / High / Standard)
   and a recommended next action.
3. **Edge case handling** — if the cause doesn't fit a known category ("Other"),
   the agent adds a short description and the case is routed to **Manual Review**
   instead of an automated (and potentially wrong) recommendation.
4. **Resolution** — the agent can mark the case **Resolved**, closing the loop
   from intake to resolution.

## Rules used for triage (kept intentionally simple)

- Unsafe vehicle location → **Urgent**
- Keys lost → **Urgent**
- Time-sensitive deadline → priority increases by one level
- No spare key and no self-service option → **High**
- Key fob/app issue with a possible retry → **Standard**
- Cause reported as "Other" → routed to **Manual Review**, not auto-decided

## Scope

This prototype intentionally covers one flow only: intake → triage → action →
resolution, for the vehicle lockout scenario. It uses mock data only — no real
customer data, no backend, no external APIs, and no authentication.

## How to run it

No installation needed.

1. Download `index.html` from this repo.
2. Open it in any browser (double-click the file, or drag it into a browser window).
3. Fill in the form and click **Submit & Triage** to see the priority and
   recommended action.
4. Click **Mark Case Resolved** to close the case.
5. Click **Reset** to try another scenario.

## Built with

Built using Claude (Anthropic) — planning the flow and edge cases first, then
generating and iterating on the working code.
