# Lab 3

The `find` utility is a useful terminal command for finding files that fit a certain description within a directory. It operates by evaluating every 
file in a given directory against an expression and printing the results. There are many additional options to be used with `find` that can be 
very useful. The format of using the command is `find [path...] [expresssion]`
Here are four examples of using `find` in different ways on the [/written=-2](https://github.com/ucsd-cse15l-w23/skill-demo1-data.git) directory.


## -name

The most useful primary option for `find` is likely `-name <pattern>` which evaluates the last compenent of given path name against the given pattern. 
You can also use special characters such as `?` and `*` in the pattern.

### Example: Finding path names containing "Italy"

!()[images/name1.png]
