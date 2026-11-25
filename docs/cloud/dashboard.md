# Dashboard

Use the HeatSuite Cloud dashboard to check device activity, view and export data, and manage a wearable study. Select **Menu** to show or hide the sidebar. The dashboard opens on **Devices**.

## Devices

**Device List** shows HeatSuite nodes, Bangle.js2 watches, and other devices known to your deployment. Check when a device was last seen, what sensor readings or uploaded files are available, and which firmware version it reports. Use the filters to narrow the list by device type or offline status.

**HeatSuite Link** shows which devices HeatSuite nodes have observed within the selected lookback period. Select a time range to see recent observations or review a longer period.

### Device details

Select a device name in **Device List** to open its detail page. Choose a data source and date range to plot historical readings. Use **Export** to download data for analysis. For devices with supported file workflows, **Upload Files** lets you import files and **Raw Files ZIP** downloads the original files available in HeatSuite Cloud.

## Study Design

Create and publish task and survey profiles for the Bangle.js2 watch app. Use **Study Tasks** to choose tasks and schedule reminders, **Survey** to build EMA questions and responses, and **Assignments** to save profile selections directly for a smartwatch. See [Study Design](study-design.md).

## Wearable Settings

Create and publish profiles that control which streams the watch records and which app features are enabled, such as GPS, high-resolution accelerometry, and task notifications. You can also import or download settings as JSON. See [Wearable Settings](wearable-settings.md).

## Participants

Register participants, assign smartwatches and published profiles, and manage monitoring sessions. Select a participant's label to see their session details, watch profiles, and last sync. Select the **Compliance / coverage** badge to review monitoring results. See [Participants](participants.md) and [Compliance Monitoring](compliance.md).

## Cloud Settings

Manage options for the whole deployment, including compliance monitoring, stale-sync alerts, wearable uptime, and Bangle.js2 software checks. This page also contains tools for exporting deployment data, reprocessing watch files, and maintaining certificates and credentials. See [Compliance Monitoring](compliance.md#cloud-settings) for monitoring settings.

## Node Firmware Installer

Install firmware on a supported HeatSuite node over USB. Choose the device type and firmware version, then select **Install** in a compatible browser such as Chrome or Edge. Use **Changelog** to review the firmware changes.
