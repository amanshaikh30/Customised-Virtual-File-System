# Customised Virtual File System (CVFS)

A Customised Virtual File System (CVFS) implementation in C that provides a basic structure and functionality to manage files in a virtual environment. This project demonstrates fundamental concepts of file systems, including inode management, file operations, and user interaction via a shell-like interface.

## Features

- **File Management**: Create, open, close, read, write, and delete files.
- **File Metadata**: Display detailed file information using `stat` and `fstat`.
- **Virtual File System Operations**: Simulate file system operations like `ls`, `truncate`, and `lseek`.
- **Command-Line Interface**: Interactive shell to execute file system commands.
- **Custom Superblock and Inode Structure**: Efficient resource management.

## Project Structure

The main implementation resides in the `CVFS.cpp` file, which contains:
- Superblock and inode management
- File operations (`create`, `read`, `write`, etc.)
- Command-line interaction for file system operations
- Helper functions like `man` and `displayHelp`

## Getting Started

### Prerequisites

- A C++ compiler (e.g., GCC, Clang)
- A Unix-like terminal or equivalent shell environment (Windows Command Prompt or PowerShell can also work with adjustments).

### Compilation

To compile the project:
```bash
g++ CVFS.cpp -o CVFS
```

After compilation, execute the binary:
```bash
./CVFS
```

### Commands Overview

- `ls`: List all files in the system.
- `create <filename> <permission>`: Create a new file with specified permissions.
- `open <filename> <mode>`: Open an existing file with the specified mode.
- `close <filename>`: Close an opened file.
- `read <filename> <bytes>`: Read data from a file.
- `write <filename>`: Write data into a file.
- `stat <filename>`: Display file metadata.
- `truncate <filename>`: Remove all data from a file.
- `rm <filename>`: Delete a file.
- `exit`: Terminate the program.

For detailed command usage, use:
```bash
man <command>
```

## Example Usage

```bash
Customised VFS => create example.txt 3
File successfully created with file descriptor: 0

Customised VFS => write example.txt
Enter the data:
Hello, CVFS!

Customised VFS => read example.txt 12
Hello, CVFS!

Customised VFS => stat example.txt
File name: example.txt
Inode Number: 1
File size: 2048
Actual File Size: 12
...
```

## Technical Details

- **Superblock**: Tracks total and free inodes.
- **Inodes**: Represent individual files, including metadata like size, type, and permissions.
- **UFDT**: User File Descriptor Table for managing file descriptors.

## Contribution

Contributions are welcome! Feel free to fork the repository, make improvements, and submit a pull request.

