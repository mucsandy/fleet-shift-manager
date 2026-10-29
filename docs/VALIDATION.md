# Testing notes

[Back to the project](../README.md) · [Installation](INSTALLATION.md)

Last checked: **29 October 2026**, in Power Apps Studio using the iPhone SE preview (375 × 667).

## What works

- **Import:** the published app file opened in a separate Studio session. The Data pane was empty and the formula checker found no errors. The example damage photo loaded correctly.
- **Vehicles:** both demo vehicles appeared. Damage and Tasks stayed disabled until a vehicle was selected.
- **Handovers:** a direct handover saved with a 10 km journey, 23.73 liters of fuel and typed-name confirmation. The history showed the saved values. A decreasing odometer, an invalid time and missing confirmation were rejected.
- **Damage:** the marked point opened the sample report. A new report saved at a different point without inheriting the sample photo. The accident notice could be dismissed.
- **Tasks:** a completed task appeared in the history. The person picker showed the three active demo members with an empty search.
- **Info:** guides and the shift-lead roster appeared. Switching from Volunteer to Team lead made management visible. This tests the demo's screen visibility, not real account permissions.

The save tests were done before export. After importing the file, I rechecked vehicle selection, damage and its photo, tasks and the person picker, Info, the role switch, the six handover choices and cancelling a handover. I did not repeat every save test after import.

## Still to check

- Every workshop/replacement and handover path from start to finish.
- Installation in another environment or tenant, then saving and publishing that copy.
- Real iPhones and Android devices, accessibility and startup speed.
- Drawing a signature; the handover test used typed-name confirmation.

App checker still reports **27 medium performance warnings and one informational warning**. These have not been resolved in this demo.

The demo keeps changes for one session. Shared storage, email, photo uploads and backend permissions are not included in these tests.

File size and checksum: [release manifest](../app/release-manifest.json).
