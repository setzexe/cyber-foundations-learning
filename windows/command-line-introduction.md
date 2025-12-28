# Windows Command Line Introduction

The Windows Command Line allows **direct interaction** with the operating system. You utilize text commands instead of the typical graphical interface. It provides:

- Visibility into the state of the system
- Control over files and processes
- Automation of actions

Many security tasks rely on the command line.

## Command Line Importance in Cybersecurity

Attackers & Defender both use the command line. It:

- Exposes system internals
- Bypasses GUI limitations & is often usable even if GUI isn't
- Allows fast inspection and control

If you understand the command line, you find it a lot easier to understand how the system as a whole operates.

## Command Line vs GUI

The GUI shows what Microsoft wants users to see. It's very user friendly.
The command line shows what the system is actually doing since you are actually working with the system itself directly. 

Security favors clarity, percision, and repeatability. The command line allows for all three.

## Common Command Line Interfaces

- Command Prompt (cmd.exe) - basic system interaction.
- PowerShell - advanced scripting & automation. 

**Command Prompt is the legacy version of PowerShell. The upcoming markdowns will focus on PowerShell.**

## Basic Scope of Command Line Capabilities

### File and Directory Interaction

The command line allows you to navigate directories. list files, create and delete files, and inspect paths. Much like what you would see in a Linux terminal.

This is crucial for malware analysis, persistence detection and configuration discovery.

### System Informtion

Commands can reveal OS version, system configuration, and environment details. This information is often used during recon, incident response, or just casual troubleshooting.

### Program Execution

The command line can start/stop programs and run system utilities. Most malware/admin tools rely on this ability in the command line.

### Permissions & Context

Commands run as a specific user with specific privileges. Security depends on who runs the command and what permissions they have. Privilege misuse / escalation is a common attack vector. Access to admin privileges goes a long way.

## Command Line and Security Visibility

Many security-relevant actions do not show obvious GUI indicators, and often occur silently via command execution. Hence why you won't see the general public knowing much about it. Logs are often what records command-line activity. 

Understanding commands help interpret logs, detect suspicious behavior, and recognize misuse.


