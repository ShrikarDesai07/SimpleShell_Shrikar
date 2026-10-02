# Functional Requirements — Simple Shell

| ID | Functional Requirement | Acceptance Criterion |
|---|---|---|
| FR-01 | The shell shall display an interactive prompt and accept user commands. | A user can enter multiple commands without restarting the shell. |
| FR-02 | The shell shall execute valid external commands. | Commands such as `ls`, `date`, and `whoami` execute successfully. |
| FR-03 | The shell shall provide built-in commands `cd`, `pwd`, `echo`, `help`, and `exit`. | Each supported built-in produces the expected behavior. |
| FR-04 | The shell shall parse commands into executable arguments. | `echo Hello World` is converted into the correct argument list. |
| FR-05 | The shell shall support quoted arguments within the agreed parser scope. | `echo "Hello World"` treats the quoted text as one argument. |
| FR-06 | The shell shall support input redirection using `<`. | `cat < file.txt` reads from the specified file. |
| FR-07 | The shell shall support output redirection using `>`. | `echo Hello > file.txt` creates/overwrites the file. |
| FR-08 | The shell shall support append redirection using `>>`. | `echo World >> file.txt` appends to the file. |
| FR-09 | The shell shall support pipelines using `|`. | `ls | wc -l` passes the first command's output to the second. |
| FR-10 | The shell shall support background execution using `&`, if enabled in the approved scope. | `sleep 2 &` returns control to the prompt without waiting for completion. |
| FR-11 | The shell shall report command and system-call errors without crashing. | An invalid command produces an error and the shell remains usable. |
| FR-12 | The shell shall terminate cleanly on `exit` or end-of-file. | The shell process terminates and releases resources. |
