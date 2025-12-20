# Windows Filesystem

Windows primarily uses **NTFS (New Technology File System)**, a journaling filesystem built for security, reliability, and access control. It plays a major part in forensic analysis.

## New Technology File System

Some key features for NTFS include:
- Journaling --> Tracks changes to recover in case of crashes
- Permissions (ACLs) + File Ownership --> Access control

NTFS permissions define who can access or modify data. The journaling makes it essential for incident response.

## ADS (Alternative Data Streams)

NTFS allows files to contain data streams that are not visible in normal file listings. Information, credentials, and beyond. They can also hide malicious data that is overlooked during basic file inspection.

## Core Directories

- C:\Windows -- Core operating system files
- C:\Users -- Users profile and users data
- C:\Program Files -- Installed applications
- C:\ProgramData -- Shared application data (Often abused!)

## Environment Variables

Windows uses environmental variables to reference system path. Some include:
- %windir% --> Windows directory
- %userprofile% --> User home directory

As these are references to existing directories, they become handle when needing to work with each. They're heavily used for malware, scripts, and automation.

## Permissions Model

NTFS permissions include:
- Read
- Write 
- Execute
- Modify
- Full Control (!)

These permissions are applied to folders, files, and inherited objects. Misconfigured privileges can cause attackers to do harm on the system.

