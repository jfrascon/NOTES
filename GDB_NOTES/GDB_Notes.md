# GDB NOTES

## INTERESTING REFS

[Hitchhikers guied to the GDB](http://apoorvaj.io/hitchhikers-guide-to-the-gdb.html)
[Debugging with GDBServer](https://sourceware.org/gdb/onlinedocs/gdb/Server.html)

```
gdb -c core_dump_file
gdb -tui      
start
run                   run freely
(n)ext                execute next statement
(b)reak               <whatever_label_in_the_program>
q                     quit
bt                    back trace

list                  see code
<C - x a>             TUI interface
<C - l>               repaint the screen after a print to get rid off the printed message
<C - x 2>             two windows: source code and assembly.
<C - x 2> <C - x 2>   three windows: source dode, assembly and registers
<C - o>               to jump between windows in the tui
tui reg float         execute the previous command and the execute this command to show the float registers
<C - x 1>             again one window
<C - p>               previous command in the gdb's CLI
<C - n>               next command in the gdb's CLI
p $pc                 print the content of your program counter
p $sp                 print the content of the stack pointer
x <memory_address>    get the content of that memory address
reverse-stepi         go one step backwards
stepi
disas                 assembler code
¿watch <adress>?      watchpoint
reverse-continue
```

There is a Python interpreter built into gdb, so you can type python in the gdb's CLI and star using python right there

```
python print(gdb.breakpoints())               Check breakpoints in gbd using the built-in python
python print(gdb.breakpoints()[0].location)    
python gdb.Breakpoint('7')                    Create a breakpoint in the code using the built-in python
```

This breakpoint might be the last one statement executed in your program (swiss army trick! =)  )

```
b _exit.c:32
```

You can set breakpoints and you can have commands that are fired when those breakpoints are hit.
Example:

```
b main
breakpoint 2 at 0x400671...: file whatever.c, line 33
b _exit.c:32
breakpoint 3 at 0x7ff...: _exit.c:32

command 2
record       enable recording
continue
end

command 3
command_1   <= first  command to be executed when the breakpoint 3 is hit
command_2   <= second command to be executed when the breakpoint 3 is hit
...
command_n
end

set pagination off <= the speaker at the conference on youtube said that he turned this off because it could be annoying
```

## [SKIP INSTRUCTIONS](http://www.toptip.ca/2010/06/gdb-skip-instructions-or-lines-while.html)

Supposed you are at line 50 and you want to skip the following several lines of your source code and continue from line 60, you can input command

```
jump 60
```

However, the command **will continue your program till it meets next break point or the end of the program**.
So before you run the `jump` command, you should set a break point first.

```
b 60
j 60
```

Alternatively, if the line you want to skip is a function call, you can step into it first, and return right after.

```
s
return
```

You would need to mind the return value if the function returns something.
