# Shell Commands

This repository describes some of the basic shell commands we will learn in this course. This list acts as a starting point to use basic command line arguemnts. 


# File Management

Replacing your File Explorer/Finder is the best way to get started with using a shell. Once you start using them more extensively, you will see the power these commands have over their GUI counterparts.

To demonstrate the outputs of this commands, we will assume that I am working in the following path:
`/Users/vijayantajain/COS225`. 

##### WINDOWS USERS

To get into your C: folder and then consecutively into any other folder from your Ubuntu shell, you need to add `/mnt/` to the path. For example, if the path to your Documents folder is as follows: `C:/Users/vijayantajain/Documents`, then go into your Documents folder from your Ubuntu shell type the command `cd /mnt/c/Users/vijayantajain/Documents`

## `pwd`    

It stands for Print Working Directory and helps you find out from the terminal your current path. Think of this command as a "Show Your Location" feature you get in your favorite Maps app (the little target or bullseye looking icon ). 


```bash
pwd
```

Here is what it looks like on my machine after I type `pwd`

```bash
> pwd
/Users/vijayantajain/COS225
```

## `ls`

Lists files in a directory. If you are in a specific folder and you want to know what are the contents of that specific folder, use this command.

Following are some options to use with `ls`:

```bash

ls
ls -a                                               # List all contents of a folder including hidden files/folders
ls -l -h                                            # List details of the contents in a human-readable form

```

Here is what it looks like on my machine after I type `ls`

```bash
> ls
barfoo.txt
```

This indicates that in my current working directory (i.e., the current folder I am in), there is one file called `barfoo.txt`.

## `cd`

This command helps you go into other directories from your current directory.

``` bash

cd directory_name                                   # Go into the folder called `directory_name`.
                                                    # Assuming there is a directory in current working directory
                                                    # by the name of `directory_name`

cd ../                                              # Change to the directory one level up
cd ../../                                           # Change to the directory two levels up
cd -                                                # Go back to the last directory you were in
cd ~                                                # Go to home directory
```

Let's say you are in `/Users/vijayantajain/COS225` and you want to go to `/Users/vijayantajain/COS125/Projects` folder. Here are series of commands you would take

```bash
> pwd                                               # Find out what is your current directory
/Users/vijayantajain/COS225
> cd ../                                            # Go one level up in your path i.e., go into `/Users/vijayantajain`
> pwd                                               # Make sure you went one level up
/Users/vijayantajain
> cd COS125/                                        # Once inside `/Users/vijayantajain/`, go into `COS125` folder
> pwd                                               # Check where you are now
/Users/vijayantajain/COS125
> cd Projects                                       # Go into the `Projects` folder which is inside `COS125`
> pwd
/Users/vijayantajain/COS125/Projects
```

#### NOTE:

If you have a space in your folder name, then you need to use the special esacpe character. For example, if your folder's name is "COS 125" then you would need to type in the following command

```bash
> pwd                                               # Find out what is your current directory
/Users/vijayantajain/COS225
> cd ../                                            # Go one level up in your path i.e., go into `/Users/vijayantajain`
> pwd                                               # Make sure you went one level up
/Users/vijayantajain
> cd COS\ 125/                                      # The `\ ` allows you to use spaces in your path when changing directories
> pwd                                               # Check where you are now
/Users/vijayantajain/COS 125
```

## `touch`

This command helps you create a file in the current folder. Note that you need to specify the name of the file you want to create.

```bash

touch foo.txt                                       # Create a file called foo.txt in the current working directory
touch ../foo.txt                                    # Create a file in parent folder
touch foo.txt bar.txt                               # Create two files
touch {foo, bar}.txt                                # Create two files
```

Here is what it looks like on my machine after I type `touch`

```bash
> touch foo.txt                                     # Created a file called foo.txt
> ls                                                # Listing the contents of the current folder to make sure it was a success
barfoo.txt foo.txt
```


## `mkdir`

Create a directory in your current folder

