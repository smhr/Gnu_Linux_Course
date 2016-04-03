# Bash programmming

---

## Hello, World: Your First Shell Program

```bash
echo Hello, World!
```
--

### How to execute it?

---

## Input, Output, and Throughput

---

### Parameter and Variables

* A parameter is an entity that stores values
    * positional parameters
    * special parameters
    * variables
---    

#### positional parameters

* arguments present on the command line and referenced by a number
* The first argument is `$1`, the second is `$2`, and so on.

```bash
printf "Hello, %s!\n" "$1"
```
--

Now you can call the script with an argument to change its output:
```bash
$ hello John
Hello, John!
$ hello Susan
Hello, Susan!
```
---
#### positional parameters
* The Bourne shell could only address up to nine positional parameters
* In BASH, to access positional parameters greater than 9, the number must be enclosed in braces: `${15}`.
---
### Special `*@#0$?_!-` Parameters
* `$*` and `$@`, expand to the value of all the positional parameters combined.

--
* `$#` expands to the number of positional parameters

--
* `$0` contains the path to the currently running script or to the shell itself if no script is being executed

--
* `$$` contains the process identification number (PID) of the current process,

--
* `$?` is set to the exit code of the last-executed command

--

* `$_` is set to the last argument to that command

--
* `$!` contains the PID of the last command executed in the background

--
* `$-` is set to the option flags currently in effect

---
### Variables

* `name=VALUE`
* Many variables are set by the shell itself, including three you have already seen: HOME, PWD, and PATH.

### Arguments and Options
* The following command lines all have four arguments:

```bash
echo 1 '2   3'  4 5
echo -n Now\ is the time
printf "%s %s\n" one two three
```

* In the second command, the first argument is an option
---
### printf: Formatting and Printing Data

* Almost similar to the C function

`printf FORMAT ARG ...`

--

* The FORMAT string can contain ordinary characters, escape sequences, and format specifiers
--

### Format Specifiers
--

* The most commonly used specifiers are `%s`, `%d`, `%f`, and `%x`

---

* The `%s` specifier prints the literal characters in the argument

```bash
$ printf "%s\n" Print arguments on "separate lines"
```
--
* `%b` is like `%s` except that escape sequences in the arguments are translated

```bash
$ printf "%b\n" "Hello\nworld" "12\tword"
```
--

* Integers are printed with `%d`.

```bash
$ printf "%d\n" 23 45 56.78 0xff 011
```
--

* For decimal fractions or floating-point numbers, use `%f`

```bash
$ printf "%f\n" 12.34 23 56.789 1.2345678
```
--

* Floating-point numbers can be presented in exponential notation using `%e`

```bash
printf "%e\n" 12.34 23 56.789 123.45678
```

---