## Question 1

Line 9 prints:

```js
values added: 20
```

This happens because `var result = 0;` is declared inside the `if` block, but `var` has function scope, not block scope. So `result` can still be used inside the function after it is assigned `num1 + num2`.

## Question 2

Line 13 prints:

```js
final result: 20
```

This works because `var` is function-scoped. Even though `result` was declared inside the `if` block, it is still accessible later in the same function.

## Question 3

We should avoid using `var` because it is function-scoped instead of block-scoped. This means a variable declared inside an `if` block or loop can still be accessed elsewhere in the same function, which can lead to unexpected behavior. `var` can also be redeclared, making bugs harder to catch. let and const are alternatives that should be used instead of var because there is more control.


## Question 4

Line 9 prints:

```js
values added: 20
```

This works because `result` is declared with `let` inside the `if` block, and line 9 is also inside that same block. Since `result` is being accessed within its block scope, there is no error.

## Question 5

Line 13 returns an error:

```js
ReferenceError: result is not defined
```

This happens because `let` has block scope. The variable `result` only exists inside the `if` block where it was declared. Line 13 is outside that block, so it cannot access `result`.

## Question 6

Line 9 does not print anything because the code returns an error before reaching line 9:

```js
TypeError: Assignment to constant variable.
```

This happens because `result` is declared with `const` and assigned the value `0`. A `const` variable cannot be reassigned, so this line causes an error:

```js
result = num1 + num2;
```

## Question 7

Line 13 does not print anything because the code already errors before reaching line 13.

The error is:

```js
TypeError: Assignment to constant variable.
```

Since `const result = 0;` cannot be reassigned, the function stops when it tries to run:

```js
result = num1 + num2;
```