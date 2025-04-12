# push_swap

This repository contains my implementation of the **push_swap** project, developed as part of the 42 School curriculum. The objective of this project is to sort a stack of integers using a limited set of operations. The challenge is to generate the shortest possible sequence of instructions that will correctly sort the given data in ascending order.

> **Note:** This project is strictly for educational purposes. Use of this code in academic submissions or by other students is prohibited by the 42 School regulations.

## Table of Contents

- [Overview](#overview)
- [Objectives](#objectives)
- [Common Instructions](#common-instructions)
- [Mandatory Part](#mandatory-part)
  - [The push_swap Program](#the-push_swap-program)
  - [Example](#example)
  - [Benchmark Requirements](#benchmark-requirements)
- [Bonus Part: The checker Program](#bonus-part-the-checker-program)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
  - [Running push_swap](#running-push_swap)
  - [Running checker](#running-checker)
- [Error Handling](#error-handling)
- [Acknowledgments](#acknowledgments)
- [Disclaimer](#disclaimer)
- [License](#license)

## Overview

The **push_swap** project is a sorting challenge based on two stacks (named **a** and **b**) and a set of predefined operations. At the start, the stack **a** contains a random list of unique integers while stack **b** is empty. The goal is to sort the integers in stack **a** (in ascending order) using the smallest number of operations possible.

## Objectives

- **Develop efficiency:** Learn to choose and implement optimal sorting algorithms.
- **Improve proficiency in C:** Work under the strict coding standards and the Norm.
- **Algorithmic Challenge:** Explore complexity analysis and decision-making when it comes to sorting.
- **Memory Management:** Ensure there are no leaks and proper resource deallocation.
- **Adherence to Standards:** Follow the project rules strictly (no global variables, error handling, correct Makefile, etc.).

For further background on sorting algorithms and their complexities, refer to [this resource](https://en.wikipedia.org/wiki/Analysis_of_algorithms).

## Common Instructions

The operations available to manipulate the stacks are:

- **sa:** Swap the first 2 elements at the top of stack **a**. (Do nothing if there is only one or no element.)
- **sb:** Swap the first 2 elements at the top of stack **b**.
- **ss:** Perform **sa** and **sb** simultaneously.
- **pa:** Take the first element at the top of **b** and put it at the top of **a** (does nothing if **b** is empty).
- **pb:** Take the first element at the top of **a** and put it at the top of **b** (does nothing if **a** is empty).
- **ra:** Rotate stack **a** upwards (the first element becomes the last).
- **rb:** Rotate stack **b** upwards.
- **rr:** Perform **ra** and **rb** simultaneously.
- **rra:** Reverse rotate stack **a** (the last element becomes the first).
- **rrb:** Reverse rotate stack **b**.
- **rrr:** Perform **rra** and **rrb** simultaneously.

For example, to sort an unsorted stack using these operations, your program must print a sequence (one instruction per line) that transforms the initial stack **a** into a sorted one.

## Mandatory Part

### The push_swap Program

- **Program Name:** `push_swap`
- **Input:** A list of integers (as command line arguments) representing stack **a**. The first argument corresponds to the top of the stack.
- **Output:** A newline-separated list of operations that will sort stack **a** in ascending order.
- **Requirements:**
  - Must be written in C.
  - Must adhere to the Norm (including bonus files if applicable).
  - Use only allowed functions: `read`, `write`, `malloc`, `free`, `exit`, and any self-coded version of `ft_printf`.
  - If using libft, its sources and Makefile should be placed in a `libft` folder.
  - The program must not print anything if no parameters are provided.

### Example

```sh
$> ./push_swap 2 1 3 6 5 8
sa
pb
pb
pb
sa
pa
pa
pa
```

In another case, if an error occurs (e.g., non-integer argument), the program prints:

```sh
$> ./push_swap 0 one 2 3
Error
```

### Benchmark Requirements

- For a minimum grade (80): Sorting 100 random numbers must require fewer than 700 operations.
- For maximum validation and bonuses: For 500 random numbers, the number of operations must not exceed 5500.

During evaluation, the number of operations produced by your program will be compared to a defined limit, and exceeding that limit will result in a grade of 0.

## Bonus Part: The checker Program

Along with push_swap, a bonus program named checker can be implemented:

- **Program Name:** `checker`
- **Input:** A list of integers (as command line arguments) representing stack a.
- **Behavior:**
  - Waits to read a series of instructions (each separated by a newline) from the standard input.
  - Executes these instructions on the provided stack.
  - If stack a is sorted in ascending order and stack b is empty after execution, print OK.
  - Otherwise, print KO.
- **Error Handling:** If any error occurs (invalid instructions, arguments, duplicates, etc.), print Error followed by a newline.

### Example:

```sh
$> ./checker 3 2 1 0
rra
pb
sa
rra
pa
OK
```

## Project Structure

```
push_swap/
├── includes/            # Header files (e.g., push_swap.h)
├── srcs/                # C source files implementing the project logic
├── libft/               # (Optional) libft sources and Makefile if used
├── tests/               # Test scripts and sample inputs for validation
├── Makefile             # Makefile with at least: NAME, all, clean, fclean, re (and bonus if applicable)
└── README.md            # This file
```

## Installation

1. **Clone the Repository:**

   ```sh
   git clone https://github.com/yourusername/push_swap.git
   cd push_swap
   ```

2. **Build the Project:**

   Use the provided Makefile to compile the source files:

   ```sh
   make
   ```

   This will compile your code into the push_swap (and optionally checker) executable(s).

## Usage

### Running push_swap

**Sorting a Stack:**

```sh
./push_swap 4 67 3 87 23
```

The program outputs a sequence of operations (one per line) that sorts the stack.

**Handling Errors:**

If any argument is invalid (non-integer, duplicates, out-of-range), the program will print:

```sh
Error
```

### Running checker

If you have implemented the bonus checker, you can validate a sequence of operations as follows:

```sh
./checker 3 2 1 0
```

Then provide the operations via standard input. For example:

```sh
rra
pb
sa
rra
pa
```

After entering the operations (pressing Enter after each), the program will evaluate and print either:

- **OK** if the stack is sorted and stack b is empty.
- **KO** if it is not.
- **Error** if an invalid instruction or argument is detected.

## Error Handling

- **No Parameters:** The program should display nothing and exit.
- **Invalid Input:** In cases where non-integer inputs, out-of-bound values, or duplicate numbers are provided, the program will output Error followed by a newline on the standard error.
- **Instruction Validation:** Both push_swap and checker must handle any error related to instruction input.

## Acknowledgments

- Many thanks to the 42 community, mentors, and fellow students for their support and feedback.
- Special recognition to the authors of various open-source projects for providing valuable insights into algorithm optimization and C programming.

## Disclaimer

**IMPORTANT**:
This project was developed solely as a part of the educational curriculum at 42 School. The code in this repository is published only for demonstration purposes to showcase my programming and algorithm design skills.

**Academic Integrity Notice**:
It is strictly prohibited to use or share this code as your own work in any academic submissions at 42 School. Any misuse will be considered a violation of 42 School's academic policies.

## License

This repository is licensed under the Creative Commons - NonCommercial-NoDerivatives (CC BY-NC-ND 4.0) license. You are free to share the repository as long as you:

- Provide appropriate credit.
- Do not use it for commercial purposes.
- Do not modify, transform, or build upon the material.

For further details, please refer to the CC BY-NC-ND 4.0 license documentation.

Developed with dedication and in strict adherence to the high standards of 42 School.
