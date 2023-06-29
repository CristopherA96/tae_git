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

In order to do repetitive tasks, we typically use loops, some of them are:

- **while**: it repeats statements while a given condition is true. It means, that while loop tests the condition before executing repetitive tasks.
- **for**: it executes multiple statements every time.
- **foreach**: it works equal to for loop but using simplified syntaxis.

**while**
```sh
    while {condition} {
        # tasks to repeat
    }
```

**for**
```sh
    for {initialization} {condition} {increment} {
        # tasks to repeat
    }
```

**foreach**
```sh
    foreach {element} {list_body} {
        # tasks to repeat
    }
```

Some examples for loop structures shown above are:

!!! example
    ```sh
    # while
        set var1 10
        while { $var1 > 10 } {
            puts "Value of var1: $var1"
            incr var1
        }

    # for
        for { set i 10 } {$i < 10} {incr i} {
            puts "Index $i"
        }
    
    # foreach
        set list { 1 2 3 4 }
        foreach item $list {
            puts "Item in list is $item"
        }
    ```
!!! info
    Also, we have loop control methods such as `break` and `continue`.

## Command substitution
---

This term is used to modify the value of a built-in function of the value of a variable. To do that, we usually use the `expr` command and then the new value, all of this into square brackets

```sh
    set var1 10
    set var2 [expr $var1 + 2]
```

!!! info
    `expr` is a command used to evaluate a given expression and display its standard output (stdout).

## Variable substitution
---

Another great feature of Tcl is something called "variable substitution", it refers to accessing the value stored in a variable with a dollar sign `$` before the variable name

```sh
    set var1 10
    puts "a is $a"
```

## Data structures

**Array**
An array is a group or a container of variables which contains each element on a specific index.

```sh
    set array_name(index) value

    # empty array
    array set array_name {}
```

!!! info
    Some built-in functions to manipulate arrays are:
    - Size of array `[array size array_name]`
    - Exists element in array `[array exists array_item]`
    - Return names of index in array `[array names array_name]`

**List**
A list as we know is a collection of items.

```sh
    set my_list { item1 item2 item3 ... }       ;# Option 1 to declare a list
    set my_list [list item1 item2 item3 ... ]   ;# Option 2 to declare a list using built-in function `list`
    set my_list [split "items separated by a character " split_character]   ;# Option3 to declare a list using a split character to separate items
```
!!! info
    Some built-in functions are:
    - Append item in list `append list_name split_character value` or `append list_name value`
    - Length of list `[llength list_name]`
    - List item at index `[lindex list_name index]`
    - Insert items at index `[linsert list_name index value_1 value_2 ... ]`
    - Replace items  at index `[lreplace list_name first_index last_index value_1 value_2 ... ]`
    - Set item at index `[lset list_name index value]`
    - Transform list to variables `lassign list_name var1 var2 ...`
    - Sort a list `[lsort list_name]`

**Dictionary**
A dictionary is an associative array, it maps values to keys.

```sh
    dict set dictionary_name key value      ;# Option 1 to declare a dictionary
    dict create dictionary_name key1 value1 key2 value2 ...
```

!!! info
    Some built-in functions are:
    - Size of dictionary `[dict size dictionary_name]`
    - Get value for key `[dict get $dictionary_name $key]`
    - Get all keys `[dict keys $dictionary_name]`
    - Get all values `[dict values $dictionary_name]`
    - Know if key exists `[dict exists $dictionary_name $key]`

**Procedures**
Procedures are like functions in other languages.

```sh
    proc procedure_name {arguments} {
        # Tasks to implement
    }
```

Some examples for those data structures are shown below:

!!! example
    ```sh
        # Array
        array set my_array { 1 2 3 4 5 6 }           ;# Initialize array with some values
        for { set i 0 } { $i < [array size my_array] } { incr i } {
            puts "Value_$i is $my_array($i)"
        }

        # List
        set my_list_1 { 1 2 3 4 5 6 }
        puts $my_list_1
        set my_list_2 [list 1 2 2 4 4 5 6]
        puts $my_list_2
        set my_list_3 [split "mon_tue_wed_thu_fri_sat_sun" _]
        puts $my_list_3

        # Dictionary
        set days [dict create day1 "monday" day2 "tuesday"]
        puts $days

        foreach item [dict keys $days] {                    ;# Iterating into entire days dictionary (keys with values)
            set value [dict get $days $item]                ;# Setting value var with the return of getting value for each key
            puts $value                                     ;# Printing value content
        }

        # Procedures
        proc mult {var1 var2} {
            set mult_res [expr { $var1 * $var2 } ]
            return "The product of $var1 * $var2 is $mult_res"
        }
        puts [add 20 30]
    ```

