# Shell Commands

This repository describes some of the basic shell commands we will learn in this course. This list acts as a starting point to use basic command line arguemnts. 


# File Management

Replacing your File Explorer/Finder is the best way to get started with using a shell. Once you start using them more extensively, you will see the power these commands have over their GUI counterparts.

## `ls`

Lists files in a directory. Following are some options to use with `ls`:

```bash

ls
ls -a                                               # List all contents of a folder including hidden files/folders
ls -l -h                                            # List details of the contents in a human-readable form

```

## `cd`

Change directory to the given path.

``` bash

cd ../                                              # Change to the directory one level up
cd ../../                                           # Change to the directory two levels up
cd -                                                # Go back to the last directory you were in
cd ~                                                # Go to home directory

```

## `pwd`    

Print working directory

```bash
pwd
```

## `touch`

Create a file

```bash

touch foo.txt                                       # Create a file called foo.txt in the current working directory
touch ../foo.txt                                    # Create a file in parent folder
touch foo.txt bar.txt                               # Create two files
touch {foo, bar}.txt                                # Create two files

```

## `mkdir`

Create a directory

```bash
mkdir some_foo                                      # Create a directory call `some_foo`
mkdir -p some_foo/another_foo/more_foo              # Create `more_foo` and also create folders in the path that are non-existent
```

## `rm`

Remove file/directory

```bash
rm foo.txt                                          # Remove the file `foo.txt`
rm -rf some_foo/                                    # Remove `some_foo` and its sub-content
```

## `cat`

Displays content of a file

```bash
cat foo.txt
```


## `head`

Get the top 10 lines of a file

```bash
head file.txt                                       # Get the first 10 lines of the file
head -n N file.txt                                  # Get the first N lines of the file
```


## `tail`

Get the last 10 lines of a file

```bash
tail file.txt                                       # Get the last 10 lines of the file
tail -n N file.txt                                  # Get the last N lines of the file
```
