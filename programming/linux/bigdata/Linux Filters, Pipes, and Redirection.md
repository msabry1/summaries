## 1. Filters

Filters are commands that take input, process it, and produce output. They are often used in combination with pipes (`|`) to transform or filter data.

### Common Filter Commands

| Command | Description |
|---------|-------------|
| `grep`  | Searches for patterns in text. |
| `awk`   | Processes text line by line. |
| `sed`   | Stream editor for text manipulation. |
| `sort`  | Sorts lines of text. |
| `uniq`  | Removes duplicate lines. |
| `cut`   | Extracts specific columns or fields from text. |
| `tr`    | Translates or deletes characters. |
| `wc`    | Counts lines, words, and characters. |

### Example

```bash
cat file.txt | grep "error" | sort | uniq
```

- `cat file.txt`: Reads the file.
- `grep "error"`: Filters lines containing the word "error".
- `sort`: Sorts the filtered lines.
- `uniq`: Removes duplicate lines.

## 2. Pipes (`|`)

Pipes allow you to send the **output of one command** as **input to another command**. They are represented by the `|` symbol.

### How Pipes Work

- The output of the command on the left of the pipe (`|`) becomes the input for the command on the right.
- Pipes are used to chain commands together to create powerful data-processing pipelines.
-  hyphen `-` :  Represents **standard input** (stdin) or **standard output** (stdout) in commands that expect a file as input or output.

### Example

```bash
ls -l | grep ".txt"
ls -l | grep ".txt" - (hyphen not needed here)
echo -e "line1\nline2" | diff - file.txt
```

- `ls -l`: Lists files in long format.
- `grep ".txt"`: Filters lines containing `.txt`.

## 3. Redirection

Redirection allows you to control where the **input** and **output** of a command go. It is used to send output to files or read input from files.

### Types of Redirection

| Symbol | Description |
|--------|-------------|
| `>`    | Redirects **output** to a file (overwrites the file). |
| `>>`   | Redirects **output** to a file (appends to the file). |
| `<`    | Redirects **input** from a file. |
| `2>`   | Redirects **error output** to a file. |
| `&>`   | Redirects **both output and error** to a file. |

### Examples of Redirection

#### 1. Redirect Output to a File

```bash
ls -l > output.txt
```
#### 2. Append Output to a File

```bash
echo "New line" >> output.txt
```
#### 3. Redirect Input from a File

```bash
sort < input.txt # not needed here ,input redirection (`<`) can be beneficial when a command does not accept a filename as a parameter and only reads from standard input.
```
#### 4. Redirect Error Output

```bash
command_that_fails 2> error.log # Saves error messages to `error.log`.
```

#### 5. Redirect Both Output and Error

```bash
command &> output_and_error.log
```

## Combining Filters, Pipes, and Redirection

You can combine filters, pipes, and redirection to create powerful command-line workflows.

### Example

```bash
cat file.txt | grep "error" | sort | uniq > filtered_output.txt
```