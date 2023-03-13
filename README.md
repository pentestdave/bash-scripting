# Bash Scripting in Linux

A bash/shell script is a computer program designed to be run by a Unix shell, a command-line interpreter. Typical operations performed by shell scripts include file manipulation, program execution, and printing text. 

# TOC

1. [Hello World](#hello-world)
2. [Comments](#comments)
3. [IF-ELSE Statement](#if-else-statement)
4. [Operators](#operators)
5. [File Operators](#file-operators)
6. [String Comparison Operators](#string-comparison-operators)
7. [Numeric Comparison Operators](#numeric-comparison-operators)
8. [Parenthesis Explained](#parenthesis-explained)

## Hello World

```bash
echo "Hello World from Bash Script!"
```

## Comments

* Single line comments

```bash
# This is a single line comment
```

* Multi-line comments

```bash
: '
This is a comment
spanning over multiple
lines '
```

## IF-ELSE Statement

```bash
age=16

if [ $age -lt 18 ]
then
        echo "You're not an adult yet!"
else
        echo "You're an adult now!"
fi
```

## Operators

[More about Bash Script operators](https://opensource.com/article/19/10/programming-bash-logical-operators-shell-expansions)

### File operators

File operators are a powerful set of logical operators within Bash.

* -a -> True if the file exists; it can be empty or have some content but, so long as it exists, this will be true.

* -b -> True if the file exists and is a block special file such as a hard drive like /dev/sda or /dev/sda1.

* -c -> True if the file exists and is a character special file such as a TTY device like /dev/TTY1.

* -d -> True if the file exists and is a directory.

* -e -> True if the file exists; this is the same as -a above.

* -f -> True if the file exists and is a regular file, as opposed to a directory, a device special file, or a link, among others.

* -g -> True if the file exists and is set-group-id, SETGID.

* -h -> True if the file exists and is a symbolic link.

* -k -> True if the file exists and its "sticky'" bit is set.

* -p -> True if the file exists and is a named pipe (FIFO).

* -r -> True if the file exists and is readable, i.e., has its read bit set.

* -s -> True if the file exists and has a size greater than zero; a file that exists but that has a size of zero will return false.

* -t fd -> True if the file descriptor fd is open and refers to a terminal.

* -u -> True if the file exists and its set-user-id bit is set.

* -w -> True if the file exists and is writable.

* -x -> True if the file exists and is executable.

* -G -> True if the file exists and is owned by the effective group ID.

* -L -> True if the file exists and is a symbolic link.

* -N -> True if the file exists and has been modified since it was last read.

* -O -> True if the file exists and is owned by the effective user ID.

* -S -> True if the file exists and is a socket.

* file1 -ef file2 -> True if file1 and file2 refer to the same device and iNode numbers.

* file1 -nt file2 -> True if file1 is newer (according to modification date) than file2, or if file1 exists and file2 does not.

* file1 -ot file2 -> True if file1 is older than file2, or if file2 exists and file1 does not.

### String Comparison Operators

String comparison operators enable the comparison of alphanumeric strings of characters. There are only a few of these operators.

* -z -> True if the length of string is zero.

* -n -> True if the length of string is non-zero.

* str1 == str2 -> True if the strings are equal; a single = should be used with the test command for POSIX conformance. When used with the *[[* command, this performs pattern matching as described above (compound commands).

* str1 != str2 -> True if the strings are not equal.

* str1 < str2 -> True if string1 sorts before string2 lexicographically (refers to locale-specific sorting sequences for all alphanumeric and special characters).

* str1 > str2 -> True if string1 sorts after string2 lexicographically.

### Numeric Comparison Operators

Numeric operators make comparisons between two numeric arguments. Like the other operator classes, most are easy to understand.

* arg1 -eq arg2 -> True if arg1 equals arg2

* arg1 -ne arg2 -> True if arg1 is not equal to arg2

* arg1 -lt arg2 -> True if arg1 is less than arg2

* arg1 -le arg2 -> True if arg1 is less than or equal to arg2

* arg1 -gt arg2 -> True if arg1 is greater than arg2

* arg1 -ge arg2 -> True if arg1 is greater than or equal to arg2

## Parenthesis Explained

In bash scripting, there are various syntax and ways of writing parenthesis to give desired results. [More about parenthesis](https://linuxconfig.org/bash-scripting-parenthesis-explained)

* Double parentheses **(( ))** are used for arithmetic and variables used inside double parentheses do not need to be prefixed with **'$'**:

```bash
((var++))
((var = 3))
for ((i = 0; i < VAL; i++))

        echo $((var + 2))
```

* Square brackets **[]** are used for test construct:

```bash
VAR=2
if [ $VAR -eq 2 ]
then
        echo 'yes'
fi
```

* Double square brackets **[[]]** offer extended functionality to single
square brackets, useful for the regular expression operator =~:

```bash
$VAR='some string'
if [[ $VAR =~ [a-z] ]]; then
        echo 'is alphabetic'
fi
```

* Curly braces **{}** are used to delimit a variable and are also used for parameter expansion:

```bash
foo='stage'
echo $fooone
           ... returns empty line
echo ${foo}one

# Parameter expansion
$ var="abcdefg"; echo ${var%d*}
```

