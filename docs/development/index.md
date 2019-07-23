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


## Repositories

| Repo | URL |
|------|-----|
| API | https://github.com/joyent/conch |
| Shell | https://github.com/joyent/conch-shell |
| UI | https://github.com/joyent/conch-ui |

Other code may be in private repositories and/or behind a VPN. Ask a member of
the Conch team for more info.

## Process

All software is developed using [git](https://git-scm.com/) and the vast
majority of our code lives in [Github](https://github.com/joyent). As a rule,
we default to open source using the MPL2 license. There are situations where
code may be deemed too sensitive or too specific to a given client for the code
to be fully open.  These are fairly rare situations, however, and our preference
is to be as open as possible. 

In most repositories, 'master' is a protected branch. Users cannot push to
master directly and changes must be merged in via a pull request. Pull requests
almost universally require another developer to approve the changes. Most
repositories are also tied into
[Buildbot](https://svc.conch.joyent.us/buildbot) and must pass tests before a
PR can be merged. This level of process is designed to help hold the team
accountable for code changes and we strive for consensus in application designs
and implementation.

## Testing

The Conch API has an extensive test suite. As a general rule, incoming PRs must
be accompanied by tests and all tests must pass. Tests will be run by Buildbot
whenever a user pushes code up to Github (including topic and personal
branches) as well as when a PR is sent. We do not require topic and personal
branches to pass tests until they are ready for a PR.

The Conch Shell has a small but growing test suite. As with the API, tests must
pass for a PR. More importantly, being a Go application, incoming code must be
formatted using gofmt and must pass gometalinter checks for best practices. See
the Makefile for the list of linters run during tests. Further, every test run
attempts to build the application for all target platforms. PRs must pass tests,
linter checks, and must build on all target platforms.


## Releases

The Conch API, UI, Stats, and Shell are all released using git tags, formatted
in [SemVer](https://semver.org/) style. In the case of the API and Shell,
releases are managed via Buildbot. When a user pushes up a new tag, Buildbot
executes the test suite. If tests pass, a new Github release is created, using
the tag's commit message as the body
([example](https://github.com/joyent/conch/releases/tag/v2.11.0)).  

For the API and Shell, we've been building the tag body using a Ruby app named
[github-changelog-generator](https://github.com/github-changelog-generator/github-changelog-generator)
and copying in the data for just the current release.

## Buildbot

Our [Buildbot](https://svc.conch.joyent.us/buildbot) setup is managed via
Ansible. A Conch developer can provide a pointer to that repo. Currently,
Buildbot executes all its work on a single FreeBSD KVM. To add a new repo to
Buildbot, the master configuration must be updated and a Github webhook must be
added to the repository. The Conch API repo can be used as an example.

## Similar Products

* The Foreman
* Collins
* netbox
* device42
* Commercial CMMS (e.g., Fiix)
* GitHub Metal Cloud

