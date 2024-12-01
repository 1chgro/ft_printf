# ft_printf

## Overview

`ft_printf` is a custom implementation of the standard `printf` function in C, designed to provide a deeper understanding of formatted output. It aims to replicate the functionality of the original `printf`, supporting multiple format specifiers. This project is part of the **42 School Curriculum**.

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

---

## Function Prototype

```c
int ft_printf(const char *format, ...);
```
