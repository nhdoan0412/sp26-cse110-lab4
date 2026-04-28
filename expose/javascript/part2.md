# Part 2: A Little More of a Challenge

## Question 1

At line 12, the code prints:

```js
3
```

This happens because `i` is declared with `var` inside the `for` loop. Since `var` has function scope, `i` is still accessible after the loop ends. The loop stops when `i` becomes `3`, because `prices.length` is also `3`.

## Question 2

At line 13, the code prints:

```js
150
```

This happens because `discountedPrice` is declared with `var` inside the `for` loop. Since `var` has function scope, it is still accessible after the loop ends. After the last iteration, `discountedPrice` stores the discounted value of `300`, which is:

```js
300 * (1 - 0.5) = 150
```

## Question 3

At line 14, the code prints:

```js
150
```

This happens because `finalPrice` is declared with `var` near the top of the function, so it is function-scoped. During each loop iteration, `finalPrice` is updated. After the final iteration, the last value assigned to `finalPrice` is the discounted price of `300`, which is `150`.

## Question 4

This function returns:

```js
[50, 100, 150]
```

The function loops through the `prices` array `[100, 200, 300]` and applies a `0.5` discount to each price. So the calculations are:

```js
100 * (1 - 0.5) = 50
200 * (1 - 0.5) = 100
300 * (1 - 0.5) = 150
```

Each final price is pushed into the `discounted` array, so the returned array is `[50, 100, 150]`.

## Question 5

At line 12, the code causes an error:

```js
ReferenceError: i is not defined
```

This happens because `i` is declared with `let` inside the `for` loop. Unlike `var`, `let` has block scope, so `i` only exists inside the `for` loop block. Since line 12 is outside the loop, it cannot access `i`.

## Question 6

At line 13, the code causes an error:

```js
ReferenceError: discountedPrice is not defined
```

This happens because `discountedPrice` is declared with `let` inside the `for` loop block. Since `let` has block scope, `discountedPrice` only exists inside the loop. Line 13 is outside the loop, so it cannot access `discountedPrice`.

## Question 7

At line 14, the code prints:

```js
150
```

This happens because `finalPrice` is declared with `let` near the top of the function, outside the `for` loop. Since line 14 is still inside the same function scope where `finalPrice` was declared, it can access the variable. After the final loop iteration, `finalPrice` stores the discounted value of `300`, which is `150`.

## Question 8

This function returns:

```js
[50, 100, 150]
```

The function applies a `0.5` discount to each price in `[100, 200, 300]`. The variable `discounted` is declared with `let` at the top of the function, so it is accessible throughout the function. Each calculated `finalPrice` is pushed into the `discounted` array.

## Question 9

At line 11, the code causes an error:

```js
ReferenceError: i is not defined
```

This happens because `i` is declared with `let` inside the `for` loop. Since `let` has block scope, `i` only exists inside the loop block. Line 11 is outside the loop, so it cannot access `i`.

## Question 10

At line 12, the code prints:

```js
3
```

This happens because `length` is declared with `const` near the top of the function. Since line 12 is inside the same function scope, it can access `length`. The value is `3` because the `prices` array has three elements: `[100, 200, 300]`.

## Question 11

This function returns:

```js
[50, 100, 150]
```

The function creates an empty array called `discounted`, then loops through the three prices. For each price, it calculates the discounted price using:

```js
prices[i] * (1 - discount)
```

With a `0.5` discount, the calculated values are `50`, `100`, and `150`. Even though `discounted` is declared with `const`, the array itself can still be modified with `.push()`. `const` only prevents reassigning the variable to a different array.

## Question 12
## Data Types

### Accessing the value of the `name` property in the `student` object

```js
student.name
```

### Accessing the value of the `Grad Year` property in the `student` object

```js
student['Grad Year']
```

Because the property name has a space, we need to use bracket notation instead of dot notation.

### Calling the function for the `greeting` property in the `student` object

```js
student.greeting()
```

### Accessing the `name` property of the object in the `Favorite Teacher` property in `student`

```js
student['Favorite Teacher'].name
```

Because `Favorite Teacher` has a space, we use bracket notation first. Then we can use `.name` to access the nested teacher name.

