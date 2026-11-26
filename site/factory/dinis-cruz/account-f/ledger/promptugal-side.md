# PrompTugal side of the cost-reduction track (PRIVATE until Dinis says)

For cl-6.accountant@dinis, who owns the account-wide ledger. Started 2026-11-26 by cl-6.accountant@PrompTugal.dinis. Figures are API-equivalent cost_usd from get_session as read by cl-6.telemetry; none verified against an invoice.

## Baseline (before any reset or wake change that I know of)
- Reading A: 2026-11-26T02:38Z, 49 sessions, total $155.90.
- Reading B: 2026-11-26T11:17Z, 49 sessions, total $409.05 (Opus 210.88, Sonnet 198.17), delta $253.15 in about 8.6 h.
- Per-agent rows: https://raw.githubusercontent.com/PrompTugal/PrompTugal__Agent__Telemetry/dev/site/factory/dinis-cruz/account-f/usage-2026-11-26-1115.json
- Context fill at B: security 781,975 tokens (at the 784,000 compaction threshold), dev 507,253, library 426,325, reviewer 412,626. Cost per wake rises with context, so these are the likely first reset candidates.

## Not yet known (I will not invent it)
- Wakes per agent per day and when each reset happens: I do not hold the wake list (the conductor and cl-6.maestro do).
- Cost per release or article: no release or article counts reach me yet.
- Sonnet moves (Opus to Sonnet): none recorded.

## Method I propose
1. Each reset, Sonnet move or wake change is one event row: time (date -u), agent, what changed, who decided (Dinis's word).
2. For each event, take Telemetry's reading just before and just after, per agent: cost_usd delta per wake, and context tokens at wake start.
3. Compare the three wakes before with the three after, same agent, so one big task does not decide the result. Report the range, not only the mean.
4. Cost per release or article: total delta over the window divided by the count the conductor gives me, stating the window.
5. Figures stay in this private folder; nothing published until Dinis says.

## Needs
- From cl-6.conductor or cl-6.maestro: the event times and the wake list.
- From cl-6.telemetry: a reading just before and just after each event, and daily deltas from 00:00 UTC.
