# Test Plan

## 1. Objectives

The objectives of testing are to verify that the Simple Shell:

- accepts and parses valid commands;
- executes built-in commands correctly;
- executes external programs;
- handles command arguments and quoting;
- performs input/output redirection;
- supports pipelines;
- supports background execution;
- reports invalid input and execution errors safely;
- terminates cleanly;
- remains maintainable and testable through automated tests.

## 2. Scope

### In scope

- Interactive command processing
- Tokenization and parsing
- Built-ins: `cd`, `pwd`, `echo`, `help`, `exit`
- External command execution
- `<`, `>`, `>>`
- `|`
- `&`
- Invalid commands and malformed input
- Process creation/waiting and error handling
- Automated parser and shell integration tests

### Out of scope

- Shell features not specified by the project requirements, such as shell scripting,
  job-control signals, command substitution, environment expansion, and globbing,
  unless explicitly implemented later.

## 3. Test Strategy

### Unit/component testing

The parser is tested independently using representative valid, quoted, redirection,
pipeline, background, and invalid-input cases.

### Integration testing

The shell is exercised through end-to-end command execution to verify interaction
between parsing, built-ins, process creation, redirection, pipelines and waiting.

### Negative testing

Malformed commands, missing files, unknown commands and invalid syntax are included
to verify safe failure behaviour.

### Regression testing

Automated tests should be rerun after changes to parser, executor, process-management,
or shell-feature code.

## 4. Test Environment

Expected development/test environment:

- Ubuntu 22.04 or Ubuntu 24.04
- GCC
- GNU Make
- POSIX/Linux process APIs
- Project source under Git
- Optional CI environment through GitHub Actions

## 5. Entry Criteria

Testing can begin when:

- the project builds successfully;
- source and test files are available;
- required compiler/toolchain is installed.

## 6. Exit Criteria

A test cycle is complete when:

- all planned automated tests have been executed;
- failures are investigated;
- known failures are documented;
- regression tests pass after fixes;
- test evidence is stored in the individual submission where required.

## 7. Defect Handling

For a failed test:

1. Record the test case ID.
2. Record the command/input and expected result.
3. Record the actual result.
4. Identify the affected module.
5. Fix the implementation.
6. Re-run the failed test and relevant regression tests.
7. Update the execution report.

## 8. Requirement Traceability

| Requirement area | Test coverage |
|---|---|
| Command prompt/input | TC-01, TC-02 |
| Built-ins | TC-03 to TC-07 |
| External commands | TC-08 |
| Quoted arguments | TC-09 |
| Input redirection | TC-10 |
| Output redirection | TC-11 |
| Append redirection | TC-12 |
| Pipelines | TC-13 |
| Background execution | TC-14 |
| Error handling | TC-15 to TC-17 |
| Clean termination | TC-18 |
| Regression/automation | Automated parser + shell test suites |

## 9. Test Evidence

Actual terminal/CI screenshots should be placed under `screenshots/`. The files in
this package do not claim screenshots that have not been captured.
