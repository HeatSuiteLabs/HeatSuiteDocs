Below are some common issues that users have experienced with the HeatSuite watch app

## Unresponsive/freezes when on the charger

This is a common issue that can happen when the Bangle.js2 is left on the charger for extended periods of time. Following multiple sync requests with one of the environmental nodes, the watch can become unresponsive. The remedy is to restart the Bangle.js2 by holding the button for ~5 seconds. 

## The watch hasn't synced data with a node for a couple of days

The watch will only sync data with a node when it is within Bluetooth range (<10 meters) of a node, and is on the charger AND charging. 

## What happens when the storage is full on the watch?

Common signs for this are a slow/unresponsive screen to touches or button presses, missing data, or frequent compacting messages on the watchface. To check the storage remaining on the watch, you can visit the [Bangle Apps Loader](https://heatsuitelabs.github.io/BangleApps/), connect to the Bangle.js2, go to the `More` tab, and scroll down to `Device Info`. There will be a Storage breakdown there. If you see <5% free space, the Bangle.js2 will have difficulties forming a connection to a node, and sending its data. In this instance, its best to use the Backup feature (under `Utilities` on the `More` tab) which will download ALL files on the watch. If issues continue to persist, you may have to `Remove all Apps` and then `Install default apps`, including [HeatSuite](https://heatsuitelabs.github.io/BangleApps/?q=heatsuite). If the watch is regularly placed nearby a node every 24/48 hrs and synced, this should not happen.

## The time on the Bangle.js2 is off

This often happens because the watch battery emptiss and the onboard real-time clock looses its "time" and reverts back to a unix of 1 (read more about unix [here](https://en.wikipedia.org/wiki/Unix_time)). If you place the watch on a charger near a node, it will automatically update its time on its next sync procedure. You can also update the time on the watch with the [Bangle Apps Loader](https://heatsuitelabs.github.io/BangleApps/) website by connecting to the device and navigating to the `More` tab and selecting `Set Bangle.js Time`. This will use your systems time to update the watch.