# Example output

## Finding

The endpoint performs one database query per item, producing `N+1` queries.

## Change

Replaced the loop with one parameterized query that loads the required records in bulk. No new dependency or abstraction was added.

## Evidence

The focused test passes. The query count falls from `N + 1` to `2` in the existing integration check.

## Tradeoffs

The bulk result uses more memory for very large requests. The existing request limit keeps the result bounded.

## Skipped

No cache was added because the request did not establish repeated reads or stale-data requirements.
