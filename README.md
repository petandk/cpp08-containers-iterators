*This project has been created as part of the 42 curriculum by rmanzana*

# C++ Module 08 — Templated containers, iterators, algorithms

## Description

Ninth module of the 42 C++ piscine. It is an introduction to the **containers, iterators and algorithms** of the C++ standard library (STL): instead of managing arrays and loops by hand, the exercises use `std::vector`, `std::list`, `std::stack`, `std::find`, `std::sort` and iterators, and combine them with templates.

All the code follows the **C++98** standard and compiles with `c++ -Wall -Wextra -Werror -std=c++98`.

## Exercises

| Exercise | Program | Description |
|---|---|---|
| `ex00` — Easy find | `easyfind` | A function template `easyfind(container, value)` that finds the first occurrence of an integer in any container of integers using `std::find`. It returns the position of the element and throws `std::out_of_range` if it is not found. Tested with `std::vector`, `std::list` and `std::deque`. |
| `ex01` — Span | `span` | A `Span` class that stores up to N integers in a `std::vector` and computes the **shortest span** (smallest distance between any two numbers) and the **longest span**. Both sort a copy of the numbers with `std::sort`, after which the shortest span is between two adjacent elements and the longest is `last - first`. Numbers can be added one by one, or a whole range at once through a member function template that takes **any pair of iterators**. Exceptions are thrown when the span is full or has fewer than 2 numbers. Tested with 10,000+ numbers. |
| `ex02` — Mutated abomination | `mutant` | `MutantStack<T>` inherits from `std::stack<T>` and makes it **iterable**: `std::stack` is an adapter that hides its underlying container (`c`, a protected member), so `MutantStack` exposes that container's `iterator` type and its `begin()` / `end()`. Its output is compared with a `std::list` doing the same operations. |

## Key concepts

- **STL containers:** sequence containers (`std::vector`, `std::list`, `std::deque`) and container adapters (`std::stack`).
- **Iterators** as a common interface to traverse any container.
- **STL algorithms:** `std::find`, `std::sort`, `std::distance`, …
- **`typename`** to refer to dependent types inside templates (`typename T::const_iterator`).
- **Member function templates** that accept any iterator type.
- **Extending** a standard class through inheritance and its `protected` members.

## Instructions

Each exercise has its own `Makefile`:

```bash
cd ex01
make
./span
```

`make clean`, `make fclean` and `make re` are available in every exercise.

## Resources

- [cplusplus.com — Containers](https://cplusplus.com/reference/stl/)
- [cplusplus.com — `<algorithm>`](https://cplusplus.com/reference/algorithm/)
- [cppreference — `std::stack`](https://en.cppreference.com/w/cpp/container/stack)
- [cppreference — Iterator library](https://en.cppreference.com/w/cpp/iterator)
- [LearnCpp.com — Introduction to iterators](https://www.learncpp.com/cpp-tutorial/introduction-to-iterators/)
