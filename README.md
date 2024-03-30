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
```
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