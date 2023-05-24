## Less and More programs
- less is a program to read files only, newer version of More.
- q key (quitting).
- Less is a program installed by default.

## Man
- This is manual for all sort of programs.
- man uses less, so if you know "less" the more you know :)
- --help/-h is a shorter version of manual. Not the same thing!

## Cat
- This program shows everything in the file.
- Can be used in STDOUT!
- ConCATening to the standard out.

## Tail & Head
- Shows last 10 lines in Tail, and first 10 lines in Head.
- Very good for logs. 
- tail -n 3 (shows only last 3 lines).
- tail -f (for realtime showing) This is good option when we want to focus what is being saved to the file.

## Mkdir
- mkdir -p (Creating a lot of folders e.g hi/my/name/is/bartosz)

## Touch
- touch creates a file
- Also modifies modify time.
- touch file{1, 2, 3, 4} will create file1, file2, file3 and so on.
- curly brackets is a way to repeat something in touch. (expansion)
-  

## rm
- Just removes files.
- RM can remove entire comupter!
- rm -r (recursive deleting for inside directories)
- rm -f (forcing to remove), important becasue will not ask to permission to delete something
- rm -rf / (DEATH SENTENCE)

## cp 
- cp first_file.extension destination_file.extension (copying content from one file to another)
- cp -R (recursive copying e.g. dictionaries)

## mv 

TO DO

## tar 
- tar is packing a lot of things together, just like zip file.
- tar -cf archive.tar first_file.ext directory (archive.tar will be a new file with first_file.ext and directory).
- -cf flag stands for one single file and packing.
- -z flag will compress whole package, but we have to remember to add .gz to the end of a file.
- -xzf archive.tar.gz -C destination (uncompress archive to destination directory).
- -x flag (unpack), -z(because it's compressed file) -f (cause it's single archive) -C (for destination).
- So -z flag is a opposite of a -x flag, but -xzf means we want to uncompress (x) a compressed (z) file. 

## Wildcards
- ls name-of-a-file* will find a lot of files with the name that starts like that.
- Astrik will basically find a pattern that match the first part of a name in a file.
- ? mark will find a pattern with one missing piece in a name of a file (e.g. ls name-??-a-file will find for example name-of-a-file file). As we see we can use a few question marks in looking for specific pattern.
- touch name{1..30} will make 30 files. I think it's the self explanatory.
- echo {0..100..10} will echo numbers from 0 to 100 with 10 mark step. It works as well with letters, like {A..z..10}.
- {mark1..mark2}{mark3..mark4} will make permutation of all marks.

-<b> We can make a file by a touch program with question mark (?) but we need to use \ backslash. (Escape character known from programming) </b>
- e.g. touch file-with-question-mark\\?.ext
