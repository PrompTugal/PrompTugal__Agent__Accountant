# PrompTugal side of the cost-reduction track (method only; figures private until Dinis says)

For cl-6.accountant@dinis, who owns the account-wide ledger. Started 2026-11-26 by cl-6.accountant@PrompTugal.dinis. Figures are API-equivalent cost_usd from get_session as read by cl-6.telemetry; none verified against an invoice.

## Baseline
Figures are deliberately not repeated here: this repository is publicly readable, and Dinis said figures stay private until he says. The baseline readings are cl-6.telemetry's usage files (02:38Z and 11:17Z on 2026-11-26) in the Telemetry repository. Context fill per agent at the first reset candidates is in the same file.

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

## Sources found (2026-11-26, from the conductor; no figures kept here)
- Sessions, models, start times, wakes: PrompTugal__Agent__Conductor, board/proposals/2026-11-26-sessions.json (41 sessions listed).
- Releases: PrompTugal__News__Website newsroom/versions.json. Each entry has a date only, no time, so a release cannot be placed inside a cost window shorter than a day. Cost per release can be stated per whole UTC day only, until release times are recorded.
- Articles: content/articles/ front matter, by date; not yet read (website not attached).
- Resets and replacements: the maestro's list is awaited (the conductor named maestro to session_016CrbJLv54Kh4CSTzagW2G3 about 13:43 UTC and the usage-limit stop 07:20 to 11:10 UTC, as told to me, not verified).

## PrompTugal events reported to me, 2026-11-26 (times Z, as told by the conductor and maestro; not verified; no figures)
- 16:38 conductor reset (new session_016CrbJMiN8eUtML9vvvGCVt).
- 16:54 abp reset (session_016CrbJLnbr219cU3eVRGxBW).
- Also reset today, time not given: journalist (session_016CrbJNYGCQ9RLyq8e7aVU7), devops (session_016CrbJK7qgEKhvrRXNs9wCo).
- New sessions: place.london (wake 25 7,18 Lisbon), data.london.
- Per event I still need Telemetry readings, three wakes each side. Reset times for journalist and devops are asked of the maestro.

## Capture log (pointers only; figures held privately, Dinis: capture everything)
- 2026-11-27T10:14Z Telemetry reading: https://github.com/PrompTugal/PrompTugal__Agent__Telemetry/blob/dev/site/factory/dinis-cruz/account-f/usage-2026-11-27-1015.json (earlier: usage-2026-11-26-1115.json, -1555.json, -2117.json, conductor-reset-2026-11-26.json in the same folder).
- My private copies are in the session scratchpad, which is lost when this container is reclaimed; a durable private home is still needed from Dinis.
