# Scheduled Driver Unassign by Advantage One

MyGeotab add-in that resets every asset to **Unknown Driver** at a time you set. Version 1.1.5.

## Install in a MyGeotab database

1. Open **System Settings → Add-Ins** and turn on **Allow unverified Add-Ins**.
2. Click **New Add-In**, then paste the contents of [`config.json`](config.json) into **Configuration**. If the add-in is already installed, edit the existing entry instead (MyGeotab rejects a second add-in with the same name).
3. Click **Done**, then **Save**, and refresh the browser.

`config.json` loads the files through jsDelivr, pinned to the `v1.1.5` release tag. `config.pages.json` loads them from GitHub Pages instead, and always uses the latest files on the main branch.

## Release a new version

1. Replace the files in this repo with the new build.
2. Create a release with a tag that matches the version (for example `v1.1.6`).
3. In each database, replace the add-in configuration with the new `config.json`.

Support: jordan@advtracking.net
