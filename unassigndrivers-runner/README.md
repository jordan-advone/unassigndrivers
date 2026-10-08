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

## Run on schedule without MyGeotab open (GitHub Actions)

`scheduled-unassign.js` and `.github/workflows/scheduled-unassign.yml` check every database listed in the `GEOTAB_ACCOUNTS` repository secret every 5 minutes. When a slot from the schedule saved on the add-in page is due, the runner unassigns the drivers and writes the run to the add-in's Run history, shown as *GitHub Actions*. It shares the add-in's lock, so an open add-in tab and the runner never both run the same slot.

- `GEOTAB_ACCOUNTS` format: `[{"database":"jorn","userName":"svc@example.com","password":"...","server":"my.geotab.com"}]`. Add one entry per customer database.
- Use a dedicated MyGeotab user per database with Administrator clearance and access to all assets.
- Set the add-in's grace window to 60 minutes, because GitHub can start scheduled runs several minutes late.
- Test with **Actions → Scheduled driver unassign → Run workflow → check**. This signs in and reports the schedule without changing anything.
- A failed run (bad password, API error) shows red in Actions and GitHub emails the repo owner.

Support: jordan@advtracking.net
