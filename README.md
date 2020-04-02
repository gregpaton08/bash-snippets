# bash-snippets

1. [shebang](#shebang)
1. [Functions](#functions)
1. [Parsing command line arguments](#parsing-command-line-arguments)
1. [Get the current script directory](#get-the-current-script-directory)
1. [For Loop](#for-loop)

## shebang

```bash
#!/usr/bin/env bash
```

## Functions

```bash
# Define a function.
function quit {
   exit
}

# Call the function.
quit

# Define a function that takes a paramter.
function printarg {
    echo $1
}

# Call the function with an argument.
printarg "Hello, world!"
```

## Parsing command line arguments

```bash
for i in "$@"
do
case $i in
    -e=*|--extension=*)
    eval EXTENSION="${i#*=}"
    shift # past argument=value
    ;;
    -s=*|--searchpath=*)
    eval SEARCHPATH="${i#*=}"
    shift # past argument=value
    ;;
    -l=*|--lib=*)
    eval LIBPATH="${i#*=}"
    shift # past argument=value
    ;;
    --default)
    DEFAULT=YES
    shift # past argument with no value
    ;;
    *)
    # unknown option
    ;;
esac
done
```

## Get the current script directory

```bash
DIR="$( cd "$( dirname "${BASH_SOURCE[0]}" )" >/dev/null 2>&1 && pwd )"
```

## For Loop

```bash
for i in {0..5}; do
   echo $i
done
# Prints out:
# 0
# 1
# 2
# 3
# 4
# 5
```
