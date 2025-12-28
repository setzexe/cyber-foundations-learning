# Filesystem

The Linux filesystem defines how programs and files are organized and accessed on the system. Everything in Linux (files, directories, devices, processes) are treated as a file. 

## Why the Filesystem Matters in Cybersecurity

The filesystem determines where programs live, where configuration is stored, where logs are written, and where attackers hide / persist.

Understanding the layout is required for investigating systems, detecting abuse, and understanding permissions.

## Root of the Filesystem

All files exist under the root directory:

    /

Every path from the system starts from this point.

## Core Directories

### /bin and /sbin

Holds essential system binaries. These hold the core commands required for system operation. 

Replacement or modification of this directory has ALOT of impact.

### /etc

System-wide configuration files. Controls services, users, and behaviors.

Frequent target for misconfiguration and abuse.

### /home

User home directories. Holds user data, SSH keys, and scripts / credentials.

### /var

Variable data (logs, caches, spool files)

This holds log files, indicators of compromise, and service activity.

### /usr

User installed programs & libraries. Third party software is located here.

The attack surface here is **huge.**

### /tmp

Temporary files. Very common abuse location, as these are world-writable.

## Files vs Directories

Files store data and executable code.

Directories organize filers.

Executables are just files with execute permission, like chmod 7.

## Permissions & Ownership

Each file and directory has an owner, a group, and permission bits (read, write, and execute). 

Permissions, like chmod 755, control who can read, write, and execute the file. 

**Misconfigured permissions are a massive security risk.**

## Filesystem & Execution

Programs run from binaries on disk and scripts with execution permissions. 

Attackers must somehow place code on disk or abuse/modify existing files and locations. This makes the filesystem the predessor for persistance.

## Filesystem & Configuration

Linux stores configuration in plain text files. This is a double edged sword. Auditing becomes easier, misconfigurations are more visible, and unauthorized changes are detectable. But this makes it way easier for attackers to abuse if permissions are weak.