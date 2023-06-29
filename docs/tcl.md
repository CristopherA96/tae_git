# Tcl
---

## Overview
---

TCL means Tool Command Language, it is one of the most popular scripting languages in the industry just like Perl.

It supports the next characteristics:

- Variables, Control structures, Command substitution
- Quotes and braces, String manipulation
- I/O and Network sockets
- File management, Time and date manipulation
- Functions and Subprocesses
- List, Arrays and Events
- Comments (Inline and not inline)
- Built-in functions

In the following chapters we will be learning a little about each of the basic features mentioned.

## Variables
---

Tcl as many other languages allows us to store values in variables. This values can be access by using a command, such as `set`.

This command is typically used to **write and read** variables.

!!! example
    ```sh
    # Writing in var1 the value 10
    set var1 10

    # Reading the value of var1
    set var1

    # To use value of variable in a command
    expr $var1+20
    ```
!!! info
    In Tcl we do not have **data types**, also we **do not need to declare variables**, they will be created automatically once it is set.

## Control structures
---

Some of the most common control structures include conditional, looping and procedures. This control structures are commands that will take Tcl scripts as arguments.

### Conditional
---

The structure for decisions operations using conditional structures is shown below.

**if-else**
```sh
    if {bool_expression} {                              
        # tasks to do when bool_expression is True
    } else {
        # tasks to do when boll_expression is False
    }
```

**if-else if-else**
```sh
    if {bool_expr_1} {                              
        # tasks to do when bool_expr_1 is True
    } elseif {bool_expr_2}  {
        # tasks to do when bool_expr_2 is True
    } else {
        # tasks to do when none of above conditions is True
    }
```

**switch**
```sh
    switch trigger_var {
        opt_1 {
            # Tasks to do when opt_1 is trigger
        }
        opt_2 {
            # Tasks to do when opt_1 is trigger
        }
        ...
        ...
    }
```

**'?' operator**
```sh
    trigger_var ? expr_1_True : expr_2_False
```

Some examples for conditional structures shown above are:

!!! example
    ```sh
    # if-else if-else
        set var1 10
        if { $var1 > 10 } {
            puts "The value of var1 is greater than 10"
        } elseif { $var1 != 10} {
            puts "The value is not equal to 10"
        } else {
            puts "The value is $var1"
        }

    # if-else
    set age 20
    if { $age > 20 } {
        puts "You are older than 20 years old"
    } else {
        puts "You are younger than 20 years old"
    }

    # '?' operator
    set var 1
    set var_1 [expr $var != 2 ? 3 : 4]
    puts "Value of var_1 is %var_1"
    ```

### Loops
---

AQUÍ ME QUEDÉ