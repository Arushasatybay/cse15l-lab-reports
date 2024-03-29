# Lab Report 1
1) ![Image](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-11%20at%202.22.52%20PM.png?raw=true)
   * The working directory when the command was run was `/home/lecture1`.
   * I got no output because the command `cd`  is used to change the current directory to the one provided, and given we gave no argument to `cd` it automatically changed to the user's home directory and started a new prompt. 
   * It is not an error, it is a default behavior. 
     
***
     
 2) ![Image](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-12%20at%204.46.45%20PM.png?raw=true)
   * The working directory when the command was run was `/home`.
   * I got `lecture1` as an output because the `ls` lists the files and folders in the given path. Given, that we did not have an argument (did not specify the path) it showed the list of folders in the current directory, which is `home`.
   * It is not an error, that's how this command operates.
     
***
     
 3) ![Image](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-13%20at%201.50.30%20PM.png?raw=true)\
   * The working directory was `/home/lecture1`.
   * I got a blank answer as an output because the `cat` or `concatenate` command prints the contents of files given by the path(s). Given, that we gave no path it tried to print the contents of `lecture1`. However, `lecture1` is not a file but rather a directory so nothing was printed.
   * It is not a mistake. We used the `cat` command on a directory and this output is expected.
     
***

 4) ![Image](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-13%20at%202.02.52%20PM.png?raw=true)
   * The working directory was `/home`.
   * I got no output because the command `cd` is used to change the current directory `home` to a newly provided `lecture1/messages/`. No output with this command just confirms that the change of directory was successful. And a new prompt `[user@sahara ~/lecture1/messages]$` shows that we are now in the `messages` directory. 
   * It is not an error due to the reasons provided above.
     
***

 5) ![Image](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-13%20at%202.14.26%20PM.png?raw=true)
   * The working directory was `/home/lecture1`.
   * I got `en-us.txt  es-mx.txt  ru.txt  zh-cn.txt` as an output because we used as an argument the directory `messages`, and the command `ls` printed the contents of the `messages` folder. 
   * It is not an error because we used the `messages` folder as a directory, which specifies a path relative to our current directory(`lecture1`). If the path(argument) chosen was not relative to the `lecture1` directory then we would have gotten an error.
     
***
     
  6) ![Image](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-13%20at%202.32.32%20PM.png?raw=true)
   * The working directory was `/home`.
   * I got `cat: lecture1: Is a directory` as an output because the command `cat` is used to print the contents of a file(s), not folders. So by choosing as an argument a directory, it lets us know that the argument we chose is a directory meaning it cannot print any content. 
   * It is considered an error because the `cat` command is again used to print the contents of files, not directories.
     
***

  7) ![Image](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-15%20at%202.41.47%20PM.png?raw=true)
* The working directory was `/home`.
* `bash: cd: lecture1/messages/en-us.txt: Not a directory ` was an output because we provided a path to a file as an argument. The `cd` command is used to change directories and not files so the output is letting us know that it is an error.
* It is an error, as we provided a file path instead of a directory.

***

  8) ![Image](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-15%20at%202.54.21%20PM.png?raw=true)
* The working directory was `/home/lecture1/messages`.
* I got the `en-us.txt` as an output because we put the file name `en-us.txt` as an argument for the `ls` command. The command returns the name of the file if  a file was used as an argument
* It is not an error, it just confirms that in the current directory, such a file exists.
       
***

  9) ![Image](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-15%20at%203.06.32%20PM.png?raw=true)
* The working directory was `/home/lecture1`.
*  `To use this program:
    javac Hello.java
    java Hello messages/en-us.txt` was outputted because the `cat` command is used to read the content of files, so when a file was given as an argument, `cat` printed the contents of the `README` file. 
* It is not an error. 
     
