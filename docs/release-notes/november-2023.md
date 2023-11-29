---
slug: november-2023
append_help_link: true
hide_title: true
description: >-
  Release notes include the changes, fixes, and additions in specific versions of Semgrep.
toc_max_heading_level: 3
title: November 2023
tags:
  - Release notes
---

# November 2023 release notes

:::tip
- **Semgrep Pro Engine** is now generally available (GA). Team tier users and above can use the Pro Engine to perform **cross-file (interfile)** and **cross-function (intrafile)** analyses. To enable Semgrep Pro Engine:
    1. Sign in to [<i class="fas fa-external-link fa-xs"></i> Semgrep Cloud Platform](https://semgrep.dev/login)
    1. Click **Settings**.
    1. Click the **<i class="fa-solid fa-toggle-large-on"></i> Semgrep Pro Engine** toggle.
- See [<i class="fa-regular fa-file-lines"></i> Semgrep Pro Engine](/semgrep-code/semgrep-pro-engine-intro/) documentation for more information.
- The Semgrep command-line tool now requires **Python 3.8** or later.
:::

## 🔧 Semgrep OSS Engine

:::note
Starting from version 1.46.0, Semgrep is first released in the following ecosystems:
- `pypy`
- `brew`
- `returntocorp/semgrep:canary` (Docker)

If no issues are detected after a few days, the Semgrep team then promotes the `:canary` Docker tag to `:latest`.
:::

- The following versions of Semgrep OSS Engine were released in November 2023:
  - [<i class="fas fa-external-link fa-xs"></i> 1.47.0](https://github.com/returntocorp/semgrep/releases/tag/v1.47.0)
  - [<i class="fas fa-external-link fa-xs"></i> 1.48.0](https://github.com/returntocorp/semgrep/releases/tag/v1.48.0)
  - [<i class="fas fa-external-link fa-xs"></i> 1.49.0](https://github.com/returntocorp/semgrep/releases/tag/v1.49.0)
  - [<i class="fas fa-external-link fa-xs"></i> 1.50.0](https://github.com/returntocorp/semgrep/releases/tag/v1.50.0)

## 🌐 Semgrep Cloud Platform

### Added

- Semgrep now records the languages that invoked the Pro Engine. This enables the Semgrep team to measure the performance impact and error rates of new Pro Engine languages. **For scans that don't send metrics, there is no change.** See [<i class="fas fa-external-link fa-xs"></i> Semgrep Privacy Policy](https://github.com/semgrep/semgrep/blob/develop/PRIVACY.md) for more information.


### Changed

- Elixir language support now requires the Pro Engine. To scan Elixir codebases, enable the Pro Engine. <!-- 9308 -->
- The Semgrep CLI tool now correctly counts the rules that are run on a codebase. Previously, Semgrep counted the total rules in the user's Policies or rulesets, including rules that did **not** have valid targets, and therefore did not actually run. <!-- 9130  -->
- **Semgrep Editor:** Rules created in the editor are private by default. This means only members of  your organization are able to view rules you have created. <!-- 11267 -->

### Fixed

- **API:** Fixed an issue where the severities filter did not return the correct value. <!-- gh-11307 -->


## 💻 Semgrep Code

### Added

- **Findings detail page:** For users that have granted Semgrep code access, you are now able to view **in-app code snippets** in Semgrep Cloud Platform.

<!-- todo add a screenshot -->

### Changed


### Fixed


## ⛓️ Semgrep Supply Chain

## 🤖 Semgrep Assistant (beta)

## 🔐 Semgrep Secrets (beta)

### Added

- Added an optional `--no-secrets-validation` flag to skip secrets validation. To run a secrets scan with no validation, enter `semgrep ci --secrets --no-secrets-validation`.
- **Secrets and Secrets details page:** Added a **<i class="fa-solid fa-ticket"></i> ticket icon** to quickly inform users if a ticket has been created for the finding.

### Changed

- Semgrep Secrets now bypasses `.semgrepignore`. This means that files not typically part of a SAST or SCA scan scope, such as configuration files, are now scanned by Semgrep Secrets. By broadening the scope of Semgrep Secrets scans, it is likelier to find leaked secrets.
    - Previously, Semgrep Secrets excluded targets from `.semgrepignore`. Your findings count may increase with this change.
    - You can still define exclusions from Secrets scanning. To **exclude targets** from Secrets scanning, define files or paths for exclusion in Semgrep Cloud Platform:
        1. Click **Projects**.
        1. Click the Project's **<i class="fa-solid fa-gear"></i> icon**.
        1. You are able to add exclusions through the **Path ignores** text box. 
    - In the future, Semgrep will enable users to define ignores based on the type of scan, whether SAST, SCA, or Secrets. <!-- 9125 (https://github.com/semgrep/semgrep/pull/9125 -->

### Fixed

- Fixed an issue where the Secrets page could freeze due to too many findings. <!-- (11254) -->
- Fixed a bug where enabling the secret beta causes the default scan mode to be  
    set to OSS, even when the Pro flag is turned on in the web UI. (ea-248)

Secrets: metadata overrides specified in validators were incorrectly applied on
top of one another (on a per-rule basis), so that only the last was applied.
Each update is now correctly applied independently to each finding based on the
rule's validators. (scrt-231)

## 📝 Documentation and knowledge base

