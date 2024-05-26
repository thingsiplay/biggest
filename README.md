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
[paths] | biggest [options] [path...]
```

By default the apparent size option of `du` is used, which will report entire
size of a directory as well. But this does not guarantee a perfect output and
may vary by real disk usage.

If no arguments are given, it defaults to all files and folders in current
working directory:

```bash
biggest
```

Give a list of files as arguments to report:

```bash
biggest *.png
```

If pipe is connected, then it will attempt to read newline separated list of
paths from stdin:

```bash
find ~/.* -maxdepth 0 -type f | biggest
```

Show a horizontal bar instead file size numbers with option `-b`. Combine it
with `-r` to show file size in relative percentage.

```bash
biggest -rb *
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

List only files with minimum size in bytes using option `-s` . Optionally add
an unit to the number: `K`, `M`, `G`, `T`, `P`, `E`, `Z`, `Y`, `R`, `Q` to
automatically calculate size with powers of 1024.

```bash
biggest -s 10k
```

Reverse size: Negative number with a minus sign in option `-s` will only output
files that do not exceed maximum size:

```bash
biggest -s -1g
```

Have a great rest of your day.
