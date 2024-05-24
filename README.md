# biggest

List biggest files and folders.

- Author: [Tuncay D.](https://github.com/thingsiplay)
- Source: [Github](https://github.com/thingsiplay/biggest)
- License: [MIT](LICENSE)

## What is this?

A simple wrapper to Linux `du` command, combining with a few other commands to
form the exact output I want. Think of this script as a super alias, nothing
more. Goal is to get a list of the biggest files and folders sorted by their
size.

## Installation

This is a Bash script. It does not need an installation. Just download and give
it the executable bit.

### Requirements

Linux and Bash. Executes only a combination of standard GNU Linux utilities.

### Download

There is no release or build version of the script. Just get the source, make
the script executable and put the file in a folder that is found in the $PATH
variable.

```bash
git clone https://github.com/thingsiplay/biggest
cd biggest
chmod +x biggest
```

## Usage

Just run the script with or without files and folders to calculate.

```bash
biggest [options] [path...]
```

By default the apparent size option of `du` is used, which will report entire
size of a directory as well. But this does not guarantee a perfect output and
may vary by real disk usage.

If no arguments are given, it defaults to all files and folders in current
working directory:

```bash
biggest
```

Specify to calculate and report only specified files:

```bash
biggest *.png
```

Show a horizontal bar instead numbers for file size:

```bash
biggest -b *
```

Directories and files can be excluded using wildcards with option `-x` as well
(but put them in quotes):

```bash
biggest -x Gaming -x '.steam*' *
```

Search deeper into directories with option `-d`, instead just looking on their
surface. And output a specific amount of paths with option `-n`:

```bash
biggest -d 2 -n 5 kiwix/*
```

Have a great rest of your day.
