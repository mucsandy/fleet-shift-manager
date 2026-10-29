# Install the English demo

[← Project](../README.md) · [User guide](USER_GUIDE.md) · [Validation](VALIDATION.md)

## What you are installing

A disconnected Power Apps Canvas app with fictional session data. It has no business connections, directory lookups or email dispatch. Nothing needs to be connected to a list to try it. Changes are held in memory and reset in a new session.

**Release status:** this exact sanitized file was imported into a separate, unsaved Power Apps Studio session on 2026-10-29. Core navigation, seeded data, the embedded example image and blank-search person selection passed the smoke test in iPhone SE preview. Formula checker reported no errors; the Data pane was empty. This checks file import in the source environment, not installation into another tenant, publication of a new app or physical-device behavior. See [Validation](VALIDATION.md).

## Before you start

- Sign in to [Power Apps](https://make.powerapps.com) with an account permitted to create apps.
- Choose a development environment where you have the **Environment Maker** role. Applicable Power Apps licensing is still required; the MIT license does not include Microsoft platform licenses.
- Use a separate app for evaluation, rather than replacing an existing operational app.

## 1. Download the actual app file

[Download Fleet-Shift-Manager-English-Demo.msapp](https://github.com/mucsandy/fleet-shift-manager/raw/refs/heads/main/app/Fleet-Shift-Manager-English-Demo.msapp)

Keep the `.msapp` extension. If GitHub shows the file page, use its **Download raw file** control. Do not rename a repository ZIP or import it as a solution/package ZIP.

The reviewed file's size and SHA-256 are recorded in [`app/release-manifest.json`](../app/release-manifest.json). For an optional Windows check:

```powershell
Get-FileHash -LiteralPath '.\Fleet-Shift-Manager-English-Demo.msapp' -Algorithm SHA256
```

## 2. Open it in Power Apps Studio

1. In the maker portal, select your destination environment.
2. Select **Apps → Import app → From file (.msapp)**.
3. Select the downloaded `.msapp` file when prompted. In the tested portal, the file chooser appeared immediately after **From file (.msapp)**; Studio then opened the app.
4. Check that the app contains **VehicleHome, DamageReports, Information, HygieneCheck, ContentAdmin, Administration** and **TaskPlanAdmin**.

These are the single-app steps documented by [Microsoft](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/export-import-single-app). They differ from importing a Canvas app package ZIP or a Dataverse solution.

The demo should not request business-connector credentials. If it asks to reconnect an organizational data source or email connector, stop and verify that you selected this file. Built-in Studio sample schemas in the archive are not business connections.

## 3. Initialize and preview

1. Let initialization finish. On the tested import, the first vehicle list was briefly empty before the two seeded vehicles appeared. If it stays empty, select **App** in the tree, open its menu and choose **Run OnStart**. Initialization seeds local collections; it does not fetch operational data.
2. Start preview with **F5** or the play button.
3. Confirm that **Damage** and **Tasks** are unavailable before vehicle selection.
4. Open **Select vehicle** and choose **DEMO-01**. Both sections should become available.
5. Open **Damage**, dismiss the accident notice and open the existing front-left report from its point. Its artificial sample photo should load with an AI-generated label.
6. Open **Tasks** and check that the documenting-person selection contains fictional people, including when the search is blank.
7. Open **Info** and try the separate guide and shift-lead views. The simulated role selector can expose the management views.

The screenshot gallery in the [README](../README.md#see-the-app) shows what to expect. The import smoke test passed; cross-environment and physical-device checks remain open in [Validation](VALIDATION.md). Please report differences with fictional data only.

## 4. Save your own copy

Save the opened file as a new app with a name such as **Fleet Shift Manager – My Demo**. Save and publish are different operations. Publish only when you want that saved version to be available through its player link; share it only with the intended evaluators. See [Microsoft's save/publish guidance](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/save-publish-app).

Publishing does not turn local collections into a shared database. Every user/session still starts with fictional data. To reset while editing, close preview and start a new app session; `OnStart` has an initialization guard, so repeatedly running it in the same session does not necessarily reset your entries.

## Adapting it for a real team

Persistent records, real photo uploads, messaging and identity-based roles require your own backend and tested integrations. The supplied schema describes local demo records, not an automatic list-provisioning script. There are no list IDs, tenant connections, deployment credentials or backend permission assignments included.

The role picker is deliberately a simulation. Enforce real permissions at your data source and test with separate driver, leadership and administrator accounts. Do not use the session demo for records you need to retain.

## Troubleshooting

| Symptom | Check |
| --- | --- |
| Cannot import the repository ZIP | Download the `.msapp` file and choose **From file (.msapp)**. |
| No import option / permission error | Check the environment and Environment Maker role with your administrator. |
| First preview has no vehicles | Run **App → Run OnStart**, then start preview again. |
| Portal remains on a loading screen | The portal initially stalled during testing; a later attempt loaded successfully. Retry after the account/environment finishes loading. Do not repeatedly upload or overwrite another app. |
| Entries disappear | Expected: this edition stores changes for one session. |
| No photo upload or email | Expected: these external operations are disabled. The supplied example photo is embedded. |
| Management is hidden | Use the **Demo role** switch; this demonstrates UI behavior only. |

For source review, see [Canvas source files](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/power-apps-yaml). The exported YAML is not a substitute for the `.msapp` import file.
