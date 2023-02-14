# Week 3 Lab Report

## Command: find

### type ___
This flag filters all files by their type, AKA only looks at one file type as specified  after

Example #1:

`$ find -type f`

![Image1](/find1.png)

This command will find and display all files that are of type file which is why the arguement is "f". This excludes things like directories, pipes, and device files. 


Example #2:

`find -type d`

![Image2](/find2.png)

This command will find and display all directories which is why the arguement is "d". This is useful as it shows all directories that are deeper inside than just the working directory.


### perm ___
This flag will search for any files with the given permission code.

Example #1:

`find -perm 755`

![Image2](/perm1.png)

This command will find and display all the files that have the permission "755" or "rwxr-xr-x" permissions

Example #2:

`find ! -perm 644`

![Image2](/perm2.png)

This command will find and display all the files that do not have the permission of "644" or "-rw-r--r--" permissions.


### exec ___
This flag will execute any command given to it on the files found by find.

Example #1:

`find -name "*.txt" -exec grep -Hi shalom {} \;`

This command will execute the command of `grep` onto the list of files returned by `find` which in this case will return all the sections in which the word `shalom` shows up. The file paths will show because of the `-H` and the `-i` will ignore the case of the pattern and the input files.

![Image2](/exec2.png)

Example #2:

`find -name “*.txt” -exec chmod 777 {} \;`

![Image2](/exec1.png)

This command will find all the files that end in `.txt` and execute the chmod command on them turning their permissions to "777" or "rwxrwxrwx".



### -size ___
This flag will search for any files that corresponds to the given input size.

Example #1:

`find -size +100k`

This command will return and display all the files that have a size of more than 100 kB

![Image2](/size1.png)

Example #2:

![Image2](/size2.png)

`find -size +50k -size -75k`

This command will return and display all the files that have a size of more than 50 kB and less than 75 kB



## Extra

### empty

![Image2](/empty.png)

I always make empty files so it would be nice to find them using this

## Resources:
- https://alvinalexander.com/unix/edu/examples/find.shtml#:~:text=The%20%2Dtype%20f%20option%20here,f%20option%20off%20your%20command. 
- https://linux.die.net/man/1/grep 
- https://man7.org/linux/man-pages/man1/find.1.html 
- https://www.redhat.com/sysadmin/linux-find-command 
- https://www.tecmint.com/35-practical-examples-of-linux-find-command/ 


