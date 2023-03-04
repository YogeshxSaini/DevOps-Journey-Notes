## Navigation

| Command | Description | Syntax |
| ------- | ----------- | ------ |
| `cd`  | Change Directory              | `cd [directory path]`             |
| `ls`  | List contents of directory	| `ls [options] [directory path]`   |
| `pwd` | Print working directory       | `pwd`                             |


## File Management

| Command | Description | Syntax |
| ------- | ----------- | ------ |
| `cp`      | Copy files or directories           | `cp [options] [source] [destination]` |
| `mv`      | Move or rename files or directories | `mv [options] [source] [destination]` |
| `rm`      | Remove files or directories         | `rm [options] [file/directory]`       |
| `mkdir`   | Create a new directory              | `mkdir [options] [directory name]`    |


## System Information

| Command | Description | Syntax |
| ------- | ----------- | ------ |
| `uname`    |	Print system information                     | `uname [options]`        |
| `hostname` | Print or set system hostname	                 | `hostname [options]`     |
| `lscpu`    | Display information about the CPU             | `lscpu [options]`        |
| `free`     | Display amount of free and used system memory | `free [options]`         |
| `df`       | Display free disk space                       | `df [options]`           |

## User Management

| Command | Description | Syntax |
| ------- | ----------- | ------ |
| `sudo`	| Execute a command with superuser privileges   | `sudo [command]`                  |
| `adduser` | Add a user to the system                      | `adduser [username]`              |
| `usermod` | Modify a user account                         | `usermod [options] [username]`    |
| `passwd`  | Change user password                          | `passwd [username]`               |
| `whoami`  | Print current user name                       | `whoami`                          |

## Package Management

| Command | Description | Syntax |
| ------- | ----------- | ------ |
| `apt-get` | Install or remove packages from repositories  | `sudo apt-get [options] [package name(s)]` |
| `dpkg`    | Install, remove or query installed packages   | `sudo dpkg [options] [package name(s)]`    |
| `snap`    | Install or manage snap packages               | `sudo snap [options] [package name(s)]`    |
| `yum`     | Install or remove packages from repositories  | `sudo yum [options] [package name(s)]`     |

## Network Management

| Command | Description | Syntax |
| ------- | ----------- | ------ |
| `ping`        | Test network connectivity                  | `ping [options] [host]`       |
| `ip`          | View or configure network interfaces       | `ip [options] [command]`      |
| `netstat`     | Display network connections and statistics | `netstat [options]`           |
| `ss`          | Display socket statistics                  | `ss [options]`                |
| `traceroute`  | Trace the path to a network host	         | `traceroute [options] [host]` |

## Process Management

| Command | Description | Syntax |
| ------- | ----------- | ------ |
| `ps`	 | Display information about running processes	| `ps [options]`                      |
| `top`	 | Display system resource usage and processes	| `top`                               |
| `kill` | Send a signal to a process to terminate it	| `kill [options] [process ID]`       |
| `pkill`| Send a signal to a process by name	        | `pkill [options] [process name]`    |
| `nice` | Set the priority of a process	            | `nice [options] [command]`          |

## Text Processing

| Command | Description | Syntax |
| ------- | ----------- | ------ |
| `grep` | Search for a pattern in a file or input	    | `grep [options] [pattern] [file(s)]`  |
| `sed`	 | tream editor for filtering and transforming	| `sed [options] [command] [file(s)]`   |
| `awk`	 | Pattern scanning and processing language	    | `awk [options] [script] [file(s)]`    |
| `cut`	 | Extract sections from each line of a file	| `cut [options] [file(s)]`             |
| `sort` | Sort lines of text	                        | `sort [options] [file(s)]`            |

## File Compression

| Command | Description | Syntax |
| ------- | ----------- | ------ |
| `gzip`	| Compress or decompress files using gzip	| `gzip [options] [file(s)]`            |
| `tar`	    | Create or extract tar archives	        | `tar [options] [archive] [file(s)]`   |
| `zip`	    | Create, modify, or extract zip archives	| `zip [options] [archive] [file(s)]`   |
| `unzip`	| Extract files from a zip archive	        | `unzip [options] [archive]`           |