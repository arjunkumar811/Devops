# Getting Started with Bash and Terminal

This guide covers essential Bash commands to navigate and manage files in the terminal. These commands are useful for beginners who want to get familiar with the command line.

---

## 1. Navigation Commands

### `pwd` (Print Working Directory)
Displays the current directory you are in.
```bash
pwd
```

### `cd` (Change Directory)
Used to navigate between directories.
```bash
cd directory_name   # Move into a directory
cd ..               # Move one level up
cd /path/to/dir     # Move to a specific directory
cd ~                # Move to the home directory
```

### `ls` (List Directory Contents)
Displays files and directories in the current directory.
```bash
ls                # List files in the current directory
ls -l             # List files with detailed information
ls -a             # Show hidden files
ls -lh            # Show file size
```

---

## 2. File and Directory Management

### `mkdir` (Make Directory)
Creates a new directory.
```bash
mkdir new_directory
```

### `touch` (Create a New File)
Creates a new empty file.
```bash
touch filename.txt
```

### `cat` (Concatenate and Display File Content)
Used to view the content of a file.
```bash
cat filename.txt
```

### `rm` (Remove Files and Directories)
Deletes files or directories.
```bash
rm filename.txt          # Remove a file
rm -r directory_name     # Remove a directory and its contents
```

### `mv` (Move or Rename Files)
Moves or renames files and directories.
```bash
mv old_name.txt new_name.txt    # Rename a file
mv filename.txt /path/to/dir    # Move file to another directory
```

### `cp` (Copy Files and Directories)
Copies files or directories.
```bash
cp file.txt /destination/path   # Copy a file
cp -r directory/ new_location/  # Copy a directory recursively
```

---

## 3. File Editing

### `vi` (Open Vi Editor)
A text editor used in the terminal.
```bash
vi filename.txt  # Open file in vi editor
```
**Basic vi commands:**
- Press `i` to enter **Insert Mode** (for editing text).
- Press `Esc` to return to **Command Mode**.
- Type `:wq` and press Enter to **save and exit**.
- Type `:q!` and press Enter to **exit without saving**.

---

## 4. Node.js and NVM (Node Version Manager)

### `node` (Run JavaScript Files)
Used to run JavaScript in the terminal.
```bash
node
```
To execute a JavaScript file:
```bash
node script.js
```

### `nvm` (Node Version Manager)
Manages multiple versions of Node.js.
```bash
nvm install node        # Install latest Node.js version
nvm install 16.20.0     # Install specific version
nvm use 16.20.0        # Switch to a specific Node.js version
nvm list               # Show installed Node.js versions
```

---

## 5. Miscellaneous Commands

### `echo` (Print Messages)
Displays a message in the terminal.
```bash
echo "Hello, World!"
```

### `clear` (Clear Terminal Screen)
Clears the terminal output.
```bash
clear
```

### `exit` (Close Terminal)
Closes the terminal session.
```bash
exit
```

---

This is a beginner-friendly introduction to basic Bash and terminal commands. Keep practicing to improve your command-line skills!
lets goo....

