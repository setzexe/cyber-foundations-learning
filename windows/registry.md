# Registry

The Registry is the system on windows that stores system configuration, user settings, and application data.  Rather than storing programs, it tells programs what to do, who can do what, what should start automatically, and what settings / values exist. As the filesystem stores actual data and is user-facing, the registry stores instructions and is more system-based, making malware harder to notice.

## Registry Structure

### Hives
Hives are the root sections of the Registry. They define who the settings apply too. You'll encounter two important hives often:
- HKLM (HKEY_LOCAL_MACHINE) --> These are rules that apply to the entire computer regardless of whos using it. Services, software settings, etc. If malware writes here, it affects *every* user.

- HKCU (HKEY_CURRENT_USER) --> Rules that apply to the current user only. Desktop settings, user startup programs, etc. 

### Keys 
Keys are like folders that store related settings. You might have a Software key that stores settings for both Microsoft and Windows. 

### Values

Values are like variables inside the folder. They are given a name, a data type, and a value.
- EnableFeature = 1

If the switch is set to 1, turn something on.

## Regedit 

Regedit is a viewer/editor of the registry database. Attackers *love* this, as it isn't safe at all. There is no undo and even a minor mistake can destroy a windows system. Blue team/forensics often involves checking is registry information / edits.

## Importance of the Registry
The registry is vital because it controls multiple essential roles like what runs at startup, how programs launch, security / driver behavior, etc.

**Windows does not automatically understand how to do these tasks, so it reads the "instructions" from the Registry.**

In a cybersecurity context, if malware is injected into the Registry that affects how a system works (startup, local machine, etc), the system will just do that. This is *persistence*; the machine does harmful tasks despite rebots or shutdowns. This makes it a VERY common attack medium. 

