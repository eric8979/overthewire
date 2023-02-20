# Level 5

## Description

The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable

## Attempts log

`cd inhere`

`du -b ./*/* | grep "1033"`
- no output

`file ./*/* | grep "ASCII"`

`find ./*/* -type f ! -executable`
- files with "file2" in the title were non-executables.

`ls -l ./*/* | grep "file2" | grep "1033"`
- no output

`file ./maybehere*/*file2* | grep "ASCII"`

## Solution

`du -ab | grep "1033"`
- OUTPUT... `1033    ./maybehere07/.file2`
- `du -b` doesn't check hidden files...

`ls -l ./maybehere07/.file2`
- `-rw-r-----`
`file ./maybehere07/.file2`
- `~~ ASCII text, ~~`
