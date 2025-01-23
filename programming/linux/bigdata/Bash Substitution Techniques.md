## 1. Variable Substitution

Replaces a variable with its value.

### Syntax
```bash
$variable
${variable}
```

### Example
```bash
name="Alice"
echo "Hello, $name"  # Output: Hello, Alice
```

**Default Value**: Use a default value if the variable is unset or empty.
  ```bash
  echo ${name:-"Guest"}  # Output: Alice (or Guest if name is unset)
  
  ${variable:-default} # Checks for both unset and empty string
  ${variable-default} # Only checks if variable is unset
  ```

**Assign Default Value**: Assign a default value if the variable is unset or empty.
  ```bash
  echo ${name:="Guest"}  # Output: Alice (or Guest if name is unset, and assigns Guest to name)
  ```

## 2. Command Substitution

Replaces a command with its output.

### Syntax
- Backticks: `` `command` ``
- `$(command)` (preferred)

### Example
```bash
echo "Today is $(date)"  # Output: Today is [current date and time]
```

## 3. Arithmetic Substitution

Replaces an arithmetic expression with its result.

### Syntax
```bash
$((expression))
```

### Example
```bash
sum=$((5 + 3))
echo "The sum is $sum"  # Output: The sum is 8
```

## 4. Process Substitution

Treats the output or input of a command as a file.

### Syntax
- Input Substitution: `<(command)`
- Output Substitution: `>(command)`

### Example
```bash
diff <(ls /dir1) <(ls /dir2)  # Compare the output of two commands
grep "warning" <(journalctl) system.log application.log == 
journalctl | grep "warning" - system.log (pipes , '-' stands for standard input)
```

## 5. Filename Expansion (Globbing)

Matches filenames using wildcards.

### Syntax
- `*`: Matches any number of characters
- `?`: Matches a single character
- `[abc]`: Matches any one of the characters inside the brackets

### Example
```bash
ls *.txt  # List all .txt files in the current directory
```

## 6. Tilde Expansion

Expands to home directories.

### Syntax
- `~`: Expands to the current user's home directory
- `~username`: Expands to the home directory of the specified user

### Example
```bash
echo ~      # Output: /home/username
echo ~root  # Output: /root
```

## 7. Brace Expansion

Generates strings by expanding patterns within braces.

### Syntax
```bash
{pattern1,pattern2,...}
```

### Example
```bash
echo file{1,2,3}.txt  # Output: file1.txt file2.txt file3.txt
echo {A..C}           # Output: A B C
```

## 8. Parameter Expansion

Manipulates and transforms variables.

### Syntax
```bash
${variable#pattern}   # Remove shortest match of pattern from the beginning
${variable##pattern}  # Remove longest match of pattern from the beginning
${variable%pattern}   # Remove shortest match of pattern from the end
${variable%%pattern}  # Remove longest match of pattern from the end
${variable/pattern/replacement}   # Replace first match of pattern
${variable//pattern/replacement}  # Replace all matches of pattern
```

### Example
```bash
filename="file.txt"
echo ${filename%.*}  # Output: file (remove .txt)
echo ${filename#f}   # Output: ile.txt (remove 'f' from the beginning)
```

## 9. History Expansion

Reuses commands from the shell's history.

### Syntax
- `!!`: Repeats the last command
- `!n`: Repeats the command with history number `n`
- `!string`: Repeats the most recent command starting with `string`

### Example
```bash
!!        # Repeats the last command
!ls       # Repeats the most recent command starting with 'ls'
!42       # Repeats the command with history number 42
```