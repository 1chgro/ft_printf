# ft_printf

## Overview

`ft_printf` is a custom implementation of the standard `printf` function in C, designed to provide a deeper understanding of formatted output. It aims to replicate the functionality of the original `printf`, supporting multiple format specifiers and additional formatting options. This project is part of the **42 School Curriculum**.

---

## Features

The `ft_printf` function supports the following format specifiers:

- `%c` : Character
- `%s` : String
- `%p` : Pointer address
- `%d` : Signed decimal integer
- `%i` : Signed integer
- `%u` : Unsigned decimal integer
- `%x` : Lowercase hexadecimal
- `%X` : Uppercase hexadecimal
- `%%` : Literal percent sign

**Additional Features**:
- Precision and width modifiers to control the output formatting.
- Manual memory management—no reliance on external libraries except `write`.
- Handles edge cases and error scenarios for robust performance.

---

## Function Prototype

```c
int ft_printf(const char *format, ...);
```
