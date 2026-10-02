# Work Breakdown Structure (WBS)
## Simple Shell

## Level 1 — Simple Shell Project

### 1. Requirements Engineering
- 1.1 Problem statement
- 1.2 Feasibility study
- 1.3 Functional requirements
- 1.4 Non-functional requirements
- 1.5 Requirements Traceability Matrix
- 1.6 Actor identification
- 1.7 Use-case diagram
- 1.8 Requirements validation

**Jira:** SH-7 to SH-11

### 2. System Design
- 2.1 High-level architecture
- 2.2 Component/module decomposition
- 2.3 Command-processing flow
- 2.4 Parser design
- 2.5 Process-execution design
- 2.6 File-descriptor/redirection design
- 2.7 Pipeline design
- 2.8 Error-handling design

**Jira:** SH-2 to SH-5 planning/design activities

### 3. Core Shell Implementation
- 3.1 Interactive shell loop
- 3.2 Prompt and input handling
- 3.3 EOF handling
- 3.4 Built-in command framework
- 3.5 `cd`
- 3.6 `pwd`
- 3.7 `echo`
- 3.8 `help`
- 3.9 `exit`

**Jira:** SH-12 and SH-13

### 4. Parsing and Process Execution
- 4.1 Tokenization
- 4.2 Quoted argument handling
- 4.3 Syntax validation
- 4.4 `fork()`
- 4.5 `execvp()`
- 4.6 `waitpid()`
- 4.7 Exit-status handling
- 4.8 Error handling
- 4.9 Resource cleanup

**Jira:** SH-14 to SH-16

### 5. Advanced Shell Features
- 5.1 Input redirection
- 5.2 Output redirection
- 5.3 Append redirection
- 5.4 Pipeline parsing
- 5.5 Pipe creation
- 5.6 Multi-process pipeline execution
- 5.7 Background execution
- 5.8 Child reaping

**Jira:** SH-17 to SH-19

### 6. Testing and Quality
- 6.1 Unit tests
- 6.2 Integration tests
- 6.3 Regression tests
- 6.4 Error-path tests
- 6.5 Sanitizer checks
- 6.6 Valgrind checks where available
- 6.7 Build verification
- 6.8 CI verification

**Jira:** SH-20 and SH-21

### 7. Documentation and Release
- 7.1 README
- 7.2 Architecture documentation
- 7.3 Test report
- 7.4 RTM update
- 7.5 GitHub evidence
- 7.6 Jira evidence
- 7.7 Copilot evidence
- 7.8 Final release/demo preparation

**Jira:** SH-22

## Individual contribution tracking

Individual contribution should be supported by actual GitHub commits, Jira assignments, pull requests/reviews, screenshots, and documented artifacts. Do not claim a contribution that is not supported by repository history or project evidence.
