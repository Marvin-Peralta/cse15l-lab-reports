# **Lab Report 3 **
## By Marvin Peralta, A17271264

##The GREP command

###Variation 1: `grep -i <patter> <file_name>`

The -i add-on ignores whether the string provided has uppercase or lowercase letters - all lines in the file containing the string will be printed out

###Variation 2: `grep -w <pattern> <file_name>`

The -w add-on makes it so that whatever string is being searched for, only searches for the string as a word.
For example: if "is" is searched for, lines containing "this" or "miss" will not qualify to be printed after the command is inputted

###Variation 3: `grep -l <pattern> <file_type or name>`

The -l add-on displays the name of the files that contain the pattern that is searched for

###Variation 4:`grep -o <pattern> <file_name>`

The -o add-on displays only the part of the line in which the pattern is present

Source:

[The Geek Stuff] (https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/)
