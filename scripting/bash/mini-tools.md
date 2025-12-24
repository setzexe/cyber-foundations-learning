# Mini Tools

This module contains small and practical bash tools that mirror real cybersecurity workflows. You will utilize concepts you see here in the future. 

## Argument Validator

Every serious script needs safe input handling, knowing if a input was even given or not

#!/bin/bash

if [ -z "$1" ]; then

--> echo "Usage: $0 <target>"

--> exit 1

fi

TARGET=$1

echo "Target is $TARGET."

If there is no user input, echo states how to use the script and exits. Otherwise, the target is specified.

**This is a VERY commonly implemented bit of script.**

## Ping Sweep (Network Reachability)

This is part of recon. This pings various networks to check if they are up.

#!/bin/bash

for ip in {1..10}; do

--> ping -c 1 192.168.1.$ip > /dev/null 2>&1

--> if [ $? -eq 0 ]; then

----> echo "192.168.1.$ip is reachable"

--> fi

done

## File existence + Line-By-Line Enumeration Tool

This ensures a file exists before you continue with a script. No proper file = potential bad input from the script.

#!/bin/bash

if [ ! -f "$1" ]; then

--> echo "Not a proper file!"

--> exit 1

fi

while read line; do

--> echo "Processing line: $line"

done < "$1"

## Mode-Based Tool (with Case)

Let's say you have a general-purpose tool and you wanna do more beyond just one task.

#!/bin/bash

case "$1" in

--> scan) echo "Starting scan..." ;;

--> enum) echo "Starting enum..." ;;

--> clean) echo "Starting clean..." ;;

--> *) echo "Usage: $0 {enum|clean|scan}" ;;

esac




