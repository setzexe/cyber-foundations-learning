# Packages

A package is a bundled piece of software that includes:

- program binaries
- libraries
- configuration files
- metadata about dependencies

Packages are how most software is installed on Linux.

## What a Package Manager Does

A package manager is responsible for installing, updating, and removing software as well as resolving dependencies. One's that may be familiar include *apt* for Ubuntu and *pacman* for Arch.

## Dependencies 

Most packages rely on other packages, meaning they are dependant. This creates dependency chains, shared libraries, and trust relationships. If one dependency is vulnerable, multiple programs may be affected.

## Repositories 

Packages are downloaded from repositories. Repositories host signed packages and define trusted software services.

Security depends on repository integrity, signature verification, and update practicies. If a repository is compromised, they can distribute malicious software at a large scale.

## Updates & Patching

Package managers are used to apply security patches, fix vulnerabilitis, and update dependencies. Unpatch systems are common targets in cybersecurity. It is a core defensive prctice to update packages frequently.

## Packages & Persistence 

Installed packages will survive reboots, integrate with system services, and may affect startup behavior. This makes packages a persistence vector.

Attackers may install malicious packages that replace legitimate ones, while also abusing package scripts. This would lead to behavior that lasts through reboots and wouldn't be very noticible unless you learned that that package was tinkered with.

## Packages vs Filesystems

The filesystem is where software lives.

Packages is how software gets there.

Packages places files into places like /bin, /usr, /etc, and /var.

## Packages Cybersecurity Importance 

Packages control what software exists on a system, which versions are installed, and which code is trusted to run. Each installed package is part of the attack surface.