# Proposal: daily caps per agent (for Dinis, via cl-6.conductor)

Status: NOT ADOPTED. Dinis, 27 Nov about 00:50 UTC, relayed by cl-6.conductor: "We don't need to put caps for now. Just want to capture everything." No caps or ceiling are in force; this file is kept as a record. Original status: PROPOSAL, nothing is in force. Money is Dinis's decision. Written 2026-11-26 by cl-6.accountant@PrompTugal.dinis.

## Basis and period read
- Source: cl-6.telemetry usage-2026-11-26-1115.json (raw URL via the Telemetry repository), as at 2026-11-26T11:17Z, 49 sessions (20 running, 27 idle, 2 archived).
- Figure: `cost_usd` from get_session, API-equivalent, cumulative per session. Deltas are since 2026-11-26T02:38Z, about 8.6 hours. I have not verified it against any invoice, and I cannot read board/budgets.json yet (website not attached); the figures for security ($30) and conductor ($50) come from Telemetry's note, unverified.
- Total $409.05 (Opus $210.88, Sonnet $198.17); delta $253.15 in about 8.6 hours.
- If that pace held for 24 hours it would be about $703 a day. That is a setup burst, not a steady state, so I do not treat it as a forecast. For comparison, the earlier estimate (an estimate, not counted) is $41.50 / $83.60 / $166.80 a day, low / mid / high.

## Where the money is
- Three Opus leads: infra $78.53 (delta $37.57), security $61.76 ($46.34), conductor $58.34 ($31.73). Together $198.63 total, $115.64 of today's delta (46% of it).
- dev (Sonnet) $16.74, delta $13.33. Every other Sonnet session is under $13 total.
- It is not clear whether cumulative cost includes days before 26 Nov; Telemetry's earlier reading was $155.90 at 02:38Z. Caps below are meant to be counted on the delta since 00:00 UTC of the day, which needs Telemetry to report it.

## Proposed caps (API-equivalent USD per agent per UTC day)
| Agent | Cap | Note |
|---|---|---|
| conductor | 50 | as in the budgets file, per Telemetry |
| security | 30 | as in the budgets file, per Telemetry; it is already over on cumulative cost |
| infra | 40 | no entry today |
| dev | 15 | busiest Sonnet |
| other Opus (router, decisions, security@dinis, strategy, helm) | 5 each | idle most of the time |
| every other Sonnet agent | 8 each | today's average is under half of this per agent |
| All agents together | warn at 170, stop-and-ask at 300 | 170 is the estimate's high; 300 is a ceiling, not a target |

Caps are proposals to test against Telemetry's daily deltas for a week, then revise. I would rather set them low and raise them on evidence.

## What a cap stops
At the cap the agent finishes the step it is on, writes its status and does not take another wake that day. I cannot stop a session or a wake myself (the grant forbids it): I tell cl-6.conductor, who tells cl-6.maestro. A cap never deletes work or history.

## What is cut first if the aggregate ceiling is hit
1. Sonnet section and data agents with no shipping change in hand (weather, travel, events, videos, signals, bulletins and similar).
2. Idle Opus sessions kept only for reference.
3. dev and the checker/reviewer pair last, because the iOS app and the site refresh depend on them.
4. conductor and security last of all; Dinis decides before either is cut.

## Open
- Needs Dinis's yes on every number.
- Needs Telemetry to report the daily delta from 00:00 UTC per agent.
- Needs board/budgets.json (website attach) to reconcile with the figures already there, and the 24 sessions with no entry.
