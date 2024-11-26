

# variadic functions
>>can take variable number of arguements (including zero arguments) of different types.

printf("hello my name is %s i'm %d years old", "laura", 23);
	-> args = ["laura", 23].
	-> args is of type va_list.
## Advantages
-Flexible function definitions.
-Simplifies handling of arbitrary inputs, like formatting functions.

## Disadvantages
-Lack of type safety:
-The caller is responsible for matching types between arguments and what the function expects.
-Passing incorrect types can lead to undefined behavior.
-Harder to debug and maintain due to implicit argument handling.

____________________
____________________________

# Macros for Argument Handling:
## va_list:
	-> Object type. [NOT A MACRO].
    -> type used to declare a variable that will hold the arguments.
	-> suitable for holding the information needed by the macros va_start/ va_end/ va_arg.
[!!] A va_list typically stores its data in the stack, but its exact location and implementation (e.g., using registers or memory) depend on the platform, compiler, and calling conventions

## va_start:
>> va_start(va_list var, parametreN);            ---<Example: va_start(ap, format);>-----
	-> va_start must br used before va_arg(), otherwise va_list variable/table will be empty.
    -> initialize argument_list for use by "va_arg()" and va_end()

## va_arg:
>> va_arg(va_list var, type of the variable);    -----<example: va_args(ap, int);>----
	-> each time va_arg is called va_arg moves to the next argument.

## va_end:
>> va_end(va_list var);                          -----<example: va_end(ap);>-----
	-> cleans up the object we initialized by calling va_start.
[!!] On many platforms, va_end is a no-op, but its use is mandatory to comply with the C standard, ensure portability, and avoid undefined behavior.

## va_copy:
>> va_copy(copy Name, original va_list var);   -----<example: va_copy(ap2, ap);>----
    -> Create a new va_list variable.
    -> Traverse or manipulate the new va_list as needed.
    -> Use va_copy to duplicate an existing va_list.

____________________
_____________________
# How Buffering Works in printf [NOT OUR ft_printf]
>> When you call printf, the data is not immediately sent to the output device (like a terminal). Instead, it is stored in a buffer:
**Data Accumulation**: Data to be printed is written into the buffer.
**Flushing**: The buffer is flushed (its contents are sent to the output) when:
	-- The buffer is full.
	-- A newline character (\n) is encountered in the output.
	-- The program explicitly flushes it (e.g., using fflush(stdout)).
	-- The program terminates normally, flushing all buffers.
