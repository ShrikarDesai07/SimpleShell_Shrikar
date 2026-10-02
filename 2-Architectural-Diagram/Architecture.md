# 2 — Architectural Diagram

## Simple Shell — High-Level Architecture

The Simple Shell is organized as a modular command-processing system. The user enters a command through the interactive shell. The command is parsed, classified as a built-in or external command, and then executed. Redirection and pipelines modify file-descriptor connections before execution.

### Main components

1. **Input/Shell Loop** — displays the prompt, reads input, handles EOF, and controls the shell lifecycle.
2. **Tokenizer/Parser** — converts the command line into tokens and identifies arguments, quotes, redirection, pipes, and background execution.
3. **Built-in Handler** — executes commands that must affect the shell process itself, such as `cd` and `exit`.
4. **Command Executor** — creates child processes and launches external programs using `fork()` and `execvp()`.
5. **I/O Redirection** — connects standard input/output to files using `open()` and `dup2()`.
6. **Pipeline Manager** — connects processes through Unix pipes using `pipe()` and file descriptors.
7. **Process Management** — waits for foreground processes and handles background child cleanup.
8. **Operating System** — provides process, file, pipe, and terminal services.

## Processing flow

```text
User
  |
  v
Interactive Shell Loop
  |
  v
Tokenizer / Parser
  |
  +--------------------+
  |                    |
  v                    v
Built-in Handler    Command Executor
  |                    |
  |              +-----+------+
  |              |            |
  |              v            v
  |        I/O Redirection  Pipeline Manager
  |              |            |
  |              +-----+------+
  |                    |
  +--------------------+
           |
           v
     Process Management
           |
           v
    Operating System
           |
           v
        Output
```

## Key design decision

`cd` is handled by the shell process rather than a child process because changing directory in a child would not change the working directory of the parent shell.

## External interfaces

- Standard input (`stdin`) — user command input.
- Standard output (`stdout`) — command output and prompt.
- Standard error (`stderr`) — error messages.
- Unix process API — `fork()`, `execvp()`, `waitpid()`.
- File descriptor API — `open()`, `dup2()`, `close()`.
- Pipe API — `pipe()`.

## Architectural quality goals

- **Modularity:** responsibilities are separated into logical components.
- **Testability:** parser and execution behavior can be tested independently.
- **Maintainability:** features can be extended without rewriting the entire shell.
- **Reliability:** system-call failures are checked and reported.
- **Resource safety:** processes, memory, and file descriptors are explicitly managed.
