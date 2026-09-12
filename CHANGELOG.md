# Changelog

Format based on [Keep a Changelog](https://keepachangelog.com/).

## [0.3.0] - 2026-09-12

### Changed
- StigForge export refresh for `ubuntu22_cis` at `0.3.0`.

### Verified (OpenSCAP)

- **`cis-l1`** — score **98.51%** (floor 90.0%) · gate **PASS** · evidence `20260912T124212Z`
  - Remaining counted failures: `file_permissions_ungroupowned, use_pam_wheel_group_for_su`
- **`cis-l2`** — score **98.53%** (floor 90.0%) · gate **PASS** · evidence `20260912T124505Z`
  - Remaining counted failures: `file_permissions_ungroupowned, use_pam_wheel_group_for_su`
- **`cis-ws-l1`** — score **98.47%** (floor 90.0%) · gate **PASS** · evidence `20260912T124702Z`
  - Remaining counted failures: `file_permissions_ungroupowned, use_pam_wheel_group_for_su`
- **`cis-ws-l2`** — score **98.52%** (floor 90.0%) · gate **PASS** · evidence `20260912T124937Z`
  - Remaining counted failures: `file_permissions_ungroupowned, use_pam_wheel_group_for_su`

### Provenance

- Factory pipeline: https://github.com/stigready/stigforge/actions/runs/34693316989
- Factory commit: `562a1f7c1a8e19235ee26e972174d1be6c88998c`

## [0.2.4] - 2026-07-30

### Changed
- StigForge export refresh for `ubuntu22_cis` at `0.2.4`.

### Verified (OpenSCAP)

- **`cis-l1`** — score **95.15%** (floor 90.0%) · gate **PASS** · evidence `20260729T223207Z`
  - Remaining counted failures: `accounts_minimum_age_login_defs, accounts_passwords_pam_faillock_deny, accounts_passwords_pam_faillock_interval, accounts_passwords_pam_faillock_unlock_time, set_password_hashing_algorithm_logindefs`
- **`cis-l2`** — score **96.12%** (floor 90.0%) · gate **PASS** · evidence `20260729T223441Z`
  - Remaining counted failures: `accounts_passwords_pam_faillock_deny, accounts_passwords_pam_faillock_interval, accounts_passwords_pam_faillock_unlock_time, set_password_hashing_algorithm_logindefs`

### Provenance

- Factory pipeline: https://github.com/stigready/stigforge/actions/runs/30496236357
- Factory commit: `7f7cafc85a392bf2a7eb04f1b979185dbcdf5530`

## [0.2.4-private-review] - 2026-07-29

### Changed
- StigForge export refresh for `ubuntu22_cis` at `0.2.4-private-review`.

### Verified (OpenSCAP)

- **`cis-l1`** — score **93.2%** (floor 90.0%) · gate **PASS** · evidence `20260729T100811Z`
  - Remaining counted failures: `account_disable_post_pw_expiration, accounts_maximum_age_login_defs, accounts_minimum_age_login_defs, accounts_passwords_pam_faillock_deny, accounts_passwords_pam_faillock_interval, accounts_passwords_pam_faillock_unlock_time, set_password_hashing_algorithm_logindefs`
- **`cis-l2`** — score **93.2%** (floor 90.0%) · gate **PASS** · evidence `20260729T101107Z`
  - Remaining counted failures: `account_disable_post_pw_expiration, accounts_maximum_age_login_defs, accounts_minimum_age_login_defs, accounts_passwords_pam_faillock_deny, accounts_passwords_pam_faillock_interval, accounts_passwords_pam_faillock_unlock_time, set_password_hashing_algorithm_logindefs`

### Provenance

- Factory pipeline: https://github.com/stigready/stigforge/actions/runs/30440754045
- Factory commit: `c481b47d629f5bc2357a86a933aa6f94f5245fce`

## [0.2.3-private-review] - 2026-07-29

### Added
- Initial StigForge export of matrix role `ubuntu22_cis`.
- OpenSCAP verify evidence bundles per profile under `compliance/releases/`.

### Verified (OpenSCAP)

- **`cis-l1`** — score **93.2%** (floor 90.0%) · gate **PASS** · evidence `20260729T083147Z`
  - Remaining counted failures: `account_disable_post_pw_expiration, accounts_maximum_age_login_defs, accounts_minimum_age_login_defs, accounts_passwords_pam_faillock_deny, accounts_passwords_pam_faillock_interval, accounts_passwords_pam_faillock_unlock_time, set_password_hashing_algorithm_logindefs`
- **`cis-l2`** — score **93.2%** (floor 90.0%) · gate **PASS** · evidence `20260729T083344Z`
  - Remaining counted failures: `account_disable_post_pw_expiration, accounts_maximum_age_login_defs, accounts_minimum_age_login_defs, accounts_passwords_pam_faillock_deny, accounts_passwords_pam_faillock_interval, accounts_passwords_pam_faillock_unlock_time, set_password_hashing_algorithm_logindefs`

### Provenance

- Factory pipeline: https://github.com/stigready/stigforge/actions/runs/30435216810
- Factory commit: `e8e323a3af3258bee63ebc1a873ba26c0cc12049`

## [0.2.1-private-review] - 2026-07-28

### Changed
- Galaxy-style layout: Ansible role at repository root; evidence under `compliance/`.
- Private review tag `v0.2.1-private-review` (supersedes nested `roles/<role>/` export).

## [0.2.0-private-review] - 2026-07-26

### Added
- First private StigForge export to `stigready/*` (factory review; nested role path).
