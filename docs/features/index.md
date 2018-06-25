# Features

### Architecture

- [x] Multi-tentant web service
- [x] Basic user roles
- [x] Rest APIs
- [x] CLI tool
- [x] Workspaces
- [x] Validation engine
- [x] User settings (KV)
- [x] Device settings (KV)
- [x] Feature flags
- [ ] Validation configuration
- [ ] Organizations
- [ ] Organization settings (KV)
- [x] Korean localization (partial)

### Datacenter Design and Visualization

- [x] Basic hardware profile support
- [ ] Robust hardware profile support
- [ ] IPAM
- [ ] BOM designer
- [ ] Rack designer
- [ ] Datacenter designer
- [ ] Design review and approval

### Asset Management

- [x] Server tracking
- [x] TOR tracking
- [ ] Component database
- [ ] Parts and supply tracking
- [ ] Preventative maintenance
- [ ] Maintenance schedules
- [ ] Work orders via JIRA integration or similar
- [ ] Spare management
- [ ] Build reports
- [ ] Failure reports
- [ ] Validation/audit reports

### Procurement and RFQs

- [ ] Emit full BOMs from a datacenter workspace

### Preflight

"Preflight" is the initial stage of a device entering service. This may happen
during hardware integration, or during datacenter standup.

- [x] Embedded Relay Devices for off-site usage (rack integration)
- [x] Linux-based live system (PXE booted)
- [x] Server firmware upgrade
- [x] Server configuration
- [x] Server validation
- [x] Server burnin
- [x] TOR firmware upgrade
- [x] TOR configuration
- [x] TOR basic validation
- [ ] TOR extended validation
- [ ] TOR burnin
- [x] Server/TOR network map validation
- [ ] Network stress testing (intra-rack)
- [ ] Network stress testing (inter-rack)
- [ ] Network stress testing (cross-DC)
- [ ] Burnin/stress metrics stored in TSDB
- [x] PDU firmware upgrade
- [x] PDU configuration
- [ ] Server/PDU power map
- [ ] Multi-OS boot
- [ ] Multi-OS burnin

### Services Standup

- [ ] Admin server
- [ ] Triton Headnode
- [ ] Triton Compute Node
- [ ] Manta initial install
- [ ] Manta storage expansion
- [ ] Manta metadata expansion

### Device Production

Production is the longest (hopefully!) stage of a device during its lifecycle.

- [x] VM-based Relay software for on-site usage
- [ ] Agent-based version of the livesys reporter
- [ ] Diagnostics mode

### Device Retirement

- [ ] API and UI for marking devices retired
