# Lab 4

The following tasks were run using the [lab 7](https://github.com/ThaimanDigital/lab7) repository, which I had previously forked onto my Github account. I had also previously set up keys on my computer to automatically log into my ieng6 and github accounts.

## Step 1: Log into ieng6

The first step is to log into my course-specific ieng6 account, which i did by typing `$ ssh cs15lwi23akp@ieng6.ucsd.edu` into my terminal. Note that I had already generated SSH keys to log into my ieng6 account automatically. 

Keys pressed: `ssh cs15lwi23akp@ieng6.ucsd.edu, <enter>`

![](/images/Step1.png)

## Step 2: Clone your fork of the repository from your Github account

The next step is to clone the lab7 repository onto your computer by using the `git clone` command. I also already had the ssh link copied to my clipboard which allowed me to simply paste the link instead of typing it out. I am also using a mac and use mac commands for copy and paste.

Keys pressed: `git clone, <command> + v, <enter>`

![](/images/Step2.png)

## Step 3: Run the tests, demonstrating that they fail

In order to run the tests, I first have to change the directory into lab7 with `$ cd lab7/`. Instead of typing out lab7, I used tab to autocomplete my command. Then I used `$ javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and `$ java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` to compile and run the JUnit tests. I just copied and pasted these commands from another file, but you can also use the arrowkeys to navigate through past commands.

Keys pressed: `cd l, <tab>, <enter>, <command> + c, <command> + v, <enter>, <command> + c, <command> + v, <enter>, ^x`

![](/images/Step3.png)

## Step 4: Edit the code file to fix the failing test

I used the nano command to enter and edit the file. Because I already knew where the bug is, it simple easy for me to correct the code.

Keys pressed: `nano L, <tab>, .java, <enter>, <down>, <right>, <delete>, 2, ^o, <enter>, ^x`

![](/images/Step4.png)

## Step 5: Run the tests, demonstrating that they now succeed

Then I compiled my corrected code with `$ javac ListExamples.java` and ran the JUnit command I used previously, except this time I used arrow keys to navigate to my past commands.

Keys pressed: `javac L, <tab>, .java, <enter>, <up>, <up>, <enter>`

![](/images/Step5.png)

## Ste 6: Commit and push the resulting change to your Github account

The final step is to add, commit, and push the changes to my repository. First I use the command `$ git add ListExamples.java` to add the corrected file to my commit. Then, I commit my changes using `$ git commmit -m "fixed"`, and push my commit with `$ git push`.

Keys pressed: `git add L, <tab>, .java, <enter>, git commit -m "fixed", <enter>, git push, <enter>`

![](/images/Step6.png)
