# Processes / Services

A process is a running instance of a program. When an application starts...

- The OS creates a process 
- The process uses memory and CPU
- The process runs under a specific user and privilege level

Everything that runs on Windows runs as a process.

When you boot up your computer, your registry describes what the services or processes should do. Windows then starts these services / processes.

## What a Service Is

A service is a special type of process that is designed to run in the background, start automatically, and provide system / application functionality.

These services usually run without user interaction and start when Windows boots up. They tend to persist even when no one is logged in.

## Process vs Services

All services are processes, but not all processes are services.

Processes are active program execution. If you load up a video game, that is a process. You boot the application and it runs, taking up some memory and CPU power. 

Services are long-running background processes. This includes things like the DNS Client, the RPC Endpoint Mapper, etc. You usually don't touch these, they just help the system operate.

## Why Processes Matter in Cybersecurity

Processes determine who is running code, what code is running, and what resources it can access.

Attackers can make malicious processes that they inject into legitimate ones. They can also abuse trusted processes.

Defenders monitor running processes, detect abnormal behavior, and correlate activity with users.

## Why Services Matter in Cybersecurity

Services are a persistence mechanism due to them booting up and running on their own.

Attackers abuse services to maintain long-term access, run malware at startup, and hide activity in background processes. As it is not a main process that you can easily get to in the task bar, this becomes abusable.

Poorly configured services can run with high privileges, exposing attack surfaces and potential privilege escalation.

## Privileges & Context

Each process or service runs as a specific user with a specific privilege level. Security failures often occur when services run with excessive permissions.

## Processes, Services, Networking

Network services:

- Listen on ports
- Are backed by processes
- Accept externl traffic (!)

An open port usually maps to:

- A listening service
- A running process (Multiplayer game for example)

## Visibility & Monitoring

Processes and services can be listed, monitored, and logged. Security tools rely on process creation events, service changes, and execution patterns. Unexpected processes / services are often a red flag.