```bash
mkdir some_foo                                      # Create a directory call `some_foo`
mkdir -p some_foo/another_foo/more_foo              # Create `more_foo` and also create folders in the path that are non-existent
```

Here is what it looks like on my machine after I type `mkdir`

```bash
> mkdir some_foo                                    # Create a folder called `some_foo` inside `COS225`
> ls                                                # List the contents of `COS225` to ensure it was created
barfoo.txt foo.txt some_foo
> mkdir -p some_foo/another_foo/bar_foo_bar         # Create folders inside `some_foo` using `-p` 
> cd some_foo                                       # Go into `some_foo`
> pwd                                              
/Users/vijayantajain/COS225/some_foo
> ls                                                # We see `another_foo` was created even though it did not exist before
another_foo
> cd another_foo
> pwd
/Users/vijayantajain/COS225/some_foo/another_foo
> ls
bar_foo_bar
> cd bar_foo_bar
> pwd
/Users/vijayantajain/COS225/some_foo/another_foo/bar_foo_bar
```

## `rm`

Remove file/directory

```bash
rm foo.txt                                          # Remove the file `foo.txt`
rm -rf some_foo/                                    # Remove `some_foo` and its sub-content
```

Here is what it looks like on my machine after I type `rm`

```bash
> ls
barfoo.txt foo.txt some_foo
> rm foo.txt
> ls
barfoo.txt some_foo
> rm -rf some_foo
> ls
barfoo.txt
```


## `cat`

Displays the entire content of a file. It is known as the concatenate command. 

```bash
cat barfoo.txt
```

Here is what it looks like on my machine after I type `cat`

```bash
> cat barfoo.txt
This is the first line
Second line of the file
Third line in the file
Another line, the fourth line in the file
fifth line, this is getting boring
sixth line in the file. I am hungry now
ok, last line in the file. This is all I can write.
```


## `head`

Get the top 10 lines of a file

```bash
head file.txt                                       # Get the first 10 lines of the file
head -n N file.txt                                  # Get the first N lines of the file
```

Here is what it looks like on my machine after I type `head`

```bash
> head -n 3 barfoo.txt                              # Get the first 3 lines of `barfoo.txt`
This is the first line
Second line of the file
Third line in the file
```


## `tail`

Get the last 10 lines of a file

```bash
tail file.txt                                       # Get the last 10 lines of the file
tail -n N file.txt                                  # Get the last N lines of the file
```

Here is what it looks like on my machine after I type `tail`

```bash
> tail -n 5 barfoo.txt                             # Get the last 5 lines of `barfoo.txt`
Third line in the file
Another line, the fourth line in the file
fifth line, this is getting boring
sixth line in the file. I am hungry now
ok, last line in the file. This is all I can write.
```

## `wc`

We can use this command to count the contents of a file without opening the file. We can use this to count the number of lines, the size of the file in bytes, or the number of words

```bash
> wc barfoo.txt                                         # Number of lines, words, and characters
    7   50  239 barfoo.txt
> wc -l barfoo.txt                                      # Number of lines
    7   barfoo.txt
> wc -w barfoo.txt                                      # Number of words
    50 barfoo.txt
> wc -c barfoo.txt                                      # Number of characters
    239 barfoo.txt
```

## `tar`

Compresses file into a tarball, very similar to create zipped folder.  Assume you have a folder called `bar` which has multiple .txt files, then you can use the following command

```bash
tar -czvf files.tar.gz bar/
```

Here is what each flag in `czvf` means:

* `c` - Create a tarball.
* `z` - Use `gzip`, a program to compress file, you can use others as well.
* `v` - Be verbose in your output.
* `f` - Specify the name of the tarball



You can also use `tar` to uncompress the files or extract the files from `.tar.gz`

```bash
tar -xzvf files.tar.gz
```

The `x` flag in `xvzf` means to extract from a tarball, instead of creating a tarball. The `z`, `v`, and `f` mean the same thing from above. 
