# DevTools Part 2

## Question 1

The bug was that the input values from the webpage were being treated as strings instead of numbers.

The code used:

```js
document.getElementById("num1").value
document.getElementById("num2").value
```

The `.value` property returns a string. So when the user entered `2` and `3`, JavaScript treated them as `"2"` and `"3"`.

Then this line:

```js
let result = num1 + num2;
```

performed string concatenation instead of numeric addition. That means:

```js
"2" + "3"
```

became:

```js
"23"
```

instead of:

```js
5
```

## Question 2

I would fix it by converting the input values into numbers before passing them into `calculateSum()`.

The fixed code should be:

```js
function printSum() {
    debugger;
    let num1 = Number(document.getElementById("num1").value);
    let num2 = Number(document.getElementById("num2").value);
    document.getElementById("sum").innerHTML = "Sum: " + calculateSum(num1, num2);
}
```

This works because `Number(...)` converts the input strings into numbers first. Then when `calculateSum(num1, num2)` runs, `num1 + num2` performs numeric addition instead of string concatenation.