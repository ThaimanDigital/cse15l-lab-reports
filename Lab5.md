# Lab 5

For this lab I decided to create a bash script that replicates the lab 7 CLDQ tasks. As with lab 7, I forked the [lab 7](https://github.com/ucsd-cse15l-w23/lab7) repository to my own github account before running the script. I also used the following online resources to help me complete this bash script: https://www.geeksforgeeks.org/sed-command-in-linux-unix-with-examples/.

## The Completed Script

Here is the completed bash script.sh script that successfully completes all the tasks. Next, I will go through the file line-by-line to demonstrate how I wrote the script.

```
CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

ssh -t cs15lwi23akp@ieng6.ucsd.edu "
    echo 'SSH Into ieng6'

    rm -rf lab7
    git clone git@github.com:ThaimanDigital/lab7.git
    cd lab7
    echo 'Finished Cloning'

    javac -cp $CPATH *.java
    java -cp $CPATH org.junit.runner.JUnitCore ListExamplesTests
    echo 'Demonstrate Tests Fail'

    sed -i '43 s/index1/index2/' ListExamples.java
    javac ListExamples.java
    java -cp $CPATH org.junit.runner.JUnitCore ListExamplesTests
    echo 'Demonstrate Tests Pass'

    git add ListExamples.java
    git commit -m 'Fixed'
    git push
    echo 'Tasks Completed'
"
```

### Step 1: SSH Into ieng6

The first issue I ran across in this script was ssh into my ieng6 account and getting bash to run commands from inside ieng6. At first, by script looked like this:

```
ssh cs15lwi23akp@ieng6.ucsd.edu 
echo 'SSH Into ieng6'
```

But I soon realized that the `echo` command would only execute once I had exited the ieng6 server. To circumvent this issue I realized I had to place the commands I wished to run within ieng6 inside the parenthesis after the ssh command. This is why the remainder of the commands inside the bash script are inside the parenthesis. I added `echo 'SSH Into ieng6'` to my bash script to demonstrate that I had successfully ssh into the server. Here is the screenshot demonstrating this section of the script working:

![](/images/Lab5-1.png)

### Step 2: Cloning Lab7 into ieng6

This next step was fairly simple because the commands were identical to how I inputted them in lab 7 CLDQ. I first removed any current lab7 folder from the directory with `rm -rf lab7`. Then, I cloned the repository from my github page using the ssh key and then changed the working directory to the new lab7 folder. I added `echo Finished Cloning` to the bash script to show that this step was completed successfully. Here is a screenshot demonstrating this section of the script working:

![](/images/Lab5-2.png)

### Step 3: Demonstrating JUnit Test Failures

Again, the bash code for this section is almost identical to my manual inputs from lab7 CLDQ. The only difference being that I saved the classpath as a bash variable `CPATH`, this way I didn't have to repeatedly type the classpath out everytime I want to compile and run JUnit Tests. Also, I added `echo Demonstrate Tests Fail` to my script to show that this task was executed correctly. Here is the screenshot of the script working:

![](/images/Lab5-3.png)

### Step 4: Editing the ListExamples.java File

This was the most involved part of making this bash script because the strategy I employed to edit the file was completely different than how I would have manually edited the file. In lab7 I used the `nano` command to open the ListExamples.java file and then make the correct changed to the file to pass the tests. However, I soon realized that writing a bash script to navigate through a file in `nano` and make and save changes would be difficult if not impossible. So I looked up other methods of editing a file from the terminal to see if there was a more efficient way of doing it. 

After a quick search I came across the `sed` command, which stands for Stream Editor, which allows us to make edits to files from the command line. After some trial and error the final line of code that I used was: `sed -i '43 s/index1/index2/' ListExamples.java` which I will explain shortly. The `-i` extention ensures that `sed` edits files in place, meaning that the command will overwrite the existing file with the changes made. Next, I learned that `sed` has lots of adresses that allows users to edit/replace/delete lines of text from a file. The `s/` address that I use in the script allows users to replace text in the following format: `s/regular expression/replacement/flags`. Because I was trying the replace `index1` with `index2` on line 43 of ListExamples.java, the regular expression I used was `index1` and the replacement was `index2`. Flags allow users to make mores
