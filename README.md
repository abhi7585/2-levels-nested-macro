# 2-levels-nested-macro

Aim: Implementation of 2-levels nested macro & its expansion.

Instructions :
1) Write a ALP using few instructions & First level macro call with no arguments.
2) Define domain/body of the first level Macro with some other macros defined with/without
arguments.
3) Define domains of each of the macros called in the first level macro.
4) Show the expansion of the Macro at the first level.
5) Also show the expansion of each of the macro at the second level.
6) Output the final expanded source code.
7) Also output the following statistics:
- Number of instructions in input source code (excluding Macro calls)
- Number of Macro calls at first level
- Number of instructions & other macro calls defined in the first level Macro call
- Total number of instructions in the final expanded source code.

Input 1: Input Source code with First level macro calls
```
MOV R
AND R
ABHISHEK
MUL 88
HALT
```

Input 2: First level macro definition “ABHISHEK”
```
MACRO
ABHISHEK
SUB R
TILAK 77
MUL R
TILAK 99
MEND
```

Input 3: Second level macro definition “TILAK”
```
MACRO
TILAK &ARG
ADD &ARG
MUL &ARG
MEND
```

Output code after first level macro expansion”ABHISHEK”:
```
MOV R
AND R
SUB R
TILAK 77
MUL R
TILAK 99
MUL 88
HALT
```

Final Expanded source code (after second level macro expansion”TILAK”):
```
MOV R
AND R
SUB R
ADD 77
MUL 77
MUL R
ADD 99
MUL 99
MUL 88
HALT
```

Statistical output:
```
Number of instructions in input source code (excluding Macro calls) = 4
Number of Macro calls at first level = 1
Number of instructions & other macro calls defined in the first level Macro call = 2, 2
Total number of instructions in the final expanded source code = 10
```
