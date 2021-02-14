# LSOF

Command meaning 'List open files'. Used to report a list of all open files and the processes that openend them.

Github: [https://github.com/lsof-org/lsof](https://github.com/lsof-org/lsof)  
Wikipedia: [https://en.wikipedia.org/wiki/Lsof](https://en.wikipedia.org/wiki/Lsof)  

## Commands

### Help?
`lsof -h`

### List IP sockets
`lsof -i`

`lsof -i:8080`

### List files for given PID
Lists all open files attached to given PID (Process Identifier, process, ID).  
The PID uniquely identify's an active process.

`lsof -p 1083`

### List PID of open files
Lists all unique PID of the open files.  
`-t` stands for terse listing or a brief listing.

`lsof -t`

This can be combined with other commands.  
E.g. `lsof -t -i`

Return the PID of the process running on port 8080.  
E.g. `lsof -t -i:8080`

## Usage examples

## Kill process running on a port

Combining some of the above lsof commands to retrieve the PID of a running process on a specific port. 
Allows to retrieve the PID an kill it:  
`sudo kill -9 $(sudo lsof -t -i:8080)`

Source: [https://tecadmin.net/kill-process-on-specific-port/](https://tecadmin.net/kill-process-on-specific-port/)