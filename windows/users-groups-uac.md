# Users, Groups, and UACs (User Account Control)

Windows enforces security through user accounts, group membership, and privilege control. These mechanisms determine who can do what on a system and are central to both attack paths and defenses.

## Users

Windows accounts fall into two main categores: the **Standard User** and the **Administrator**. Admins have full system control, standard users have limited permissions. Each user has a profile stored under the user directory:
- C:\Users\<username>

Most attacks in cybersecurity start from standard users. Once these users gain admin permissions, the entire system is compromised. 

## Groups
Groups are collections of users that share permissions. Admins will be grouped, users will be grouped, sometimes you'll have remote desktop users too. Users can belong to multiple group, where they inherit all associated privileges. Group membership is what defines access, not just account name. You could have a user named *REAL_LOCAL_ADMIN* and if it is not in the administrator group, then it is not going to have admin perms.

## UAC (User Account Control)

User Account Control is a security mechanism that limits automatic admin actions. If you ever downloaded an app, tried to execute it, and got a "proceed?" message, that was UAC's doing. This helps prevent possible bad system modification. 

UAC behavior affects registry and system access. Many attacks will attempt to bypass this system.

## Privilege Seperation

Windows seperates user-level actions and system-level actions. They are not usually on the same tier. Some admins might have this utilized. Like an admin account for a tech-company. It might limit system-level actions for the sake of the company.

**Privilege escalation is a primary attack goal. Most persistence requires this.** The more privileges gained, the more potential harm can be done.
