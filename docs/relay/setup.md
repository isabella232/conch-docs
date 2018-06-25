# Initial Setup of Diagnostic Relay Devices (DRD)

## Bill of Materials

Upon receiving the Diagnostic Relay Device equipment, the shipment should be
inspected for obvious damage or tampering.

Any suspected damage should immediately be reported to Joyent Build Operations,
who can be reached at preflight-dev@joyent.com

All hardware is engineered and assembled to be robust and free of maintenance
tasks once the DRDs are deployed. 

The DRD shipment consists of:

* 802.11n/ac wireless access point
* Diagnostic Relay Devices (DRD) with wifi antenna kits
* IEC C13-C14 power cables (blue) and AC-DC power supplies
* 1gig copper SFPs
* 2 CAT5 ethernet cables per DRD

## Device Assembly

After unpacking, initial setup of the DRD system consists of the following
steps:

Unbox the DRDs and attach the two wifi antennas included in each box to the
gold coaxial connectors on rear of the DRD, ensuring that the antennas are
screwed on securely.

Unpackage the IEC C13-C14 power cables and AC/DC power supplies and match a set
of these to each DRD.

## Wireless Connectivity

Locate an ethernet jack for the premises’ network and a AC power outlet
which are in reasonable wifi range of the area where the DRDs will be
operating.

Plug the provided wireless access point into these. This access point is fully
secured and acts as the bridge for the DRDs to the outside world, and thus to
Joyent’s Conch servers. It broadcasts a wireless network with the SSID of
“preflight”.

Only the DRDs will be able to access this SSID in order to send and receive
telemetry from Joyent. After initializing, the access point should display a
large blue light on its top indicating that it is operating correctly and was
able to DHCP an IP address from the local network.

The DRD Wireless Access Point requires access to the public internet on the
following TCP+UDP ports:

* TCP 22 (SSH)
* UDP+TCP 53 (DNS)
* UDP 123 (NTP)
* TCP 443 (HTTPS)

At this point, the DRD system setup is complete and, if powered on, the DRDs
will ping home to the Joyent Conch servers. They are now ready to be employed.
A small blue light on the rear of each DRD indicates that it is powered on.
They have no on/off switch, only a small, recessed reset button in the rear
co-located with the blue status lamp next to the DC power input.
