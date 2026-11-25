# Study Design

Use **Study Design** to configure what participants do on the HeatSuite watch app. The **Study Tasks** tab controls which tasks appear and when the watch prompts participants. The **Survey** tab defines the ecological momentary assessment (EMA) questions and responses.

## Configure study tasks

1. Open **Study Tasks** and choose a **Profile** or select **Add profile**.
2. Move tasks from **Available tasks** onto the watch preview. Drag them within the preview to change their order. Move a task back to **Available tasks** to leave it out of the profile.
3. Select a task tile to edit its settings. Enter **Times of day** as comma-separated 24-hour times in HHMM format, such as `900, 1300, 1800` for 09:00, 13:00, and 18:00. Set **Notify** to enable reminders for those times. **Debounce** is the number of seconds before a scheduled reminder during which a recent completion suppresses that reminder.
4. Select **Publish** when the task profile is ready.

Select **Custom** in **Available tasks** to create a task template with your own identifier and label. Under **Custom task fields**, you can supply an icon and the JavaScript that runs when someone selects the task on the watch. See [Watch App Tasks](../watchapp/watchapp-tasks.md) for the built-in tasks and configuration details.

For prompts on the watch, include the **Survey** task in the task profile, configure its times, and enable **Notify**. The wearable settings profile also needs **Task Notifications** enabled. The questions participants see come from the survey profile installed on the watch.

## Build an EMA survey

1. Open **Survey** and choose a **Profile** or select **Add profile**. Select the languages participants will use under **Available Languages**.
2. Select **Add Question**. Give the question a unique **Key** and provide question text in each selected language.
3. For a choice-based question, use **Add Option** to define response text and a stored value for each option. For a numeric question, turn on **Numeric** and set the starting value, minimum, maximum, step, and optional units.
4. To branch to another question based on an answer, use the **Next** control for a response option or add a follow-up for a numeric value. Mark a question **Follow-up only** when it should appear only through a branch. Use **Add Window** to limit a question to specific times of day. **Once/day** limits repeats within a day, and **Fixed order** keeps a question in place when randomization is enabled.
5. Check the watch preview and any question warnings, then select **Publish** on the **Survey** tab.

Survey time windows control when a question can appear. To schedule a reminder to open the survey, configure the survey task under **Study Tasks**. See [EMA Survey](../watchapp/watchapp-ema.md) for more about branching, time windows, and language support.

## Manage drafts and published versions

Task and survey edits save automatically to drafts. Each tab publishes its own version, so publish both tabs if your study uses tasks and an EMA survey. **JSON Preview** shows the current configuration, **Download** exports it, and **Revert changes** restores that tab's draft from its active published version.

- **Study Tasks** imports and exports `heatsuite.tasks.json`. When importing, choose **Overwrite current draft** or **Create new profile**.
- **Survey** imports and exports `heatsuite.survey.json`. An import replaces the selected survey draft. To preserve that draft, select or create a different profile before uploading.

[Compliance Monitoring](compliance.md) uses published task profiles for scheduled task calculations.

## Assign profiles to a smartwatch

1. Open **Study Design → Assignments** and find the Bangle.js2 by its name or device ID. Watches appear here after they check in to HeatSuite Cloud.
2. Choose the **Study Tasks**, **Survey**, and **Wearable Settings** profiles for the watch.
3. Select the checkmark in the watch's row to **Save assignment**. These selections can prefill the profile fields when you choose that watch during participant enrollment.

For a watch already enrolled in a monitoring session, use [Participants → Watch profiles](participants.md#assign-watch-profiles) to change its monitoring assignment.
After publishing your task and survey profiles, open [Participants → Watch profiles](participants.md#assign-watch-profiles) to assign them to the participant's smartwatch.

!!! note "Automatic updates at the next sync"
    The watch applies new assignments and published profile updates automatically on its next sync with a HeatSuite node that has the updated assignment and profiles. This lets you update task schedules, surveys, and recording settings remotely as deployment needs change.

### Apply profiles manually with the App Loader

To configure a connected watch directly, copy the **Profile API URL** from **Study Design** and paste it into **Cloud Connect** in the HeatSuite App Loader. Select **Get Profiles**, choose the published settings, task, and survey profiles you want to apply, then select **Apply Selected** and **Upload**. Follow the [manual App Loader steps](wearable-settings.md#apply-profiles-manually-with-the-app-loader) for the full procedure.
