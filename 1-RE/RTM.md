# Requirements Traceability Matrix — Simple Shell

| Req ID | Requirement Area | Jira | Design/Implementation | Test |
|---|---|---|---|---|
| FR-01 | Interactive shell | SH-12 | `shell.c` | TC-01 |
| FR-02 | External commands | SH-15 | `executor.c` | TC-02 |
| FR-03 | Built-ins | SH-13 | `builtins.c` | TC-03 |
| FR-04 | Parsing | SH-14 | `parser.c` | TC-04 |
| FR-05 | Quoted arguments | SH-14 | `parser.c` | TC-05 |
| FR-06 | Input redirection | SH-17 | `redirect.c` | TC-06 |
| FR-07 | Output redirection | SH-17 | `redirect.c` | TC-07 |
| FR-08 | Append redirection | SH-17 | `redirect.c` | TC-08 |
| FR-09 | Pipelines | SH-18 | `pipeline.c` | TC-09 |
| FR-10 | Background execution | SH-19 | `executor.c` | TC-10 |
| FR-11 | Error handling | SH-16 | execution/error handling | TC-11 |
| FR-12 | Termination | SH-12 | `shell.c` | TC-12 |
| NFR-01 | Reliability | SH-20 | Test suite | NFR-T01 |
| NFR-02 | Performance | SH-21 | Execution benchmark | NFR-T02 |
| NFR-03 | Usability | SH-22 | CLI behavior/docs | NFR-T03 |
| NFR-04 | Portability | SH-21 | Makefile/CI | NFR-T04 |
| NFR-05 | Maintainability | SH-21 | Modular source structure | NFR-T05 |
| NFR-06 | Memory safety | SH-21 | Sanitizers/Valgrind | NFR-T06 |
| NFR-07 | Testability | SH-20 | Automated tests | NFR-T07 |
| NFR-08 | Documentation | SH-22 | `docs/` and README | NFR-T08 |
