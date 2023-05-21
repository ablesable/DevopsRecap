- Using a command line is a programming line by line. That way is possible by REPL (Read Evauluate Print Loop)  programming environment inside the CLI.
- Node or Python can be run as REPL as well (e.g. Python prompt).
  
## CLI and basic file system

- Emulator can run a lot of shells. WSL is running Linux and Linux built in emulator is running Bash (the shell).
- Root directory is represented just as slash / 
- A bash command is a program in a terms of REPL env.
- -- help at the end of any bash command will help you what you can do with a command. 
- /home directory have different directories for different users. 
- using names of dictionaries with cd commands without slashes means we're using relative paths.
- Echo command works different for every different shell (e.g. string needs to be put in a quote)
- Argument is a textual information we're passing into the program. 
- -- is a thing called a Flag. Running command with a flag means running a programm in a specific mode!
- -a flag on ls command shows even hidden directories.
- . (dot) in front of a file means it's a hidden file. Just like .gitignore  
- short flag (-) in comparsion with long flag (--) means we want to pass a few flags at once
- Using a short flag - with full flag name that we use with -- is a mistake, shell will understand e.g. -help command as passing -h -e -l -p
- FLAGS ARE ADJUSTED TO PROGRAMS, NOT THE SHELLS! (In some cases order of a flags matters, in some doesn't)
- BEST TO GIVE FLAGS FIRST AFTER COMMAND :)
- FLAGS ARE CASE SENSITIVE!
- Arrow keys are used for history of previous commands
- JUST BE AWARE THAT BY BASH HISTORY someone can see your password! It's good to modify history in that case.
- Clicking ctrl + R a few times will search previous usage of a specific pattern we're looking for.
- Bash history is not updated every single time we're type something into the command line. It cashes last season and then save it into .bash_history file.
- Bang Bang can be typed into another command (!!)