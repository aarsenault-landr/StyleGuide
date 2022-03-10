# CMake Style Guidelines

## 1. Indentation

1. Use spaces to indent.
2. The indent size is 4 spaces.
3. Indent all code correctly in the body of `if`, `while`, `macro` and `function`.

```
if (FOO)
	some_command(...)
endif()

foreach (X ${BAR})
	some_command(...)
endforeach()

macro(MyMacro)
	some_command(...)
endmacro()

function(MyFunction)
	some_command(...)
endfunction()
```


## 2. Line breaking
1. Each line of text should be at most 120 characters long.


## 3. Function calls
1. Either write a function call on a single line, or start the arguments on a new line indented by four spaces and continue at that 4 space indent.
2. Don't break line for the end parenthesis.
3. Put one argument per line when it is followed by an assigned value.

### Arguments wrapping
<span style="color:#367E21">**Right**</span>

```
some_command(OPT1 OPT2 OPT3)
```

```
some_command(OPT1 OPT2
    OPT3 OPT4)
```

```
some_command(
    OPT1
    OPT2
    OPT3)
```

<span style="color:#EA3323">**Wrong**</span>

```
some_command(
    OPT1
    OPT2
    OPT3
)
```

### Assigned value parameters
<span style="color:#367E21">**Right**</span>

```
target_compile_definitions(${PROJECT_NAME}
    PUBLIC
    	USE_FOO=0
    	USE_BAR=1
	PUBLIC
    	USE_FOO2=0
    	USE_BAR2=1)
```

```
some_command(${PROJECT_NAME}
    BAR_NAME "BINGO"
    IS_FOO TRUE)
```
    
## 4. Upper/lower casing

1. Use lower-case for CMake keywords, functions and macro.
2. Use CamelCase for user defined functions and macros.
3. Use CamelCase with a lower-case first letter for function and macro parameters.
3. Use upper-case with underscore for variables.

### CMake functions

<span style="color:#367E21">**Right**</span>

```
add_executable(foo foo.c)
```

<span style="color:#EA3323">**Wrong**</span>

```
ADD_EXECUTABLE(bar bar.c)
```

### Variables

<span style="color:#367E21">**Right**</span>

```
set(MY_VAR "banana")
```

<span style="color:#EA3323">**Wrong**</span>

```
set(my_var "banana")
```

### Function declarations

<span style="color:#367E21">**Right**</span>

```
function(MyFunctionName inputValue)
	...
endfunction()
```

<span style="color:#EA3323">**Wrong**</span>

```
function(my_function_name INPUT_VALUE)
	...
endfunction()
```


## 5. if, elseif, else, foreach, endforeach statements
1. Add a space after `if`, `elseif` and `foreach`.
2. Always leave the `endif()` sections empty.

### If statements

<span style="color:#367E21">**Right**</span>

```
if (FOO)
	some_command(...)
elseif (BANANA)
	some_command(...)
endif()
```

<span style="color:#EA3323">**Wrong**</span>

```
if(FOO)
	some_command(...)
elseif(BANANA)
	some_command(...)
endif(FOO)
```


### Foreach statements

<span style="color:#367E21">**Right**</span>

```
foreach (X ${BAR})
    some_command(...)
endforeach()
```

<span style="color:#EA3323">**Wrong**</span>

```
foreach(X ${BAR})
    some_command(...)
endforeach()
```
