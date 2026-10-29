# Using Fleet Shift Manager

[← Project](../README.md) · [Install the demo](INSTALLATION.md) · [Validation](VALIDATION.md)

## 1. Select the vehicle you are actually using

Open **Select vehicle** and choose the vehicle. Registration and status help distinguish the pool vehicle from a replacement. Damage and Tasks become available after selection, keeping the work in that vehicle's context.

<img src="../assets/screenshots/vehicle-picker.png" alt="Vehicle selection in iPhone SE preview" width="300">

## 2. Choose the operation

Open **Handover / Logbook** and pick what actually happened.

| Option | When to use it |
| --- | --- |
| Driver to driver | You hand the vehicle directly to another person. |
| Park vehicle — no direct handover | You leave the vehicle without someone there to receive it. |
| Collect vehicle — no direct handover | You pick up a parked vehicle without an in-person giver. |
| Logbook entry without a handover | Record a journey without transferring the vehicle. |
| Workshop / vehicle swap | The vehicle goes to the workshop, potentially with a replacement workflow. |
| Vehicle back from workshop | The original vehicle returns from the workshop. |

Leaving a vehicle without a recipient is explicit. The history preserves the last recorded giver, and the next person can choose **Collect vehicle — no direct handover**.

<img src="../assets/screenshots/handover-types.png" alt="Handover and logbook operation choices" width="300">

## 3. Complete the record

The form walks through times, odometer readings, people, condition and equipment. Review the details before saving. If you refueled, record liters. Use the signature or explicit name-confirmation option required by the workflow.

Time and odometer checks help catch invalid entries; enter the actual readings. If you cancel, confirm whether to discard the unfinished form. **Handovers / Logbook** shows recent vehicle history with the values and confirmation stored for each operation.

## 4. Check and report damage

Open **Damage**. Tap a numbered point to open an existing report. Choose **New damage** for a new report and place its point on the right vehicle view. Add a clear description, severity/type and review before saving.

<img src="../assets/screenshots/damage-map.png" alt="Numbered damage point on the front vehicle view" width="300">

The demo includes one labeled artificial photo for the front-left sample report. New reports do not inherit it. Uploading photos is disabled in the session edition; a connected deployment needs its attachment flow configured and tested.

**In an accident, also follow the required accident and damage-reporting process. The app entry does not replace it.**

## 5. Work through due tasks

Open **Tasks**, select a task and read the instructions. Choose the person documenting the result. Record completion or explain why it could not be done. Due tasks, history and the plan have separate views.

<img src="../assets/screenshots/tasks.png" alt="Due vehicle tasks" width="300">

## 6. Find guides and the shift lead

Use **Info → Info & documents** for guidance and **Info → Shift lead** for the roster. The current duty period is highlighted; the demo roster uses Berlin time. Further shift documents are planned for the information area.

<img src="../assets/screenshots/shift-leads.png" alt="Highlighted current shift lead" width="300">

Demo names/addresses are invented and contact actions do not send anything. **Demo role** changes the simulated identity to expose leadership and administration screens; it grants no external permissions.

## What happens to demo entries?

Changes live only in the current session. A new session starts with fictional seed data. Use a separately configured and tested backend for records your team needs to keep.
