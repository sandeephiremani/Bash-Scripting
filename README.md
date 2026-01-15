# 🧑‍💻 Bash-Scripting 
##  ➡️ What is Bash?
Bash stands for Bourne Again SHell.
It is a command-line interpreter (shell) used in Unix/Linux operating systems. Bash allows users to interact with the operating system by typing commands, running programs, managing files, and controlling system processes.

## 🤔 What does Bash do?
**Bash acts as a middle layer between:**
- User → commands you type
- Operating System → kernel that executes tasks

**When you type a command:**

1. Bash reads the command
2.  Interprets it
3. Executes it using system resources
4. Displays the output

## 🗝️ Key features
**Below are the key features of bash**
1. Command Execution – Runs Linux/Unix commands entered by the user
2. Command History – Remembers previously used commands
3. Tab Completion – Automatically completes commands and filenames
4. Variables & Environment Variables – Stores and uses values for programs
5. Input/Output Redirection – Sends output to files or takes input from files
6. Pipes – Connects the output of one command to another
7. Job Control – Manages running processes (foreground/background)
8. Scripting Support – Automates tasks using script files
9. Conditional Statements – Makes decisions using if-else logic
10. Loops – Repeats commands multiple times

## 🤔 What is Bash Scripting?
**Bash scripting** is the process of writing a series of Bash commands in a file to automate tasks.
Instead of typing commands one by one, you write them in a script and execute it.

A Bash script is a **plain text file** with commands that Bash can interpret.

## Why use Bash Scripting?

- Automate repetitive tasks
- System administration
- File and directory management
- Backup and maintenance tasks
- Software installation and configuration

## Basic Structure of a Bash Script 
Create the file `script.sh` using below command:
```bash
vi script.sh
```
Once you created the file add the below mentioned lines

```bash
#!/bin/bash
echo "Hello, World!"
```
**Explanation:**
- #!/bin/bash → Shebang (tells the system to use Bash)
- echo → prints text to the terminal

**To Run the script:**
```bash
chmod +x script.sh
./script.sh
```
**Explanation:**
- chmod +x script.sh → Providing the 777 permission to execute the script
- ./script.sh → Executing the script 

## Bash Variables
In Bash (Linux shell), variables are used to store data (text or numbers) that can be reused in scripts or commands.

Like in the other programming languages , you can variable in Bash Scripting  as well. However, there are no data types.

### Creating a Variable
In Bash, you assign a value without spaces around `=` .
```bash
name="Alice"
age=25
```
### Using a Variable

Use `$` before the variable
```bash
echo $name
echo $age
```
**Output:**
```text
Alice
25
```
### Variable types in bash
Bash does **not require declaring types**. All variables are treated as strings by default

```bash
x=10
y=5
echo $x$y
```
**Output:**
```text
105
```
### Read Input into a variable 
use `read` to take input from the user.

```bash
read -p "Enter your name: " username
echo "Hello, $username"
```

##  🧐 Variable scope
### What is variable scope?
Variable scope defines where a variable can be accessed or used in a script.

In Bash, there are mainly two scopes:
    
1. Global scope
2. Local scope (inside functions)

⚠️ Important: Bash does not have block scope (like if, for, while). Scope is mainly determined by functions.

### What is a Global Variable?

**A global variable is a variable that:**
1. Is declared outside of any function
2. Can be accessed anywhere in the script
3. Can be accessed inside functions unless overridden

Example:
```bash
#!/bin/bash
name="Alice" # Global variable

greet(){
    echo "Hello, $name"
}

echo "$name"
greet
```
In the above example, we created a global variable and assigned a value to it. The same global variable is accessed both inside and outside the function, which demonstrates that the variable is globally accessible.

**Output:**
```text
Alice
Hello, Alice
```
### Global Variables Modified Inside Functions
In Bash, **functions can modify global variables.**
```bash
#!/bin/bash
count=10 #Global variable

increase(){
    count 20 #Modified global variable
}

echo "Before modifying the global variable $count"
increase
echo "After modifying the global variable $count"
```

**Output:**
```text
Before modifying the global variable 10
After modifying the global variable 20
```

### What is Local Variables?
A local variables is a variables that **exists only inside a function/method**.
It is not accessible **outside the function/method.**

### How to Declare Local variable
use the `local` keyword inside a function.
**Example**
```bash
#!/bin/bash

localfunction(){
    local name="Alice"
    echo "Inside function: $name"
}
localfunction 
echo "Outside function : $name"
```

**Output:**
```text
Inside function: Alice
Outside function:
```
**Explanation** 
- `name` exists **Only inside the function** `localfunction`
- Outside the function, `name` is undefined

### What is Environment Variable ?
In Bash, an environment variable is a named value that is stored in the shell’s environment and is available to the shell and any programs (child processes) it starts.

**Key ideas**

- Environment variables are key–value pairs
- They are typically used to configure program behavior
- Child processes inherit environment variables from the parent shell

**Examples of common environment variables**
```bash
PATH=/usr/local/bin:/usr/bin:/bin
HOME=/home/username
USER=username
SHELL=/bin/bash
```
**Creating an environment variable**
```bash
export MY_VAR="hello"
```
- `export` makes the variable an environment variable
- Without `export`, it is only a shell variable

**Using an environment variable**
```bash
echo $MY_VAR
```
**Difference: shell variable vs environment variable**
```bash
MY_VAR=hello        # shell variable (not inherited)
export MY_VAR=hello # environment variable (inherited)
```
**Viewing environment variables**
```bash
env
# or
printenv
```
**Removing an environment variable**

```bash
unset MY_VAR
```

**Why environment variables are useful**

- Configure applications (e.g., `JAVA_HOME`, `DATABASE_URL`)
- Control command behavior (e.g., `PATH`, `LANG`)
- Pass configuration to scripts without hardcoding values

### Special Bash variables
| **Variable**  | **Meaning**                        |
| --------- | --------------------------- |
| `$0`      | Script name                 |
| `$1` `$2` | Script arguments            |
| `$#`      | Number of arguments         |
| `$@`      | All arguments               |
| `$?`      | Exit status of last command |
| `$$`      | Process ID                  |

### 🗝️ Key Comparison between Local Variable, Global Variable and Environment Variable 
| Feature                  | Local Variable       | Global Variable | Environment Variable    |
| ------------------------ | -------------------- | --------------- | ----------------------- |
| Scope                    | Inside function only | Entire script   | Shell + child processes |
| Keyword                  | `local`              | None            | `export`                |
| Available to child shell | ❌ No                 | ❌ No            | ✅ Yes                   |
| Example                  | `local x=5`          | `x=5`           | `export x=5`            |



