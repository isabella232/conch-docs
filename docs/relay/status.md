# Status Information

## Status Information

### Status Page: Validation Progress

The Status page contains a progress diagram. Each cell represents a rack.

As systems come online and begin validation, the cells in the bar will fill.

| Color | Description |
|-------|-------------|
| Grey  | Pending     |
| Green | All devices validated |
| Blue  | Devices in progress |
| Red   | One or more devices have failed validation. |

![progress](../images/rack_validation_inprogress.png)

### Status Page: Validation Failures List

The Status Page contains a summary of the devices with validation problems.
Click View Device to open details and review the validation failures.

![failures](../images/validation_problem_list.png)

### Device Details: View Validation Failure

When a device fails validation, the Validation tab in the Device Details view
will provide information on what has failed. In this case, the devices
networking is not cabled correctly.

![v-failure](../images/device_view_validation_failure.png)

### Device Details: Validation Complete

When a device has validated completely, the Device View will look something like
this:

![v-complete](../images/device_validation_complete.png)

## Icons Legend

| Icon | Description |
|------|-------------|
| ![attention](../images/status_attention.png) | Item requires attention |
| ![failure](../images/status_failure.png) | If device, it is failing validation. If datacenter or rack listing, a device contained within is failing validation. |
| ![in-progress](../images/status_in_progress.png) | Datacenter, rack, or device is currently being validated. |
| ![no-report](../images/status_no_report.png) | No report has been collected from this device yet. |
| ![validated](../images/status_validated.png) | Device has been validated and has been shut down. |
