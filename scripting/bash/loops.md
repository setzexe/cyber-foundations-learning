# Bash Loops

Loops allow scripts to repeat actions automatically. This becomes essential for enumeration (examining a target for information), scanning, and automation. It gives the ability  to automatically examine and scale across files, users, ports, etc.

## for Loops

These repeat commands over a list of items.

### Loop Through Words

for word in one two three; do

--> echo "$word"

done

"# Don't use --> during actual scripting. That is meant to show a tab. Markdowns just format actual tabs weirdly"

### Loop Through Files

for file in *.txt; do # *.txt = All txt files

--> echo "Found file: $file"

done

This is common in cybersecurity for scanning files, logs, wordlists, etc.

### Port Enumeration

for port in 22 80 443; do

--> echo "Checking port $port"
--> # do thing with port

done

## While Loops

A while loop runs as long as a condition is true.

### Counting Loop

count=1

while [ $count -le 5 ]; do # runs while count is less than 5

--> echo "Count: $count"

--> ((count++)) # (()) is used for arithmetic commands.

done

### Read File Line by Line

while read line; do

--> echo "Line: $line"

done < users.txt 

"# doing < file.txt redirects input to that file."

## Until Loops

An until loop runs until a condition becomes true.

### Loop until count condition

count=1

until [ $count -eq 5 ]; do

--> echo "Count: $count"

--> ((count++))

done

## Loop Control

Control how loops behaves.

### Break 

Stops the loop immediately.

for i in 1 2 3; do

--> echo "$i"

--> break

done

"# Breaks out after echoing 1."

### Continue

Skips the current iteration.

for i in 1 2 3; do

--> continue

--> echo "$i"

done

"# No output. Continue goes to the next iteration before echo."
