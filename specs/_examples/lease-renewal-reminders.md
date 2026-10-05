# Lease renewal reminders (example)

| Field   | Value |
|---------|-------|
| Status  | draft |
| Domain  | property management |
| Effort  | S |

## Problem pattern

Small property managers track lease end dates manually and miss the window to
negotiate renewals, causing vacancies or month-to-month holdovers at stale rents.

## Desired outcome

Each lease owner gets a reminder at 120, 90 and 60 days before lease end, with
a link to start the renewal.

## Inputs and outputs

- **Input:** list of leases (`tenant`, `unit`, `end_date`, `owner_email`).
  Example: `Acme Bakery, Unit 4, 2027-03-31, owner@example.com`
- **Output:** reminder emails and a weekly "upcoming renewals" summary.

## Functional requirements

1. Import leases from CSV or an API.
2. Send reminders at the configured offsets; never send the same reminder twice.
3. Allow marking a renewal as "in progress" or "signed" to stop reminders.

## Out of scope

- Generating the renewal document itself.

## Acceptance tests

- Given a lease ending in 120 days, when the daily job runs, then one reminder is sent.
- Given a lease marked "signed", when the job runs, then no reminder is sent.

## Notes / lessons learned

Reminder offsets should be configurable per portfolio; commercial leases often
need 180+ days of notice.
