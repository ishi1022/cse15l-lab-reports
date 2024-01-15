![Image](https://github.com/ishi1022/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-14%20at%208.26.25%20PM.png?raw=true)
cd
1. No Arguments
- The current working directory for the cd command with no arguments is lecture1
- When running the cd command with no arguments the directory changes from the working directory (lecture1) to the home diretory
- There is no error with this command, the directory is successfully changed
2. Directory as argument
- The current working directory is the home directory
- When running the cd command with directory2 as an argument it changes the directory from home to directory2
- There is no error, the directory is successfully changed
3. File as argument
- The current working directory is the directory2
- When running the cd command with a file (hindi.txt) as an argument it does not work as it is trying to change the current directory to a file which is not allowed with this command.
- This prodcues the Not a directory error becasue this command cannot accept files as arguments

![Image](https://github.com/ishi1022/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-15%20at%2012.32.28%20PM.png?raw=true)
ls
1. No arguments
- The current working direcotry is the home directory
- When running the ls command it lists all the contents of the home directory which are two directories: "lecture1" and "directory2"
- The output is not an error as the command listed everything in the diretory which is correct
2. Directory as argument
- The current wokring direcotry is the home directory
- When running the ls command with "directory2" as an argument which is a directory, it lists all the contents of that directory
- The output is not an error as the command listed everything in the diretory
3. File as argument
- The current working directory is the home directory
- When running the ls command on a file it tries to list the contents of the file but that is not allowed
- This command produces an error "No such file or directory" as in the home directory that file is not present and the ls command cannot list the contents of a file

![Image](https://github.com/ishi1022/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-15%20at%2012.33.55%20PM.png?raw=true)
cat
1. No Arguments
- The current working direcotry is lecture1
- When running this command with no arguments it tries to concatenate the contents but there is nothing to concatenate
- There is no error but there is no output as no file is specified
2. Directory as argument
- The current working directory is lecture1 
- When running this command with a directory as an argument it tries to concatenate the contents of the directory but that is not allowed
- The error is "Is a directory" which is the output because this command requires a file to concatenate
3. File as argument
- The current working direcotry is the messages direcotry which is inside the lecture1 directory
- When running this command with a file as an argument we can see the contents of the "hindi.txt" file
- There is no error, the output is the contents of the hindi.txt file

