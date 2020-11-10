<!--
SPDX-FileCopyrightText: 2020 Helmholtz Centre for Environmental Research (UFZ)
SPDX-FileCopyrightText: 2020 Helmholtz-Zentrum Dresden-Rossendorf (HZDR)

SPDX-License-Identifier: Apache-2.0
-->

# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

Group your changes into these categories:

`Added`, `Changed`, `Deprecated`, `Removed`, `Fixed`, `Security`.

## Unreleased

[List of commits](https://gitlab.com/hifis/ansible/keepalived-role/-/compare/v0.3.0...master)

### Added
- Enable check-mode
  ([!27](https://gitlab.com/hifis/ansible/keepalived-role/-/merge_requests/27)
  by [Normo](https://gitlab.com/Normo)).

## [0.3.0](https://gitlab.com/hifis/ansible/keepalived-role/-/releases/v0.2.1) - 2020-09-25

[List of commits](https://gitlab.com/hifis/ansible/keepalived-role/-/compare/v0.2.1...v0.3.0)

### Changed
- Enable keepalived process tracking
  ([!19](https://gitlab.com/hifis/ansible/keepalived-role/-/merge_requests/19)
  by [tobiashuste](https://gitlab.com/tobiashuste)).
- Make CI jobs interruptible to support auto-cancellation
  ([!21](https://gitlab.com/hifis/ansible/keepalived-role/-/merge_requests/21)
  by [tobiashuste](https://gitlab.com/tobiashuste)).
- Cache pipenv dependencies in .gitlab-ci.yml
  ([!22](https://gitlab.com/hifis/ansible/keepalived-role/-/merge_requests/22)
  by [tobiashuste](https://gitlab.com/tobiashuste))

### Fixed
- Fix runtime directory not being available after reboot
  ([!20](https://gitlab.com/hifis/ansible/keepalived-role/-/merge_requests/20)
  by [tobiashuste](https://gitlab.com/tobiashuste)).

## [0.2.1](https://gitlab.com/hifis/ansible/keepalived-role/-/releases/v0.2.1) - 2020-08-20

[List of commits](https://gitlab.com/hifis/ansible/keepalived-role/-/compare/v0.2.0...v0.2.1)

### Fixed
- Fix mandatory variables check for `keepalived_virtual_ipaddress_configs`
  ([!17](https://gitlab.com/hifis/ansible/keepalived-role/-/merge_requests/17)
  by [tobiashuste](https://gitlab.com/tobiashuste)).

## [0.2.0](https://gitlab.com/hifis/ansible/keepalived-role/-/releases/v0.2.0) - 2020-08-18

[List of commits](https://gitlab.com/hifis/ansible/keepalived-role/-/compare/v0.1.0...v0.2.0)

### Added
- Optionally allow to specify multiple virtual IP addresses
([!16](https://gitlab.com/hifis/ansible/keepalived-role/-/merge_requests/16)
by [tobiashuste](https://gitlab.com/tobiashuste)).

## [0.1.0](https://gitlab.com/hifis/ansible/keepalived-role/-/releases/v0.1.0) - 2020-08-14

### Added
Initial release of the Ansible Keepalived Role.
