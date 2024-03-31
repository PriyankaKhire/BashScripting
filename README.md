# Bash Scripting
## Installing Bash on Windows
- Go to CMD and type ```wsl --install```
- Reboot the system
- Open WSL to then have ubuntu on your windows system
- You can now type ```bash``` and run bash shell

## What is Bash ?
Bash is a shell program.

A shell program is typically an executable binary that takes commands that you type and (once you hit return), translates those commands into (ultimately) system calls to the Operating System API.

## Globbing
Glob characters:
- ```*``` Matches everything
- ```?``` Matches single character
- ```[abd]``` Matches any character from a, b or d
- ```[a-d]``` Matches any character from a, b, c or d

While globs look similar to regular expressions (regexes), they are used in different contexts and are separate things.

### Dotfiles
To list all files that start with dot, example ```.git``` we can use ```echo .*```

## Variables
### Creating Variable
```bash
MYSTRING=astring
echo $MYSTRING # Echoes astring
```
Variables don’t need to be capitalized, but they generally are by convention.

If you want a string variable with space in it then use quotes.
```bash
MYSENTENCE="A sentence" #Note no space between = sign
echo $MYSENTENCE
```
If you want to see all the variables that are available to you in your shell, type:
```bash
compgen -v
```
### Arrays
Declaring array
```bash
stringArray=("cat" "dog" "mouse" "frog")
intArray=(1 2 3 4 5 6 7 8 9) # Notice no comma,
```
echoing this array will only give first element, we need ```for statement``` to output all elements of the array.

To access individual elements in the array
```bash
echo ${stringArray[3]} # Will output: frog
```

## Function
Basic function
```bash
function myfunc {
  echo "Hello world"
}
```
### Arguments
To call a function with arguments:
```bash
function_name "$arg1" "$arg2"
```
The function refers to passed arguments by their position (not by name), that is ```$1```, ```$2```, and so forth. ```$0``` is the name of the script itself.

Also, you need to call your function after it is declared.
```bash
#!/usr/bin/env sh

foo 1  # this will fail because foo has not been declared yet.

foo() {
    echo "Parameter #1 is $1"
}

foo 2 # this will work.
```

## Redirect
Bash redirection is a way to control where the input to and output from commands and scripts go.
- **Standard Input (stdin) Redirection (```<```):** This allows you to change where a command gets its input from.
```bash
command < input.txt
```
This command runs ```command``` and takes the contents of ```input.txt``` as input instead of waiting for input from the keyboard.

- **Standard Output (stdout) Redirection (```>```):** This allows you to change where a command sends its output.
```bash
command > output.txt
```
This command runs ```command``` and saves its output to ```output.txt``` instead of displaying it on the terminal. If ```output.txt``` already exists, it will be overwritten.

- **Appending Output (```>>```):** Similar to stdout redirection with ```>```, appending output with ```>>``` allows you to add command output to the end of an existing file instead of overwriting it.
- **Standard Error (stderr) Redirection (```2>```):** In addition to stdout, commands can also produce error messages on stderr. Similar to stdout redirection, 2> allows you to redirect stderr to a file.
- **Pipe (```|```) :** takes the standard output of one command and passes it as the input to another.
```bash
command1 | command2
```
This command runs command1 and sends its output to command2 as input. This can be chained indefinitely to create complex operations.






# Good Reads
- [Bash Array – How to Declare an Array of Strings in a Bash Script](https://www.freecodecamp.org/news/bash-array-how-to-declare-an-array-of-strings-in-a-bash-script/)
- [Arguments in function](https://stackoverflow.com/questions/6212219/passing-parameters-to-a-bash-function)
- [Advance Bash-Scripting Guide](https://tldp.org/LDP/abs/html/complexfunct.html)