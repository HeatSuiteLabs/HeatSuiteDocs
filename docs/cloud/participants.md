# Participants

Use **Participants** to register study participants, assign smartwatches, and manage monitoring sessions. A participant record stores a study label, an optional group, and a participant status. A monitoring session records the monitoring period and timezone. The smartwatch assignment records which watch and profiles apply during that period, including when you replace a watch or change its profiles.

## Find a participant and open their details

Search by participant label, group, or smartwatch ID. Use the status filter to narrow the list by participant status, or turn on **No recent sync** to find participants with a stale-sync warning. The **Monitoring** column shows the session state, such as **Not assigned**, **Scheduled**, **Active**, **Paused**, or **Ended**.

Select the participant's label to open their details. The dialog shows their participant status, smartwatch, session dates and timezone, last sync, and assigned watch profiles. This is also where you edit the participant and manage the session. After a watch or profile change, a notice can show that HeatSuite Cloud is still waiting for a file from the watch.

## Add a participant and start monitoring

1. Select **Add participant**. Enter a study label such as `P04`, an optional group, and a status. Use a study code for the label so you can work in HeatSuite Cloud without entering names.
2. To start monitoring, choose a **Smartwatch** that has checked in and a published **Task Profile** from [Study Design](study-design.md). If you want to add the participant and assign a watch later, leave both fields blank.
3. For a monitoring session, choose the **Timezone** used for the participant's schedule. You can also select **Survey** and **Wearable** profiles and enter a **Session label**, such as `baseline`. If **Monitoring starts** is blank, the session starts now. If **Monitoring ends** is blank, the session stays open until you stop it.
4. Select **Create participant**. To enroll an active participant later, open their details, select **Assign smartwatch**, and complete the form with **Start monitoring**.

## Assign watch profiles

1. Open **Participants** and select the participant's label.
2. Under **Watch profiles**, select the pencil to edit the smartwatch's profiles.
3. Choose a published **Task profile** and any published **Survey profile** and **Wearable profile** the participant needs. Select **Save**.

In HeatSuite Cloud, the assignment change takes effect when you save or at the scheduled assignment start if it is in the future. Ended assignments are read-only.

!!! note "Automatic updates at the next sync"
    Once profiles are published and assigned, the smartwatch applies them automatically the next time it syncs with a HeatSuite node that has the updated assignment and profiles. The same process applies when you change which profile is assigned or publish a new version of an assigned profile. If the next node still has an older configuration, the watch receives the update when it syncs with a node that has it. This keeps watches in step with changes to recording settings, task schedules, and surveys during a deployment.

## Manage a monitoring session

- **Switch smartwatch** records a replacement watch within the same session. Choose the replacement, a published task profile, any optional survey or wearable profile, and the switch time. Leave the time blank to switch now. The old watch assignment ends at the switch time and the new assignment starts then.
- **Edit participant** lets you update the label, group, or status. If the participant has a session, the form also lets you correct its start, end, or timezone. Timing and timezone corrections trigger a compliance recalculation.
- **Pause monitoring**, **Resume monitoring**, and **Stop monitoring** are available for open-ended sessions. When you stop a session, choose the resulting participant status. An active participant whose previous session has ended can start a new session with **Assign smartwatch**.

!!! warning "Deleting a participant"
    **Delete participant** removes the participant record, monitoring sessions, and compliance results. Raw smartwatch data already stored in HeatSuite Cloud is retained.

## Review compliance

Select the **Compliance / coverage** badge to open the session's compliance details. Use **Recalculate compliance** in the participant details to request a refresh, for example after late uploads. See [Compliance Monitoring](compliance.md) for how task windows, coverage, sync warnings, and wearable uptime are calculated.
