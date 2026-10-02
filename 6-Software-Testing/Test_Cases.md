# Test Cases

## Functional Test Cases

| ID | Test | Input / Action | Expected Result |
|---|---|---|---|
| TC-01 | Shell startup | Launch shell | Shell displays prompt and accepts input |
| TC-02 | Empty input | Press Enter on empty line | Shell remains active without crashing |
| TC-03 | `pwd` | `pwd` | Prints current working directory |
| TC-04 | `echo` | `echo hello` | Prints `hello` |
| TC-05 | `help` | `help` | Displays supported command/help information |
| TC-06 | `cd` valid | `cd <existing-directory>` followed by `pwd` | Working directory changes |
| TC-07 | `cd` invalid | `cd <nonexistent-directory>` | Error is reported; shell continues |
| TC-08 | External command | `ls` or another available executable | External program executes and shell returns appropriately |
| TC-09 | Quoted argument | `echo "hello world"` | Quoted text is treated as one argument |
| TC-10 | Input redirection | `cat < input.txt` | Reads command input from `input.txt` |
| TC-11 | Output redirection | `echo hello > output.txt` | File is created/overwritten with expected output |
| TC-12 | Append redirection | `echo world >> output.txt` | Output is appended to the existing file |
| TC-13 | Pipeline | `cat input.txt | grep word` | Output of first command becomes input of second |
| TC-14 | Background execution | `sleep 1 &` | Command runs without blocking the interactive shell |
| TC-15 | Unknown command | `command_that_does_not_exist` | Execution error is reported and shell remains usable |
| TC-16 | Missing input file | `cat < missing_file` | Redirection/open error is reported safely |
| TC-17 | Invalid syntax | Malformed redirection/pipeline input | Parser rejects or reports invalid syntax safely |
| TC-18 | Exit | `exit` | Shell terminates cleanly |

## Non-Functional / Robustness Cases

| ID | Test | Expected Result |
|---|---|---|
| NTC-01 | Long command/argument within supported limits | Shell handles input without memory corruption |
| NTC-02 | Repeated commands | Shell remains stable over repeated execution |
| NTC-03 | Repeated parser test suite | Results are deterministic and reproducible |
| NTC-04 | Build from clean checkout | Project builds using documented build command |
| NTC-05 | Automated regression suite | Existing parser and integration tests continue to pass after changes |

## Test Case Execution Fields

For every manually executed case, record:

- Date/time
- Environment
- Tester
- Command/input
- Expected result
- Actual result
- Pass/Fail
- Screenshot or terminal evidence, if required
- Defect/Jira issue if failed
