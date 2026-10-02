# Software Testing — Individual Evidence

**Student:** Shrikar Desai  
**Project:** Simple Shell (Command-Line Interpreter)  
**Team:** H1  
**Language:** C

## Purpose

This folder documents the testing approach for the Simple Shell project. It covers
functional testing, parser testing, process execution, shell features, negative
cases, and traceability to the project requirements.

## Contents

- `Test_Plan.md` — testing objectives, scope, strategy, environment and entry/exit criteria.
- `Test_Cases.md` — detailed functional and negative test cases.
- `Test_Execution_Report.md` — execution record and observed results from the available project test suite.
- `screenshots/` — reserved for actual screenshots of test execution/results.

## Evidence policy

Only actual execution evidence should be placed in `screenshots/`. Do not fabricate
screenshots or test results. If additional tests are run locally, update the execution
report with the actual command, date, result and observations.

## Project test layers

The project uses:
1. Automated parser tests.
2. Shell integration tests.
3. Manual functional checks for interactive features where appropriate.

## Traceability

Testing is linked to the functional/non-functional requirements and Jira work items
defined for the Simple Shell project, especially SH-20 (automated parser and shell
tests), SH-21 (build/CI/memory-safety checks), and the corresponding implementation
tasks.
