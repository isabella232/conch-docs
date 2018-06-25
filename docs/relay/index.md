# Diagnostic Relay Device (DRD)

!!! note "Note"
    The DRD was previously known as the Preflight Relay Device, but this name
    has been changed to avoid overloading "PRD", internally.

Joyent’s Conch system with its Diagnostic Relay Devices ensures that the
servers, switches, and network cabling inside an assembled rack conform to
Joyent’s specifications regarding correct network wiring harness, firmware
versions, and hardware component manifests.

DRDs are generally used in off-site integration by third-party vendors.

Once all items are verified to be correct, it performs burn-in testing of the
CPU, DRAM, and disks of each system and then powers the system off when
completed.

Joyent staff track the progress of the systems undergoing preflight testing live
and advise integration staff on any anomalies which require correcting. The goal
is to verify correct configurations and to root out failing or DOA components
prior to their departure to the datacenter.

## Automated Upgrades and Validation

Each switch and server come from the manufacturer with the configuration
specified in Bill of Materials, but it has not yet been customized for
production.

The DRD Preflight environment configures and upgrades the host to Joyent’s
operating standards, using automation with scripts and software the DRDs upgrade
and customize each host.

This includes the following settings:

* Top of rack switch firmware
* Server firmware for BIOS, HBA, backplane and hard drives
* Custom boot and environmental settings.

Upgrades will automatically reboot switches and servers when necessary.

!!! warning "Warning"
    It is important to maintain power to the rack during this entire process.

In the event that power is shut off to the rack, it should be recorded and
reported to Joyent Build Operations.

During the upgrade process the switches and servers are continuously checked for
alignment with the production specifications.

This process can be viewed at https://conch.joyent.us using the supplied
credentials.

Hosts that are reporting into the interface have the cloud icon with the arrow
pointing up and if they are not actively reporting a question mark will appear.
As settings are validated a checkmark will appear. If there are errors an
exclamation point will show.

Finally, when a device reaches all of the stages of upgrading and validation a
check mark with a solid colored circle will appear and the “PASS" box will show
for the device.
