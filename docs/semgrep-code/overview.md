---
slug: overview
append_help_link: true
title: Overview
hide_title: false
description: Learn about Code, a static application security testing (SAST) tool |
    designed to find seucurity vulnerabilities in your applications.
tags:
  - code
---

import MoreHelp from "/src/components/MoreHelp"
import SemgrepScan from "/src/components/concept/_semgrep-scan.mdx"

Semgrep Code is a static application security testing (SAST) tool that inspects your application for security vulnerabilities.

## Rules

<SemgrepScan />

In addition to the default rules (available in the [Registry](https://semgrep.dev/r)), you can write custom rules to determine how Semgrep scans your code. Regardless of whether you use with Semgrep's default rules or write custom rules, knowing *which* rules Semgrep ran against your code helps you understanding how Code detected security issues.

## OSS vs. Pro Engine

By default, Code is powered by Semgrep's OSS engine. It is capable of analyzing interactions within a single function (this process is known as intraprocedural analysis), and its smaller scope of analysis makes it faster and easier to integrate into developer workflows.

However, if you would like cross-file analysis and cross-function analysis (also known as interfile analysis and interprocedural analysis, respectively), please consider using the [Pro engine](/semgrep-code/semgrep-pro-engine-intro/).

## Findings

Semgrep displays findings identified by Code in the Cloud Platform. Additionally, the Cloud Platform allows you to:

* Triage findings;
* Send alerts and notifications or create tickets to track findings identified by Code;
* Customize the way Semgrep scans your projects;
* Manager your users and facilitate team collaboration in remediating security issues.

## Next steps

[Scan your codebase](/semgrep-code/getting-started): Learn how to scan your project by integrating Code into your CI/CD pipeline, or how to scan projects available locally on your machine.

<MoreHelp />
