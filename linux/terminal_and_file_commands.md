# Terminal & File Commands

The **terminal** is a text-based interface used to directly interact with the operating system. As no GUI is involved, you instead use commands to do a variety of tasks like navigation, running programs, configuring services, etc. 

Many servers do not have some sort of GUI, making text-based communication the only viable way of interaction. This is why scripting, automating, and remote access all rely on the terminal.

To open to terminal in Linux, the short cut is **Ctrl + Alt + T**.

## Essential Navigation Commands

- pwd -- Print Working Directory. Shows your current location in the filesystem. Used consistently to avoid accidentally running commands in the wrong place.

- ls -- List Files. Shows files and folders in the current directory.
    - ls -l adds a detailed view, showing permissions, owner, and size
    - ls -la includes hidden files (starting with .)

- cd -- Change Directory. Move between directories. 
    - cd folder_name

## Command Operators

- & -- Runs a script in the background as you do more terminal work.
    - python3 script.py &

- && -- Run command only if the previous command succeeds.
    - ping -c 2 10.10.10.10 && echo "Ping success!"

- > -- Overwrite File. 
    - echo "Hello" > file.txt

- >> -- Append to File.
    - echo "New Line" >> file.txt

## User Context

- whoami -- Shows current user.

- id -- Desplays UID, GID, and group memberships. Important for understanding permissions.

---

# File & Directory Commans

Linus systems are file-based. Everything from logs to credientials exists as files. This makes understanding how to work with files mandatory for cybersecurity.

- mkdir -- Make Directory. Makes one (or more) folders. Common for labs.
    - mkdir notes recon

- touch -- Creates empty files. 
    - touch test.txt test2.txt
    - touch ennum.sh

-  nano -- Terminal Text Editor. Can edit configs or write small scripts
    - nano file.txt

- cat -- Print File Contents. Can be used for quick inspection of logs.
    - cat file.txt

- less -- Paginate Viewing. Scroll with arrow keys.
    - less access.log

- find -- Search for files across directories. Used for log analysis & incident response.
    - find -name "*.log"
    - find -name test.txt

- grep -- Searches for matching text inside files. Used for threat hunting and credential discovery.
    - grep "10.10.10.10" access.log

- cp -- Copy Files. Common to copy files before risky edits.
    -cp file.txt file_backup.txt

- mv -- Moving & Renaming Files. Same command does both depending on inputs.
    - mv file.txt folder/ ---> Moves to folder
    - mv file.txt rename.txt ---> Moved to same directory with a different name.

- rm -- Remove Files. No recycle bin like Windows; deletion is permanent.
    - rm file.txt

- rmdir -- Remove Empty Directory. File MUST be empty.
    - rmdir empty_folder

- rm -rf -- Remove Directory & Contents. Directories are deleted without confirmation. Misuse can destroy systems. 
    - rm -rf folder_name