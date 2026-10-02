# Non-Functional Requirements — Simple Shell

| ID | Category | Requirement | Verification |
|---|---|---|---|
| NFR-01 | Reliability | Normal valid commands shall not crash the shell. | Integration and regression tests. |
| NFR-02 | Performance | The shell should add minimal overhead for simple foreground commands. | Basic execution benchmark. |
| NFR-03 | Usability | The prompt and error messages shall be understandable and consistent. | Manual usability review. |
| NFR-04 | Portability | The project shall build on the agreed Linux/GCC environment. | Clean build on target Linux environment. |
| NFR-05 | Maintainability | Parsing, built-ins, execution, redirection, and pipelines shall be separated into maintainable modules. | Code review and repository structure review. |
| NFR-06 | Memory Safety | Dynamically allocated memory shall be released and file descriptors shall be closed appropriately. | AddressSanitizer/Valgrind checks where available. |
| NFR-07 | Testability | Core functionality shall have repeatable automated tests. | Test suite execution. |
| NFR-08 | Documentation | Setup, supported features, architecture, requirements, and testing shall be documented. | Documentation review. |
