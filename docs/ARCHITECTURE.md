# Architecture

[← Project](../README.md) · [Install](INSTALLATION.md)

The public edition is a single Canvas app: seven screens, nine typed local data collections and fictional seed records. `App.OnStart` initializes the collections once per session. Power Fx filters the selected vehicle's records and writes changes back into those collections.

| Screen | Responsibility |
| --- | --- |
| VehicleHome | Vehicle selection, handover/logbook wizard and recent history |
| DamageReports | Vehicle diagrams, reports and simulated review workflow |
| HygieneCheck | Due tasks, documentation and task history |
| Information | Guides, shift leadership and demo role switch |
| Administration | Fictional members and vehicles |
| TaskPlanAdmin | Task templates and schedule settings |
| ContentAdmin | Guide content and shift-lead roster |

The [`src-demo`](../src-demo) files are taken from the actual `.msapp` export. [`schema/demo-collections.json`](../schema/demo-collections.json) describes the local table shapes, including compatibility fields retained from the connected workflow. They are not active connections or a backend provisioning contract.

The app uses local `Collect`, `Patch`, `UpdateIf` and `RemoveIf` operations. Email, live account lookup, outbound contact actions and photo uploads are disabled. One embedded, labeled AI-generated bumper photo illustrates a fictional damage report; new reports do not inherit it.

Role switching is a demonstration of screen visibility and workflow behavior. It is not authentication or server authorization. There is no shared persistence, offline synchronization, flow deployment or production backend in this repository.

The `.msapp` includes a neutral icon, embedded artwork, layout/control metadata and three built-in Studio sample schemas. The latter are static samples, not business connectors. A future connected implementation needs its own data model, permissions, attachment handling and concurrency tests.
