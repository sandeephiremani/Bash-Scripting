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

