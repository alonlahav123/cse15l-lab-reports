# Week 2 Lab Report

## Part 1
Code for the StringServer:
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String str = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("String: %s", str);
        } else if (url.getPath().equals("/add-message")) {
            System.out.println("Path: " + url.getPath());
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                str += parameters[1];
                str += "\n";
                return String.format(str);
            }
        } else {
            return "404 Not Found!";
        }
        return String.format("404 Not Found!");
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
![Image1](/cse15l-lab3-screenshot1.png)
Methods called:
 - I went to the following URI: http://localhost:4000/add-message?s=Hello
 - When I access this specific URL it calls the Handler class which called the handleRequest method
 - The handleRequest method takes in the URL and is able to extract information from it

Relevant Arguments:
 - The relevant arguements for this is the "/add-message?s=Hello"
 - My code is able to take that arguement and understand that I want to add a message to my overall string as the path is "/add-message"
 - Then we see the query which is "?s=Hello" which my code separates into two arguments by dividing it around the "="
 - Then we know that what follows the "s=" will be the string that I want to add therefore I add "Hello" to my global string
 - Finally I concatinate "\n" to add a new line so that any future additional messages will appear on a new line
 - In total the only field changed is the `str` variable as the inputted string gets added as well as the URI

![Image2](/cse15l-lab3-screenshot2.png)
Methods called:
 - I went to the following URI: [http://localhost:4000/add-message?s=How are you](http://localhost:4000/add-message?s=How%20are%20you)
 - Similar to the above example, this URL calls the Handler class which called the handleRequest method
 - The handleRequest method takes in the URL and is able to extract information from it

Relevant Arguments:
 - The relevant arguements for this is the "/add-message?s=How are you"
 - My code is able to take that arguement and understand that I want to add a message to my overall string as the path is "/add-message"
 - Then we see the query which is "?s=How are you" which my code separates into two arguments by dividing it around the "="
 - Then we know that what follows the "s=" will be the string that I want to add therefore I add "How are you" to my global string
 - Finally I concatinate "\n" to add a new line so that any future additional messages will appear on a new line
 - In total the only field changed is the `str` variable as the inputted string gets added as well as the URI

---
---
# Week 1 Lab Report
### How to remotely access my account
--- 
## Step 0: Download VS Code
If you haven't already, make sure you download VS Code
 - download VS Code using this [link](https://code.visualstudio.com/)
![Image](/vscode-download-screenshot.png)
 - click on download button

## Step 1: Open VS Code
![Image](/VSCode-Screenshot.png)
 - once you have this you can continue to the next step 

## Step 2: Open The Terminal
![Image](/terminal.png)
 - Once VS Code is open press Ctrl + ` to open the terminal
 - once completed you will see a $ where you can write in inputs

## Step 3: SSH Into Account
![Image](/remote-access.png)
 - to remotely connect to your account write the following into the terminal:
```
$ ssh cs15lwi23zz@ieng6.ucsd.edu
```
 - replace the "zz" after "cs15lwi23" with your user id
 - side note: when typing your password you will not see any characters being written on the screen which is fine! Proceed as normal
 - once logged in you will see the same thing as shown in the above image
 - you will now have access to the remote account and you will be shown your home directory (signified by the ~)

P.S. my user is "ats"

#### Forget username? 
 - go to this [link](https://sdacs.ucsd.edu/~icc/index.php)
 - input last name and student ID into section titled "Forgot Username or New Student?"

#### Forget password?
 - to reset password follow the step by step instructions at this [link](https://docs.google.com/document/d/1hs7CyQeh-MdUfM9uv99i8tqfneos6Y8bDU0uhn1wqho/edit)

## Step 4: Bash Commands
![Image](bash-try.png)
 - once inside try some bash commands
 - try `ls` (list)
     - this command will list all the files and directories in the current directory you are looking at
     - you can also input a directory location after the command to list the files in that specific directory
     - to see the files in a parent directory try `ls ..`
     - to see the files in a child directory try `ls /[child directory name]`
 - try `pwd` (print working directory)
     - this command will pring the current directory you are in
     - very helpful in a new computer or when you need a reminder of where you are
 - try `cd ___` (change directory)
     - this command will change the directory you are in
     - you can use `cd [child directory name]` to change to a directory that is a child of your current working directory
     - you can input multiple child directories at once concatinated by `/` instead of cd'ing multiple times
     - you can use `cd [absolute path]` to change any directory
     - you can use `cd ~` to go to home directory
 - try `ls / -Ral`
     - lists all files in long format, this works recursively from root to all chilren
     - this will start listing a lot of files, you will probably want to stop this from running by doing the following
 - press Ctrl + c to stop the printing
 - try `clear` to clear the command line
 - try `exit` to exit the remote access

I learned a lot from running these commands, specifically on how to go about navigating my computer's file system through a text based application rather than the normal graphical user interface. I also learned that a lot of these commands have inputs as well as flags that alter their normal function to make my life easier as a programmer. I was specifically interested in `ls -l` which I later learned that it shows the permissions of different users and what each type of user can do to each file.
