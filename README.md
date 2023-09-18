# Get Next Line

This repository contains the implementation of the Get Next Line project, a fundamental project at 42 School. The project focuses on reading and managing input from file descriptors and dealing with multiple file descriptors.

## Project Description

The Get Next Line project involves creating a function that reads a line from a file descriptor, either from a file or from standard input. The function must handle multiple file descriptors and return the line read up to a newline character.

## Usage

To use this project, follow these steps:

1. Clone the repository or download the relevant files.
2. Include the `get_next_line.c` file in your project.
3. Call the `get_next_line` function to read lines from file descriptors.

Example usage:
```c
#include "get_next_line.h"

int main(void)
{
    int fd;
    char *line;

    fd = open("example.txt", O_RDONLY);
    if (fd == -1)
        return -1;

    while (get_next_line(fd, &line) > 0)
    {
        printf("%s\n", line);
        free(line);
    }

    close(fd);
    return 0;
}
```

## Code Structure

The `get_next_line` function is the core of the project, responsible for reading lines from the given file descriptor. It is defined in the `get_next_line.c` file. The function returns `1` if a line has been read, `0` if the end of the file has been reached, and `-1` in case of an error.

## Header File

The `get_next_line.h` header file contains the function prototype and any necessary included libraries and defines.

## Supporting Functions

The project may also include supporting functions and helper utilities to manage memory, handle file descriptors, and facilitate the implementation of `get_next_line`.

## Documentation

For more detailed information about the project, including its requirements and specifics, please refer to the official project documentation and subject provided by 42 School.