### Accessing index zero in the array of the `courseLoad` property of the `student` object

```js
student.courseLoad[0]
```

# Basic Operators & Type Conversion

## Question 13: Arithmetic

### A. `'3' + 2`

Output:

```js
'32'
```

Explanation: Since one value is a string and the operator is `+`, JavaScript converts `2` into a string and concatenates them.

### B. `'3' - 2`

Output:

```js
1
```

Explanation: The `-` operator only works as numeric subtraction, so JavaScript converts `'3'` into the number `3`.

### C. `3 + null`

Output:

```js
3
```

Explanation: In numeric conversion, `null` becomes `0`, so this becomes `3 + 0`.

### D. `'3' + null`

Output:

```js
'3null'
```

Explanation: Since one value is a string and the operator is `+`, JavaScript converts `null` into the string `'null'` and concatenates.

### E. `true + 3`

Output:

```js
4
```

Explanation: In numeric conversion, `true` becomes `1`, so this becomes `1 + 3`.

### F. `false + null`

Output:

```js
0
```

Explanation: In numeric conversion, `false` becomes `0` and `null` also becomes `0`, so this becomes `0 + 0`.

### G. `'3' + undefined`

Output:

```js
'3undefined'
```

Explanation: Since one value is a string and the operator is `+`, JavaScript converts `undefined` into the string `'undefined'` and concatenates.

### H. `'3' - undefined`

Output:

```js
NaN
```

Explanation: The `-` operator tries to convert both values into numbers. `'3'` becomes `3`, but `undefined` becomes `NaN`, so the result is `NaN`.

## Question 14: Comparison

### A. `'2' > 1`

Output:

```js
true
```

Explanation: JavaScript converts `'2'` into the number `2`, so this becomes `2 > 1`.

### B. `'2' < '12'`

Output:

```js
false
```

Explanation: Both values are strings, so JavaScript compares them lexicographically. Since `'2'` comes after `'1'`, the result is false.

### C. `2 == '2'`

Output:

```js
true
```

Explanation: The `==` operator allows type conversion. JavaScript converts `'2'` into the number `2`, so the values are equal.

### D. `2 === '2'`

Output:

```js
false
```

Explanation: The `===` operator does not allow type conversion. One value is a number and the other is a string, so they are not strictly equal.

### E. `true == 2`

Output:

```js
false
```

Explanation: The `==` operator converts `true` into `1`. Since `1 == 2` is false, the result is false.

### F. `true === Boolean(2)`

Output:

```js
true
```

Explanation: `Boolean(2)` becomes `true` because any nonzero number is truthy. Then `true === true` is true.

## Question 15

The `==` operator checks equality after allowing type conversion. This means JavaScript may convert one or both values before comparing them. For example, `2 == '2'` is true because the string `'2'` is converted into the number `2`.

The `===` operator checks strict equality without type conversion. The values must have the same type and the same value. For example, `2 === '2'` is false because one is a number and the other is a string.

In general, `===` is safer and preferred because it avoids unexpected type conversion bugs.

## Question 17

The result is:

```js
[2, 4, 6]
```

The function call is:

```js
modifyArray([1, 2, 3], doSomething)
```

The first argument is the array `[1, 2, 3]`. The second argument is the function `doSomething`, which takes a number and returns that number multiplied by `2`.

Inside `modifyArray`, the loop goes through each element in the array and calls the callback function on it:

```js
callback(array[i])
```

So the steps are:

```js
doSomething(1) // returns 2
doSomething(2) // returns 4
doSomething(3) // returns 6
```

Each returned value is pushed into `newArr`, so the final returned array is:

```js
[2, 4, 6]
```

## Question 19

The output is:

```js
1
4
3
2
```

Explanation: First, `printNums()` runs normally from top to bottom. It immediately prints `1`, then schedules `2` to print after `1000` milliseconds, then schedules `3` to print after `0` milliseconds. Even though the delay for `3` is `0`, it still waits until the current synchronous code finishes. Then the function immediately prints `4`.

After the synchronous code finishes, the `setTimeout` with `0` milliseconds runs, so it prints `3`. Finally, after about one second, the `setTimeout` with `1000` milliseconds runs, so it prints `2`.