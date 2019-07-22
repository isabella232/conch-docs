## Components

### API

Conch's core is its REST API. The API is documented [here](https://conch.joyent.us/doc).

It exposes basic CRUD for all resources we know how to manage:

* Users
* Workspaces
* Datacenters, rooms
* Racks
* Hardware products (servers, switches)
* Relays (DRDs and other device report generators)
* Devices
* Validation failures

Workspaces are arbitrary collections of Datacenter Racks. This is
useful for a number of reasons: You can define workspaces for AZs, for
expansions, or for specific builds. You can invite specific users to a given
workspace, allowing you to limit the devices an outside vendor can interact
with. Workspaces are a very powerful, useful primitive.

It also includes report ingestion and validation endpoints. These feed into the
[validation engine](https://joyent.github.io/conch/validation/BaseValidation)
which allows us to decide if a device is healthy or not, based off its hardware
profile, environmental or arbitrary data.

Writing and testing new validations is documented
[here](https://joyent.github.io/conch/validation/Guide)

The APIs are written in Perl's [Mojolicious framework](https://mojolicious.org/), and are available
[here](https://joyent.github.io/conch).

### UI

The Conch UI is rapidly evolving. Its initial design was targeted at hardware
integrators and datacenter operation staff -- the main focus was on defining
rack layout and identifying problems with devices in those racks.

As time goes on, the UI will expand to include better search and reporting
options, and more advanced features like datacenter, rack, and BOM design.

The UI is an API consumer, and is not magical in any respect.

The UI is written in [Vue.js](https://vuejs.org/), and is available
[here](https://github.com/joyent/conch-ui).

### Conch Shell

The Conch Shell is a CLI tool provides many useful primitives for interacting
with the Conch API. It supports multiple user profiles and endpoints, and has
JSON output options to allow users to create arbitrary processes with it.

The Shell has many options. Here are some examples of using it:

* [Overview](https://gist.github.com/bdha/1a625f22e922cbba315b660f30c3681c)
* [Rack slot contents](https://gist.github.com/bdha/5bcb8bf8321026c68e5b15c76bc77470)
* [Validation plans](https://gist.github.com/bdha/ea93ddd19be5afa7ad21f52bfd6c7bde)
* [Hardware profiles](https://gist.github.com/bdha/ac41b6953325580b614ff4e44b09c095)

The Shell is an API consumer, and is not magical in any respect.

The Shell is written on Go, and is available [here](https://github.com/joyent/conch-shell).

### Database

Conch's core database is Postgres.

Conch uses a [simple migration system](https://github.com/joyent/conch/tree/master/sql)
for managing database changes.

### Relay

Conch Relay is a simple API service that takes traffic from the livesys or other
Conch clients and interacts with the Conch API. It is currently used mainly in
integration and initial validation stages of datacenter builds.

The Relay codebase is currently closed, but is planned on being open ASAP.

The Relay comes in two flavors:

#### Diagnostic Relay Device (DRD)

AKA Preflight Relay Device (PRD).

This is a physical deployment of the Relay service. DRDs are simple x86 or
Rasberry Pi devices that run the Relay and various other agents for standing up
and configuring racks.

In this mode, we support configuration of TORs. As such, the device is plugged
into individual racks. In certain configurations, the DRD must have serial
cables plugged into the TORs to configure them. Other switches only require
ethernet access to do so.

This mode is exclusing used in off-site integration facilities, before the racks
are shipped to the datacenter.

The Relay also includes a support tunnel feature, so engineers can remotely log
into the integration facility if needed.

#### Relay Service (VM)

In this mode, the Relay runs in a SmartOS or VM, and operates in a post-shipment
re-validation mode. In the future, this mode may also allow the planned
production inventory agent to submit reports to the Conch APIs from a local
service.

### Livesys

The live system is a read-only Linux image the Relay PXE boots on servers.

The livesys includes a number of agents:

* Firmware upgrade
* Reporter
* Rebooter
* Burnin
* ...

The livesys is configured via `chef-solo` cookbooks.

The livesys codebase is currently closed, but is planned on being open ASAP.
