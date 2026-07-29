# Changelog

Format based on [Keep a Changelog](https://keepachangelog.com/).

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
