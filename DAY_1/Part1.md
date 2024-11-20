# Linux Commands Reference Guide

A comprehensive guide to common Linux commands, including date operations, file management, archiving, and system information retrieval.

## Table of Contents
- [Date and System Information Commands](#date-and-system-information-commands)
- [File and Directory Operations](#file-and-directory-operations)
- [File Archiving and Compression](#file-archiving-and-compression)
- [File Content Management](#file-content-management)

## Date and System Information Commands

### Date Commands
```bash
date                     # Shows current date and time
date "+%d"              # Shows day of month (01-31)
date "+%d-%m"           # Shows day-month
date "+%d-%b"           # Shows day-abbreviated month name
date "+%d-%b-%Y"        # Shows day-month-full year (e.g., 20-Nov-2024)
date "+%d-%b-%y"        # Shows day-month-short year (e.g., 20-Nov-24)
date "+%d-%b-%y:%H"     # Adds hour in 24-hour format
date "+%d-%b-%y:%H:%M"  # Adds minutes
date "+%d-%b-%y:%H:%M:%s"  # Adds seconds
man date                # Shows date command manual
date --help            # Shows date command help
```

### System Information Commands
```bash
hostnamectl            # Displays system hostname and related information
cat /etc/os-release    # Shows Linux distribution information
uname -r               # Displays kernel version
echo $USER             # Shows current username
echo $UID             # Shows user ID number
echo $SHELL           # Shows current shell path
echo $0               # Shows current shell name
```

## File and Directory Operations

### Directory Creation and Navigation
```bash
mkdir /vadapav         # Creates directory named 'vadapav'
cd /vadapav/          # Changes to vadapav directory
```

### File Creation and Management
```bash
touch 1.txt           # Creates empty file or updates timestamp
touch {1..10}.txt     # Creates files 1.txt through 10.txt
touch {1..100}.txt    # Creates files 1.txt through 100.txt
touch {1..100000}.txt # Creates files 1.txt through 100000.txt

# File Removal with Wildcards
rm ?.txt              # Removes single-digit named files
rm ??.txt             # Removes two-digit named files
rm ???.txt            # Removes three-digit named files
rm ????.txt           # Removes four-digit named files
rm ?????.txt          # Removes five-digit named files
```

### Creating Files with Specific Sizes
```bash
dd if=/dev/zero of=1.txt bs=1M count=1    # Creates 1MB file
dd if=/dev/zero of=1.txt bs=1M count=1000 # Creates 1GB file
```

## File Archiving and Compression

### Creating Archives
```bash
tar -cvf samosa.tar 1.txt 2.txt 3.txt  # Creates tar archive
gzip samosa.tar                        # Compresses with gzip
bzip2 samosa.tar.gz                    # Further compresses with bzip2
```

### Extracting Archives
```bash
bunzip2 samosa.tar.gz.bz2              # Decompresses bzip2
gunzip samosa.tar.gz                   # Decompresses gzip
tar -xvf samosa.tar                    # Extracts tar archive
```

## File Content Management

### Redirection Operations
```bash
> index.html           # Creates empty file or truncates existing file
>> index.php           # Creates empty file or appends to existing file
echo 123 > index.html  # Writes "123" to file (overwrites)
echo "text" >> index.html # Appends text to file
cat index.html         # Displays file contents
```

### File Size Management
```bash
dd if=/dev/zero of=1.txt bs=1M count=1 # Creates 1MB file
> 1.txt                                # Truncates file to zero bytes
```

## Important Notes
1. The `>` operator overwrites file content
2. The `>>` operator appends to file content
3. `dd` is useful for creating files of specific sizes
4. File wildcards (?, *) are powerful for batch operations
5. Always be careful with `rm` commands as they permanently delete files
6. Archive commands typically use these extensions:
   - `.tar` for tar archives
   - `.gz` for gzip compression
   - `.bz2` for bzip2 compression

