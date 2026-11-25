# Wearable Settings

Use **Wearable Settings** in HeatSuite Cloud to create reusable configurations for Bangle.js2 smartwatches. A profile controls which data the HeatSuite watch app records and which app features are enabled. Use [Study Design](study-design.md) to configure task schedules and survey questions.

## Create or edit a settings profile

1. Open **Wearable Settings** and select a **Profile**, or select **Add profile** to create one with a name and an optional description.
2. Adjust the recording and app settings for your study. The dashboard saves edits to the selected profile's draft as you work.
3. Open **JSON Preview** to inspect the draft configuration. Select **Publish** when the profile is ready for use.

The status bar shows the draft and published versions and flags **unpublished changes**. Select **Revert changes** to replace the draft with the active published version. You can do this once the profile has been published.

## Settings you can configure

- **Recorder Options** controls which streams are recorded. Options include steps, optical heart rate, accelerometry, battery, movement, temperature and pressure, Bluetooth heart rate, and the CORE Sensor. Pair any required external sensors as part of [Watch Setup](../watchapp/index.md).
- **Extras** controls task notifications, EMA question randomization, swipe-to-launch, fall detection, and debug options. Set individual task reminder times and enable **Notify** in [Study Design](study-design.md).
- **High Resolution Accelerometer** enables high-resolution accelerometry and lets you set the logging interval in seconds and the maximum number of records per file.
- **GPS PSMOO** enables GPS and exposes scan time, scan interval, and adaptive time in minutes.


## Import or download settings

Select **Upload settings JSON** to import an existing watch settings file. Choose **Overwrite current draft** to replace the selected profile's draft, or **Create new profile** to keep the import as a separate profile. Publish the resulting draft when it is ready.

Select **Download** to export the current settings as `heatsuite.default.json`. The download can include changes you have yet to publish.

## Assign settings and sync the watch

Open [Participants → Watch profiles](participants.md#assign-watch-profiles) and select the published wearable settings profile for the participant's smartwatch. If you publish a new version of a profile already assigned to the watch, the same assignment can deliver the new version.

!!! note "Automatic updates at the next sync"
    The watch applies the published settings automatically on its next sync with a HeatSuite node that has the updated assignment and profile. This lets you update recording settings remotely as deployment needs change.

## Apply profiles manually with the App Loader

1. Publish the settings, tasks, and survey profiles you plan to use. Copy the **Profile API URL** from **Wearable Settings** or **Study Design**. Keep the URL private because it contains your deployment's access token.
2. Connect the smartwatch in the [HeatSuiteLabs Bangle.js2 App Loader](https://heatsuitelabs.github.io/BangleApps/?q=heatsuite) and open the HeatSuite app customizer.
3. Open **Cloud Connect**, paste the URL, and select **Get Profiles**.
4. Choose the **Settings profile**, **EMA profile**, and **Tasks profile** you want to use. Select **Apply Selected** to load those choices into the customizer, then select **Upload** to write the configuration to the connected watch.

See [Watch Setup](../watchapp/index.md) for help connecting a watch and opening the customizer.
