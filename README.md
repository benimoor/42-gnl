# get_next_line

get_next_line is a function developed as part of the 42 École curriculum. The function reads a line from a file descriptor (FD) and returns it without the newline character.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Function Prototype](#function-prototype)
- [Return Value](#return-value)
- [Performance](#performance)
- [Contact](#contact)

## Introduction

The get_next_line function reads a line from a given file descriptor and returns it without the newline character. It is a useful utility function for reading text from files, especially when dealing with large files or dynamic input.

## Features

- Read a line from a file descriptor.
- Handle reading from multiple file descriptors simultaneously (if implemented).

## Installation

To use the get_next_line function in your project, follow these steps:

1. **Clone the repository**
   ```
   git clone https://github.com/your_username/get_next_line.git
   cd get_next_line

    Include the header file

   #include "get_next_line.h"

Compile your project with the get_next_line function

    gcc -Wall -Wextra -Werror -D BUFFER_SIZE=32 your_source_files.c get_next_line.c get_next_line_utils.c -o your_executable

## Usage

To use the get_next_line function in your project, call it with a file descriptor (FD) as the argument:
```
#include "get_next_line.h"

int main(void)
{
    int fd;
    char *line;

    fd = open("example.txt", O_RDONLY);
    while (get_next_line(fd, &line) > 0)
    {
        printf("%s\n", line);
        free(line);
    }
    close(fd);
    return (0);
}
```
## Function Prototype
```
char *get_next_line(int fd, char **line);
```
## Return Value
The get_next_line function returns the next line read from the file descriptor fd without the newline character. It returns NULL if there are no more lines to read or if an error occurs.
Performance

## Performance
The performance of the get_next_line function depends on the value of BUFFER_SIZE and the size of the input. Adjusting BUFFER_SIZE can optimize performance for different use cases, balancing memory consumption and read efficiency.

## Contact
Erik Grigoryan - ergrigor@student.42yerevan.am
