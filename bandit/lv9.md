# Level 9

## Description

The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

## Attemps log

`cat data.txt | grep -a "="`
- Got the output but not precise.

## Solution

`strings data.txt | grep "="`
- `grep` on binary file doesn't work well even with `-a` flag.
- Using `strings` is more appropriate.
