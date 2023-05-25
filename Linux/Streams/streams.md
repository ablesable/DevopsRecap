## Standard output/error

- Using > or 1> is standard out for example to the file.
- This can be used as giving infomation from terminal or just copying between files.
- Using >> or 1>> is used for adding to the file.
- Single > is used for replacing of a content on the other hand.
- Redirected streams from console can be formatted differently than in a console (e.g. with ls).
- Even empty outputs can creat new files. That's why in terminal will see error, in spite of empty output put to the new file.
- 2> or 2>> is used for standard errors on the same terms as standard outputs.
- We can use standard output and standard error streams at the same time in a single command.
- For ignoring errors: 2> /dev/null (throwing into oblivion).

## Standard input

- < is used for a standard input.
- Using streams from standard input and standard output/errors in one line of a command is possible (e.g grep "xd" < newfile.txt > grep.txt 2> /dev/null)