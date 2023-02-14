# Lab 3

The `find` utility is a useful terminal command for finding files that fit a certain description within a directory. It operates by evaluating every 
path in a given directory against an expression and printing the results. There are many additional options to be used with `find` that can be 
very useful. The format of using the command is `find [path...] [expresssion]`
Here are four examples of using `find` in different ways on the [/written=-2](https://github.com/ucsd-cse15l-w23/skill-demo1-data.git) directory.


## 1: The -name primary

The most useful option for `find` is likely `-name <pattern>` which evaluates the last compenent of given path name against the given pattern. 
You can also use special characters such as `?` and `*` in the pattern.

### Example: Finding path names containing "Italy"

![](images/name1.png)

In this example the pattern is `*Italy*.txt` meaning that any path containing "Italy" should be returned by our command. The astericks are wildcard 
characters that can represent zero or many different characters of any type.

### Example: Finding non .txt path names

![](images/name2.png)

In this example the addition of `\!` before the file path represents the logical NOT operator. Meaning that find will return true for cases where the 
given expression was evaluated to false. In this case the pattern was any path containing `*.txt`, therefore the paths returned by find do not contian 
".txt"

## 2: The -s option

The  `-s` option allows you quicklky sort the given files alphabetically within each directory.

### Example: Searching through berlitz1 alphabetically

![](images/s1.png)

In this example we search through all the paths in berlitz1 directory alphabetically. This could be useful if you want to browse through paths in a 
directory in an ordered fashion.

![](images/s2.png)

Similarly, we can sort the non-fiction paths within written-2 using`-s`.
