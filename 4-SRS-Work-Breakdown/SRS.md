# Software Requirements Specification (SRS)
## Simple Shell — Individual Submission

**Project:** Simple Shell (Command-Line Interpreter)  
**Language:** C  
**Team:** H1  
**Repository:** https://github.com/ShrikarDesai07/simple-shell  
**Individual repository:** https://github.com/ShrikarDesai07/SimpleShell_Shrikar  
**Jira project:** SH — Simple Shell

---

## 1. Purpose

The purpose of the Simple Shell project is to develop a lightweight Unix-like command-line interpreter in C. The shell accepts commands from a user, parses the command line, executes built-in and external commands, manages processes, and supports selected Unix shell features such as I/O redirection, pipelines, and background execution.

This SRS defines the functional and non-functional requirements that guide the design, implementation, and testing of the system.

## 2. Scope

### In scope

- Interactive command prompt and input loop.
- Built-in commands: `cd`, `pwd`, `echo`, `help`, and `exit`.
- External command execution.
- Command tokenization and parsing.
- Quoted arguments within the agreed parser scope.
- Input redirection `<`.
- Output redirection `>`.
- Append redirection `>>`.
- Pipelines using `|`.
- Background execution using `&`.
- Process synchronization and child-process cleanup.
- Error handling.
- Automated testing and memory-safety checks.

### Out of scope

Unless explicitly added later, the project does not attempt to implement a complete POSIX shell. Advanced job-control features such as full terminal process-group management, shell scripting languages, command substitution, globbing, aliases, and shell-specific scripting features are outside the initial scope.

## 3. Users and Actors

### User

The user interacts with the shell by entering commands and observing output or error messages.

### Operating System

The operating system provides process creation, program execution, file descriptors, files, pipes, and process synchronization.

## 4. Functional Requirements

| ID | Requirement |
|---|---|
| FR-01 | The shell shall display an interactive prompt and accept user commands. |
| FR-02 | The shell shall execute valid external commands. |
| FR-03 | The shell shall support `cd`, `pwd`, `echo`, `help`, and `exit`. |
| FR-04 | The shell shall parse commands into executable arguments. |
| FR-05 | The shell shall support quoted arguments within the agreed parser scope. |
| FR-06 | The shell shall support input redirection using `<`. |
| FR-07 | The shell shall support output redirection using `>`. |
| FR-08 | The shell shall support append redirection using `>>`. |
| FR-09 | The shell shall support pipelines using `|`. |
| FR-10 | The shell shall support background execution using `&`, subject to the approved project scope. |
| FR-11 | The shell shall report command and system-call errors without crashing. |
| FR-12 | The shell shall terminate cleanly on `exit` or end-of-file. |

## 5. Non-Functional Requirements

| ID | Category | Requirement |
|---|---|---|
| NFR-01 | Reliability | Normal valid commands should not crash the shell. |
| NFR-02 | Performance | The shell should introduce minimal overhead for simple commands. |
| NFR-03 | Usability | Prompt and error messages should be consistent and understandable. |
| NFR-04 | Portability | The project should build on the agreed Linux/GCC environment. |
| NFR-05 | Maintainability | Major responsibilities should be separated into maintainable modules. |
| NFR-06 | Memory Safety | Memory and file descriptors should be managed correctly. |
| NFR-07 | Testability | Core behavior should have repeatable automated tests. |
| NFR-08 | Documentation | Setup, architecture, usage, requirements, and testing should be documented. |

## 6. External Interface Requirements

### User interface

The shell provides a terminal-based interface:

```text
$ command [arguments]
```

### Operating-system interface

The implementation may use standard POSIX/Linux interfaces including:

- `fork()`
- `execvp()`
- `waitpid()`
- `chdir()`
- `getcwd()`
- `open()`
- `dup2()`
- `pipe()`
- `close()`

## 7. System Constraints

- The implementation language is C.
- The primary target is a Linux environment.
- The project must be buildable with GCC.
- The implementation must avoid unnecessary dependence on non-standard libraries.
- System-call failures must be handled appropriately.
- The shell must not terminate unexpectedly for ordinary invalid user input.

## 8. Acceptance Criteria

The implementation will be considered functionally complete when:

1. The shell starts and displays a prompt.
2. Built-in commands operate correctly.
3. External commands execute correctly.
4. Invalid commands generate useful errors.
5. Supported quoting/parsing behavior works.
6. `<`, `>`, and `>>` work as specified.
7. Pipelines work for supported command chains.
8. Background commands work if included in the final approved scope.
9. `exit` and EOF terminate the shell cleanly.
10. Automated tests pass.
11. The project builds cleanly with the configured compiler warnings.
12. Documentation and the RTM are updated with implementation and test evidence.

## 9. Traceability

The requirements are linked to the Jira project `SH`, the team GitHub repository, implementation modules, and test cases through the RTM.

Relevant Jira work includes:

- SH-7 — Problem statement and feasibility
- SH-8 — SRS
- SH-9 — RTM
- SH-10 — Actors/use case
- SH-11 — Validation
- SH-12 to SH-19 — implementation features
- SH-20 to SH-22 — testing, quality, documentation, and release

## 10. Approval

This document is prepared as the project SRS and should be reviewed by the project team and instructor before final academic submission.