## File I/O
In Tcl we can handle with files by using some built-in functions, such as `open, read, puts, gets, close`.

**Open a file**
```sh
    open file_name access_mode          ;# Access modes are r -> read, w -> write, a -> append, r+ -> read and write (file shall exist), w+ -> read and write (file is overwritten if exists otherwise it will create it.), a+ -> read and write (read will start at beginning, but writing can only be appended). 
```

**Close a file**
```sh
    close file_name 
```

**Write a file**
```sh
    puts $filename "text to write"
```

**Read a file**
```sh
    set file_data_to_read [read $filename]
```

Some examples for those instructions are shown below.

!!!example
```sh
    # Writing into text.txt file
    set filename_pointer [open "text.txt" w+]           ;# Opening file to write into it
    puts $filename_pointer "test 1"                     ;# Writing test 1 in the file text.txt
    close $filename_pointer                             ;# Closing filename_pointer file

    # Reading a file
    set filename_pointer [open "text.txt" r]            ;# Opening file to read the text file
    set file_data_to_read [read $filename_pointer]      ;# Reading filename
    puts $file_data_to_read                             ;# Printing data that was read
    close $filename_pointer                             ;# Closing filename_pointer file

    # Another option to work with text.txt file
    set filename_pointer [open "text.txt" w+]
    puts $filename_pointer "test\ntest"
    close $filename_pointer
    set filename_pointer [open "text.txt" r]

    while { [gets $filename_pointer data] >= 0 } {
        puts $data
    }
    close $filename_pointer
```

## Regular expression
---

To work with regular expression we use `regexp` in Tcl, we know that regular expression is a sequence of characters that contains a search pattern.

```sh
    regexp optional_switches patterns search_string full_match sub_match_1 ...
```

| Regular expression | Description |
| ------------------ | ------------ |
|        x           | Exact match  |
|    [a-z]           | Any lowercase letter from a-z |
|    .           | Any character |
|    ^           | Beginning string should match |
|    $           | Ending string should match |
|    \^           | Backslash sequence to match special character ^. |
|    ()           | Add the above sequences inside parenthesis to make a regular expression |
|    x*           | Should match 0 or more ocurrences of the preceding x |
|    x+           | Should match 1 or more ocurrences of the preceding x |
|    [a-z]?           | Should match 0 or 1 occurrence of the preceding x |
|    {digit}           | Matches exactly digit ocurrences of previous regex expression. Digit that contains 0-9 |
|    {digit,}           | Matches 3 or more digit ocurrences of previous regex expression. Digit that contains 0-9 |
|    {digit1, digit2}   | Ocurrences matches the range between digit1 and digit2 ocurrences of previous regex expressions. |



## Special variables
---

Additional to all basic features that Tcl has, there are something called special variables. Those variables shall have special functionality.

| Regular expression | Description |
| ------------------ | ------------ |
| argc           | Refers to a number of command-line arguments |
| argv           | Refers to the list containing the command-line arguments |
| argv0 | Refers to the file name of the file being interpreted or the name by which we invoke the script |
| env   | Used to represent the array of elements that are environment variables |
| errorCode | Used to provide the error code for the last error |

There are more special variables but some of the most useful are shown above.


## Laboratory
---

Develop a program that will implement:

- Procedures for basic arithmetical operations, such as add, sub, mul, div with two numbers.
- Each procedure can be access by selecting an option in a menu.
- The values for each number and the results of each operation shall be store in a file. i.e. add 2 4 6
- In the menu, shall have an option to read the numbers into the file which can be used to do the other operations with those values, it is something like to import content of a file to handle with.

!!! info
    Please, try to use as much as you can the features provided in this guide. Be creative.