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
- -cf flag stands for one single file and compress.
- -z flag will compress whole package, but we have to remember to add .gz to the end of a file.
- -xzf archive.tar.gz - C destination (unpack archive to destination directory).
- -x flag (unpack), -z(because it's compressed file) -f (cause it's single archive) -C (for destination).
- 