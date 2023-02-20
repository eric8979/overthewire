# Level 6

## Description

The password for the next level is stored somewhere on the server and has all of the following properties:

    owned by user bandit7
    owned by group bandit6
    33 bytes in size


## Attemps Log

`cd /home/bandit7`

`su bandit7`
- Authentication failure

`du -ab | grep "33"`
- Got matches but permission denied

## Solution

`find / -group bandit6 -user bandit7`
- Outputs a single available path and numerous `permission denied`
- The path contains the pwd.
