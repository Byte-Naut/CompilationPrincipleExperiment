# Compiler Front-End Coursework

> [!IMPORTANT]
> This repository contains coursework completed in 2021 for a compiler-principles course.
> It is provided for educational reference only. It is not a production compiler and is no longer maintained; compatibility with current Python versions and dependencies is not guaranteed.

[中文说明](README.zh-CN.md)

## Overview

This project implements the early front-end stages of a small compiler in Python:

- a YAML-configured lexical analyzer;
- FIRST and FOLLOW set computation;
- LR item-set construction;
- SLR-style ACTION and GOTO table generation;
- shift-reduce parsing;
- basic panic-mode syntax error recovery;
- a multiprocessing pipeline between the lexer and parser.

The example grammar recognizes a limited C-like language. It is not intended to implement the complete C language.

## Scope

Implemented:

- lexical analysis;
- token generation;
- parsing-table construction;
- SLR parsing;
- basic lexical and syntax error reporting.

Not implemented:

- semantic analysis;
- type checking;
- intermediate representation;
- optimization;
- code generation;
- linking or executable generation.

## Requirements

The project was originally developed with Python 3 in 2021. The exact original dependency versions were not recorded.

Known dependencies:

- PyYAML
- pandas

Install them with:

```bash
python -m pip install -r requirements.txt
```

No ongoing compatibility support is provided for newer Python or dependency versions.

## Running the Example

Run commands from the repository root:

```bash
python main.py
```

The example input is located at:

```text
test/test_lexical_input.txt
```

The program prints the generated FIRST and FOLLOW sets, LR item sets, parsing tables, lexical or syntax errors, and the applied production sequence.

## Project Structure

```text
lexical_analysis/       Lexer implementation and YAML state definitions
syntax_analysis/        SLR table generation and parser implementation
test/                   Example input and manual lexer test
main.py                 Lexer-parser pipeline entry point
utils.py                Token definitions, grammar, and output helpers
```

## Testing Status

The repository contains example-driven manual tests. It does not contain a modern automated test suite with assertions or continuous integration.

## Security and Limitations

The lexer configuration is bundled with the repository and should be treated as trusted input. The historical implementation evaluates expressions loaded from the YAML configuration and must not be used with untrusted configuration files.

This project is preserved as coursework and should not be used as a production parser or as the basis of a security-sensitive application.

## Academic Integrity

This repository is provided for educational reference. Do not submit this project, or substantial parts of it, as your own coursework.

## License

See [LICENSE](LICENSE).
