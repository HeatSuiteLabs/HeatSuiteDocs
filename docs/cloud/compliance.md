!!!warning
    This feature is still in beta testing.

# Compliance Monitoring

HeatSuite Cloud can calculate participant-level smartwatch compliance for study tasks and passive wearable uptime. Compliance monitoring is designed for studies where each participant is assigned a smartwatch for a defined monitoring period, and where the same smartwatch may later be reused by another participant or switched during participation.

!!! note
    Scheduled task compliance is calculated only from published Study Task profiles. Draft or unpublished task profiles are ignored by the compliance worker. Wearable uptime can still be calculated independently.

## What Compliance Monitoring Measures

Compliance monitoring answers:

> During this participant's monitoring period, did the expected smartwatch tasks appear in the uploaded data during their allowed time windows?

Compliance can include:

- scheduled study tasks, such as blood pressure, core temperature, body mass, surveys, or sit-to-stand tasks
- passive wearable uptime from `mindata`
- missed, pending, and completed expected task windows
- watch switches during a participant's monitoring period
- stale-sync warnings when a watch has not uploaded data recently

## Key Concepts

### Participant

A participant is the study-facing person or subject identifier, such as `P04`. Participants are managed from the **Participants** page.

Participant records include:

- label
- optional group
- participant status

!!!note
    Avoid storing personally identifying information in participant labels unless your deployment has appropriate HIPAA/GDPR compliant security.

### Monitoring Session

A monitoring session is the participant's study monitoring period.

It includes:

- participant
- session start time
- optional session end time
- timezone
- optional session label
- active, paused, or ended state

If no session label is set, the dashboard shows `Not labelled`.

### Smartwatch Assignment

Smartwatch assignments track which watch was used during which time period inside a monitoring session.

A participant can keep the same monitoring session even if the smartwatch changes. When a watch is switched, HeatSuite closes the old smartwatch assignment and starts a new one at the selected switch time.

### Published Task Profile

Scheduled compliance is based on the active published Study Task profile assigned to the participant's smartwatch assignment.

If a selected task profile is not published:

- the participant page shows a warning
- the profile is labelled as `not published`
- starting or switching monitoring to that profile is blocked
- the compliance worker will not calculate scheduled task compliance for that profile

## Before Starting Monitoring

Before enrolling a participant for compliance monitoring:

1. Go to **Study Design**.
2. Create or edit a Study Task profile.
3. Publish the Study Task profile.
4. Confirm the smartwatch has checked in and appears in HeatSuite Cloud.
5. Go to **Participants**.

!!! warning
    If the Study Task profile is only saved as a draft, scheduled task compliance will not be calculated.

## Adding a Participant

Open **Participants** and select **Add participant**.

Enter:

- participant label, such as `P04`
- optional group
- participant status

To start monitoring immediately, also select:

- smartwatch
- published Study Task profile
- participant timezone
- monitoring start time
- optional monitoring end time
- optional session label

If `monitoring start` is left blank, HeatSuite uses the creation time.

If `monitoring end` is left blank, the monitoring session remains ongoing.

## Changing a Smartwatch During Participation

If a participant changes watches:

1. Go to **Participants**.
2. Find the participant row.
3. Select the switch-watch icon beside the smartwatch.
4. Choose the replacement smartwatch.
5. Choose the published Study Task profile.
6. Set the switch time, or leave it blank to use the current time.
7. Confirm the switch.

HeatSuite keeps the same monitoring session and records the watch change as a new smartwatch assignment. Compliance results after the switch are linked to the new assignment.

## Pausing, Resuming, and Ending Monitoring

From the **Participants** page:

- Pause monitoring when a participant is temporarily not being monitored.
- Resume monitoring when monitoring should continue.
- Stop monitoring when participation has ended.

When stopping a monitoring session, you can also update the participant status, such as `completed` or `withdrawn`.

Ended sessions can still be recalculated if older files are uploaded later.

## Recalculating Compliance

Use the recalculate icon (:material-refresh:) on the participant row to queue a recalculation for that participant's monitoring session.

Recalculation is useful when:

- old files are uploaded after the participant has ended
- a session start or end time is edited
- a timezone is corrected
- a smartwatch switch time is corrected
- task compliance results need to be refreshed

## Compliance Statuses

Each expected task or uptime window can be:

| Status | Meaning |
| --- | --- |
| `complete` | Required data was found inside the compliance window. |
| `missed` | Synced data has passed the compliance window, but required data was not found. |
| `pending` | The watch has not synced data far enough to determine whether the task was missed. |

Pending does not mean the task was missed. It means HeatSuite Cloud does not yet have enough synced data to make a final decision.

## Assessed Compliance and Coverage

The participant table and compliance modal separate assessed compliance from coverage.

| Metric | Meaning |
| --- | --- |
| Assessed compliance | `complete / (complete + missed)` |
| Coverage | `(complete + missed) / expected` |
| Pending | Expected windows that cannot be finalized yet |

Example:

```text
Assessed: 99% (233/236)
Coverage: 9% (236/2586)
Pending: 2350
Expected: 2586
```

This means the synced portion is highly compliant, but most expected windows are still unknown because the watch has not synced.

The main participant table badge shows:

```text
Assessed % / Coverage %
```

For example:

```text
99% / 9%
```

Low coverage is shown as a neutral or warning badge instead of green, even when assessed compliance is high.

## Reviewing Compliance Details

On the **Participants** page, select the compliance badge for a participant.

The compliance details modal shows:

- participant label
- smartwatch
- session label
- timezone
- last sync time
- stale-sync warning, if applicable
- task-level assessed compliance and coverage

The summary table includes:

| Column | Meaning |
| --- | --- |
| Task | Study task or wearable uptime task |
| Assessed | Compliance among finalized windows |
| Coverage | Proportion of expected windows that have been assessed |
| Complete | Finalized windows with data present |
| Missed | Finalized windows with no required data |
| Pending | Windows waiting for more synced data |
| Expected | Total expected windows |

Select a task in the modal to open the daily compliance graph for that task.

## Last Sync and Stale-Sync Warnings

HeatSuite tracks the last processed smartwatch file for each watch. If an active participant's watch has not synced within the configured stale-sync period, the Participants page and compliance modal show a warning.

The default stale-sync period is `48 hours`. This can be changed by:

1. Go to **Cloud Settings**.
2. Open **Compliance Monitoring**.
3. Change **No-sync alert hours**.
4. Save compliance settings.

The stale-sync warning does not mark tasks as missed by itself. It indicates that many compliance windows may remain pending until the watch syncs again.

## Wearable Uptime

Wearable uptime is calculated from passive `mindata` rows.

Uptime uses:

- uptime window minutes
- minimum rows per window
- uptime measurement, usually `mindata`

These settings are configured in **Cloud Settings** under **Compliance Monitoring**.

Wearable uptime is independent from published Study Task profiles. It can still be calculated even if scheduled task compliance is not available.

## Cloud Settings

Compliance settings are managed in **Cloud Settings**.

Available settings include:

- run compliance monitor
- worker interval
- compliance window before the scheduled task time
- compliance window after the scheduled task time
- recompute lookback hours
- no-sync alert hours
- wearable uptime monitoring
- uptime window minutes
- minimum rows
- uptime measurement
