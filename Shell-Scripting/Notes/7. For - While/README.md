### While Loop in Shell Scripting

#### Definition:
The "While" loop in shell scripting allows you to repeatedly execute a block of commands as long as a specified condition is true. It's commonly used when the number of iterations is not known beforehand, or when you want to continue looping until a certain condition is met.

#### Syntax:
The syntax of a "While" loop in shell scripting is as follows:
```bash
while [ condition ]; do
  # Commands to execute as long as condition is true
done
```
- `condition` is a test that is evaluated before each iteration of the loop. If the condition is true, the loop continues; otherwise, it exits.

#### Example Usage:
```bash
#!/bin/bash

# Initialize a counter
counter=1

# Execute the loop while counter is less than or equal to 5
while [ $counter -le 5 ]; do
  echo "Counter: $counter"
  ((counter++))  # Increment the counter
done
```
Output:
```
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
```

#### Infinite Loop:
You can create an infinite loop by omitting the condition, but be cautious as it may cause your script to hang if not properly controlled.
```bash
#!/bin/bash

# Infinite loop
while true; do
  echo "This is an infinite loop"
  sleep 1  # Add a delay to prevent CPU overload
done
```

#### Reading Input with While Loop:
You can use a "While" loop to read lines from a file or input stream until a specific condition is met.
```bash
#!/bin/bash

# Read lines from a file until end of file is reached
while IFS= read -r line; do
  echo "Line read: $line"
done < input.txt
```

#### Important Notes:
- Be careful to ensure that the condition in the "While" loop eventually becomes false to avoid infinite loops.
- Use caution when using infinite loops to prevent unintended consequences, such as CPU overload or system crashes.
- "While" loops can be nested within other loops or conditional statements for more complex control flow.

#### Summary:
The "While" loop in shell scripting allows you to repeatedly execute commands as long as a specified condition remains true. Whether it's iterating over a sequence of numbers, processing input lines, or creating infinite loops, understanding how to use "While" loops is essential for writing efficient and flexible shell scripts.