# Pipes
- Used for adding one program to another.
- Very common practice is using pipe to add a result of ps command to grep for specific selection of the processes.
- e.g. `$ ps aux | grep "ps aux"` (this will show two running processes excluded)
- Used ps for processes can return a really long list of them, so for killing one of them by using pipes and grep command is important and helpful.
- Another great example for using pipes: rm -i is a command for remove files and a flag for asking if we are sure about that:
 `$ yes y | rm -i file*`
- Previously mentioned in files notes: pipes doesn't work with echo cause echo doesn't read from standard input!