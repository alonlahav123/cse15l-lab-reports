# Lab 4

In lab 4 we had a competition for who can do steps 4-9 the quickest, below are the listed steps:

1) Setup: Delete any existing forks of the repository you have on your account
2) Setup: Fork the [repository](https://github.com/ucsd-cse15l-w23/lab7)
3) The real deal: Start the timer!
4) Log into ieng6
5) Clone your fork of the repository from your Github account
6) Run the tests, demonstrating that they fail
7) Edit the code file to fix the failing test
8) Run the tests, demonstrating that they now succeed
9) Commit and push the resulting change to your Github account (you can pick any commit message!)

We were told that after some practice the TA's were able to complete the challege in under 5 minutes which became my goal. 

My first attempt took a little over 11 minutes but by the end I was able to complete the challenge in under 30 seconds which made me my group's champion.

My strategy comprised on creating a text document containing all the commands I needed to run and opening it side by side with my terminal copy and pasting the commands I wanted to run. This was the text document:

![textDocumentOfCommands]()

This is how I setup my windows for the competition:

![windowSetup]()

Assuming I already completed the setup I start from step 4 do the following:

First I started by copying the ssh command from the text file and pasting it into my terminal as so:

![sshcommand]()

Next I combine steps 5 through 7 as they can run independently from each other. I copy the following four lines and paste them into my terminal: 

```
git clone git@github.com:alonlahav123/lab7.git

cd lab7/

javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java

java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

nano ListExamples.java 
```

This code 




ssh cs15lwi23ats@ieng6.ucsd.edu

git clone git@github.com:alonlahav123/lab7.git

cd lab7/

javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java

java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

nano ListExamples.java 

javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java

java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

git commit -m 'l'

git push
