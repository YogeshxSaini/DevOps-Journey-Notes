### Command-Line Arguments in Shell Scripting

#### Definition:
Command-line arguments are values provided to a script or program when it is executed from the command line. They allow users to pass input to scripts and customize their behavior without modifying the script itself.

#### How Command-Line Arguments Work:
- Command-line arguments are passed to a script as strings separated by spaces.
- They are accessed within the script using special variables called positional parameters.

#### Positional Parameters:
- Positional parameters are variables that hold the command-line arguments passed to the script.
- They are represented by `$1`, `$2`, `$3`, and so on, where `$1` represents the first argument, `$2` represents the second argument, and so forth.
- `$0` represents the name of the script itself.

#### Example Usage:
```bash
#!/bin/bash

# Accessing command-line arguments
echo "Script name: $0"
echo "First argument: $1"
echo "Second argument: $2"
echo "All arguments: $@"
echo "Number of arguments: $#"
```

#### Passing Command-Line Arguments:
- To pass command-line arguments to a script, simply type them after the script's name when executing it from the command line.
- Arguments containing spaces should be enclosed in quotes to be treated as a single argument.

#### Example Execution:
```bash
./script.sh arg1 arg2 "argument 3 with spaces"
```

#### Important Notes:
- Command-line arguments provide a way to customize the behavior of scripts without modifying their code.
- Use positional parameters (`$1`, `$2`, etc.) to access command-line arguments within a script.
- Remember to handle spaces and special characters in arguments appropriately by quoting them.

#### Summary:
Command-line arguments allow users to provide input to scripts and programs when executing them from the command line. Understanding how to access and manipulate these arguments is essential for writing flexible and customizable scripts.