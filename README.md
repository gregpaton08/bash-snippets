# bash-snippets

## shebang

```
#!/usr/bin/env bash
```

## Parsing command line arguments

```
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
