# ubuntu22_cis — Ansible role (ubuntu22-cis)

**Ansible hardening role** for **Ubuntu 22.04 LTS**, generated from the CIS Ubuntu Linux 22.04 LTS Benchmark profiles in ComplianceAsCode SSG 0.1.82. Suitable for playbooks, Packer/Ansible provisioners, and golden-image pipelines. Search keywords: `ansible`, `ansible-role`, `cis`, `cis-benchmark`, `cis-hardening`, `compliance`, `devsecops`, `hardening`, `infrastructure`, `jammy`, `openscap`, `security`, `stigforge`, `ubuntu`.

StigForge-exported Ansible role **`ubuntu22_cis`** · release **`0.3.51`**.
Matrix cell status: **`green`**.

## Before you run this role

Each default below changes how a running host behaves. Read them before you apply the role to a host you depend on.

### Passwords that root sets must meet the password quality rules

_Requirement: ComplianceAsCode rule `accounts_password_pam_enforce_root`, selected by the CIS profile for this product._

**What the role does.** Adds `enforce_for_root` to /etc/security/pwquality.conf, where the pwquality library is installed. pam_pwquality then rejects a password root sets (for root or for another user, with passwd) that fails the length and complexity rules, instead of only warning.

**Who is affected.** Administrators and provisioning scripts that set passwords as root through PAM (passwd): a password that does not meet the quality rules in /etc/security/pwquality.conf is now refused.

**How to change it.** Set `ubuntu22cis_accounts_password_pam_enforce_root: false` before the first run. If the role has already run, delete the `enforce_for_root` line from /etc/security/pwquality.conf.

**Effect on compliance.** With `ubuntu22cis_accounts_password_pam_enforce_root` set to false, the role no longer remediates that CIS rule, and an OpenSCAP scan reports it as failing unless the host already meets it.

### sudo asks for the password again after 15 minutes

_Requirement: ComplianceAsCode rule `sudo_require_reauthentication`, selected by the CIS profile for this product._

**What the role does.** Writes `Defaults timestamp_timeout=15` to /etc/sudoers (the value of `var_sudo_timestamp_timeout`), checking that edit with visudo, and deletes every `Defaults ... timestamp_timeout` line from the files in /etc/sudoers.d (those deletions are not checked with visudo). sudo then caches a password for 15 minutes per terminal instead of the sudo default.

**Who is affected.** Administrators, and scripts or automation, that run sudo with a password: they are prompted again once the cached password expires. A timestamp_timeout someone set in /etc/sudoers.d is removed. Users whose sudoers entry is NOPASSWD are not prompted either way.

**How to change it.** Set `var_sudo_timestamp_timeout` to the number of minutes sudo should cache a password; the role writes that value. To leave sudo's timeout alone, set `ubuntu22cis_sudo_require_reauthentication: false` before the first run.

**Effect on compliance.** With `ubuntu22cis_sudo_require_reauthentication` set to false, the role no longer remediates that CIS rule, and an OpenSCAP scan reports it as failing unless the host already meets it. A `var_sudo_timestamp_timeout` other than the profile's value is written as set; a scan checks the profile's value, so it reports the rule as failing unless the scan is tailored to the same value.

## Install

This repository root **is** the Ansible role (Galaxy-style layout). Release metadata and the
scoring helper live under `compliance/` and are not loaded when the role runs.

From **GitHub** (public):

```yaml
# requirements.yml
roles:
  - src: https://github.com/stigready/ubuntu22-cis
    scm: git
    version: v0.3.51   # or an immutable commit SHA
    name: ubuntu22_cis
```

```bash
ansible-galaxy role install -r requirements.yml -p ./roles
ansible-playbook -i inventory site.yml   # role: ubuntu22_cis
```

## Verification status (this release)

This release carries no per-role OpenSCAP score, and no OpenSCAP results ship with it. A container
cannot evaluate most hardening rules, so the role is not scored here. To score a host you hardened
with it, see *Score it yourself*. `compliance/releases/0.3.51/manifest.json` records this.

## Reports & review

- **[reports/index.html](reports/index.html)** — HTML report index
- **[CHANGELOG.md](CHANGELOG.md)** — release notes

## Score it yourself

This repository ships no OpenSCAP results (see *Verification status*). To score a host you
hardened with this role, run `oscap xccdf eval` on it and score the `results.xml` with this role's
exception list: see **[compliance/README.md](compliance/README.md)**.

## Notices

StigForge and StigReady are independent. They are not affiliated with, endorsed by or certified by the Center for Internet Security, Inc. (CIS), the Defense Information Systems Agency (DISA), the U.S. Department of Defense, NIST, Canonical or the ComplianceAsCode project. "CIS" and "CIS Benchmarks" are trademarks of the Center for Internet Security, Inc. DISA STIGs are DISA publications. Ubuntu is a trademark of Canonical Ltd. Linux is the registered trademark of Linus Torvalds in the U.S. and other countries. All trademarks are the property of their respective owners. This role applies ComplianceAsCode (SSG 0.1.82) remediation from SSG's CIS Ubuntu Linux 22.04 LTS Benchmark profiles. An OpenSCAP score is a measurement, not a certification.

## License

Copyright (c) 2026 StigReady.

- **[LICENSE](LICENSE)** (MIT) — StigForge export packaging
- **[NOTICE](NOTICE)** — ComplianceAsCode / BSD-3-Clause task body attribution

## Catalog

- [https://stigready.com/#stigforge](https://stigready.com/#stigforge)

