# CSCI-400 Homework #6 (Individual)

## Setting up the Repository
- **READ THIS FIRST!!**
- This README and accompanying files are contained in
  the read-only *assignment* repository --
  you will be able to pull from here, but not push.
- To get started on the assignment, first 
  carefully follow the instructions in `INSTRUCTIONS.md`.
- The basic idea is: you will first create an empty personal
  repository in the mines-csci400 organization,
  clone this assignment template repository and then push it up to your personal repository.
  Be sure to follow *all* the instructions so that you can pick up any homework updates that occur.

## Basic Instructions

- Complete each of the following Tasks.
- Submit your answers in one of the following
  formats: Markdown (`answers.md`),
  text (`answers.txt`), or LaTeX+PDF
  (`answers.tex` and `answers.pdf`).
- Note that if you choose to use LaTeX, you
  **must** submit both the TeX source `answers.tex`
  and the generated PDF `answers.pdf`.
- If you submit your solution as `answer.md`,
  one option is to use the [CodeCogs equation editor](https://www.codecogs.com/latex/eqneditor.php)
  to make nicely-formatted images such as the one below
  for any needed mathematical notation.
- Please add a .gitignore file to your local repo so that only 
  the base files and the files requested here are included in your repo.

## Rubric

- The total score is out of 100 points.
- Please make your answers clear and concise.

| Item                                        | Points |
|---------------------------------------------|--------|
| Task 1: Function type                       | 20     |
| Task 2: Type inference                      | 80     |

## Task 1

Think carefully about what the following OCaml function
is doing, and write down its type:

```
fun f x -> (f 5 (x+1)) + 1
```

## Task 2

Using the basic constraint-generation/solving approach discussed
in class, show how the Hindley-Milner type inference algorithm
would infer the type of the above OCaml function.

Recall that the algorithm does the following:
1. Rewrite the function as a new expression,
   using only (curried) lambdas and function calls
   (remember that the 2-argument OCaml operator `+`
   which performs integer addition can be used as
   a function when parenthesized, like this: `(+)`).

2. Build a list containing the above expression and its subexpressions,
   and the corresponding types.

| Expression                  | Type                  |
|-----------------------------|-----------------------|
| `fun f x -> (f 5 (x+1)) + 1` | A                     |
| ...                         | ...                   |

3. Produce a set of constraints using the above list.

```
A = ...
...
```

4. Solve the constraints to get the type for the original function.

