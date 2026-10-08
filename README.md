# Scheduled Driver Unassign by Advantage One

MyGeotab add-in that resets every asset to **Unknown Driver** at a time you set. Version 1.1.5.

The whole add-in is the single file `unassignDrivers.html`. MyGeotab loads it through jsDelivr, pinned to a release tag.

## Install in a MyGeotab database

1. Open **System Settings → Add-Ins** and turn on **Allow unverified Add-Ins**.
2. Click **New Add-In** and paste the contents of [`config.json`](config.json) into **Configuration**. If the add-in is already installed, edit the existing entry instead, because MyGeotab rejects a second add-in with the same name.
3. Click **Done**, then **Save**, and refresh the browser.

## Release a new version

1. Replace `unassignDrivers.html` and `config.json` with the new build.
2. Publish a release with a **new** tag that matches the version (for example `v1.1.6`). Never move or reuse a tag: jsDelivr caches each tag permanently.
3. In each database, replace the add-in configuration with the new `config.json`.

Support: jordan@advtracking.net
