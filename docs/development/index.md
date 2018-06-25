# Development

## Design

Major Conch features must be written as Request For Discussion documents (RFD).

RFDs are published in the [Joyent RFD GitHub repo](https://github.com/joyent/rfd).

| State    | RFD |
|----------|-----|
| Deployed | [RFD 132 Conch: Unified Rack Integration Process](https://github.com/joyent/rfd/blob/master/rfd/0132/README.md) |
| Deployed | [RFD 133 Conch: Improved Device Validation](https://github.com/joyent/rfd/blob/master/rfd/0133/README.md) |
| Deployed | [RFD 134 Conch: User Access Control](https://github.com/joyent/rfd/blob/master/rfd/0134/README.md) |
| Draft    | [RFD 135 Conch: Job Queue and Real-Time Notifications](https://github.com/joyent/rfd/blob/master/rfd/0135/README.md) |
| Draft    | [RFD 136 Conch: Orchestration](https://github.com/joyent/rfd/blob/master/rfd/0136/README.md) |
| Draft    | [RFD 140 Conch: Datacenter Designer](https://github.com/joyent/rfd/blob/master/rfd/0140/README.md) |
| Private  | Triton CN Setup Automation |

Minor features require discussion (often in GitHub Issues or email) but not
RFDs.

Conch is designed in public as much as possible, though there some components
that are currently closed (until they can be scrubbed for security.)

## Development Process

All Pull Requests to Conch repos require code review by at least one engineer.

A buildbot deployment runs the Conch test suites for every commit.

Binary releases of the Conch Shell are available [here](https://github.com/joyent/conch-shell/releases) for many platforms.

## Similar Products

* The Foreman
* Collins
* netbox
* device42
* Commerical CMMS (e.g., Fiix)
* GitHub Metal Cloud

