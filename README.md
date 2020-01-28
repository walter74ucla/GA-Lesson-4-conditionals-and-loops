
# WDI

<hr>
Title: Conditionals and Loops<br>
Type: Lesson<br>
Duration: 1.5 hrs<br>
Creator: GA Instruction Team <br>
Updated by: Alex White <br>
Topics: Intro to Conditionals & Loops <br>
<hr>

# But first! 
Some quick but important notes on [Code Quality](https://git.generalassemb.ly/gist/alexw/c791b68224f2adfc4fd69de65a5db45e)

# Intro to Conditionals & Loops

### Lesson Objectives
_After this lesson, students will be able to:_

- Explain why we would use 'control flow' in our programs
- Write a simple if statement
- Write an if / else statement
- Write a for loop with a conditional inside

<br>
<hr>

# Control Flow

Control Flow is the order in which individual statements or instructions are executed.

:door: **Example**

You want to enter a house. You have to walk through the door to get inside. Based on whether that front door is open or closed, locked or unlocked, you may have to take a different step to get inside the house.

Control Flow lets you specify **when** and **which** lines of code get executed

:door: **Example**

- When the door is open: I walk inside.

- When the door is closed:
I determine if it's locked.

There are three forms of Control Flow:

- **Conditionals** - skip lines of code
- **Loops** - repeat lines of code
- **Functions** - save and later deploy lines of code

For now, let's focus on *conditionals*

# Conditionals

We can set up a branching tree-like structure and control the flow of our code. Though, our code will look less like a tree and more like:
```js
if (BOOLEAN EXPRESSION){
  // run this code
};
```
If the boolean expression within our condition is `true`, a branch will execute. If it is `false`, it will not execute. This is an example of `control flow`.

![control flow wd40](https://i.imgur.com/v4W1xwD.png)

Before we write in some control flow, let's take a closer look at the boolean logic that will drive our conditionals.

<br>
<hr>

# Booleans

* Booleans allow us to set `true` and `false` values. With true and false values, we can control the flow of our programs.

:door: **Example**

The door to our house from earlier, we could create a variable for `door_open` and its value can be set to either true or false. If it's true, we can run a line of code to walk through the door. If the `door_open` variable is false, then we would have to run a different line of code to figure out what to do next.

:books: **History Lesson**

 Boolean logic is a type of logic that deals with binary values, and is named after George Boole who invented it.

<hr>

### Let's Practice :computer:

1) Create a file called `conditional_practice.js` in your folder


:elephant: **Reminder** <br>
Use `cd` to change directories and `atom filename` to open a file with Atom.

2) In your terminal, open the file in your browser in order to run the code that is inside your file.

3) Let's declare some variables with Boolean values.

```js
const sunny = true;
const temp = 76;
```

4) Check the values of your variables by logging them and running your code.

:elephant: **Reminder** <br>
- To log your code:
`console.log(variable_name or "message")`
<br>


<hr>

## Not
- `!` **not** sometimes called a 'bang': changes Boolean value to its opposite.

### Let's Practice :computer:

Uh oh! There are cloudy skies :cloud::cloud::cloud:

1) Change the value of your `sunny` variable to `!true`. Log `sunny` and run your code to see the result.

2) Using a bang, change the value of `notSunny` to result in true.

3) Add the following code to your file to test out:

```js
let toggle = true;
console.log("this is toggle " + toggle);
toggle = !toggle;
console.log("this is toggle " + toggle);
```
**Look at that!** :eyes: <br>
You can reassign values with a variable's own value (a little bit of a brain bender)!

<hr>

## Truthiness

**All** values in JavaScript have an implicit 'truthiness'. They can be evaluated as either true or false. In effect, every value in Javascript is converted into a Boolean when it is checked as an expression of truth.

##### All of the following become false when converted to a Boolean

- `false`
- `0`
- `""` (empty string)
- `NaN`
- `null`
- `undefined`

<br>

### Let's Practice :computer:

JavaScript has a built-way to convert things to Booleans: `Boolean()`. Put the following inside the parenthesis of `console.log()` to see the result.

```js
Boolean("");
Boolean(null);
Boolean(0);
```
<br>


##### All other values are implicitly true

### Let's Practice :computer:

```js
Boolean("hi");
Boolean(1);
Boolean(true);
```

<br>  
<hr>


There is a simple way of verifying the thruthyness or falsiness of a value. When you add `!` in front of a value, the returned value will be the inverse of the value in a boolean. So if you add two `!` then you'll get the boolean value of the original one:

```javascript
!!1
//=> true

!!0
//=> false

!!-1
//=> true

!![]
//=> true

!!{}
//=> true

!!null
//=> false

!!""
//=> false
```

## Equality operators

`==`, `!=`, `===`, `!==`

Equality operators are **not** the same as the _assignment_ operator `=`

- `==` **equality**: compares left-hand and right-hand and checks if they are the same. Returns a Boolean value.
- `!=` **inequality**: compares left-hand and right-hand and check if they are not the same. Returns a Boolean value.

```js
true == true
=> true
```

```js
true == false
=> false
```

&#x1F535; **Examples**

Booleans:

```js
false == false
=> true
```

```js
true != true;
=> false
```

```js
true == !true
=> false
```

Numbers:

```js
1 == 1
=> true
```

And with strings:

```js
"hello world" == "hello world"
=> true
```

### Strict

- `===` **strict equality**: same as equality, but does not coerce
- `!==` **strict inequality**: same as inequality, but does not coerce

```js
5 == '5';
=> true
```

```js
5 === '5';
=> false
```

### Let's Practice :computer:

1) Is the number 1 equivalent to the number 1?

2) Is the string "beans" equivalent to the string "soup"?

3) Is (5 + 5 * 3) equivalent to ((5 + 5) * 3)?

4) Is 9 strictly unequal to false?

5) Is NaN equivalent to NaN?

<hr>


## Comparison Operators

[Comparisons](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators) in JavaScript can be made using `<`, `>`, `<=` and `>=`. These work for both strings and numbers. This is both useful, and can be the source of frustration for some developers, since most languages do not implicitly convert strings to numbers the way that JavaScript does.

```javascript
"A" > "a"
//=> false

"b" > "a"
//=> true

12 > "12"
//=> false

12 >= "12"
//=> true
```


```
5 > 2;
=> true
```

```
5 <= 5;
=> true
```

- strings are compared by alphabetical precedence

```js
`'a' > 'b'`;
=> false
```

```js
`'z' > 'abc'`
=> true
```


### Let's Practice :computer:

1) Is -10 greater than or equal to -100?

2) Is Infinity greater than or equal to -Infinity?

3) Is "McDonald's" greater than "Burger King?"

<br>
<hr>

## Logical operators

`&&`, `||`

- `&&` **and**: evaluates to `true` if both sides are true. It does not check for equality! Rather, **and** evaluates the truth of the statement, and will return the value of one of the operands.

```js
true && true
=> true
```

```js
false && false
=> false
```

In these examples, each side is the same (they are equivalent), but in this case, both sides do not both evaluate to `true`.
If an `&&` statement begins with `false`, it automatically evaluates to false.
Both sides must evaluate to true to && to result in true.

```js
true && false
=> false
```

```js
const a = true;
const b = false;

a && b
=> false
```

<br>

- `||` **or**: evaluates to true if _either_ side is true.

```js
true || false
=> true
```

```js
false || false
=> false
```

```js
const x = false
const y = false

x || y
=> true
```


### Boolean order of evaluation

1. `>, <, >=, <=`
2. `==, ===`
3. `&&`
4. `||`

<br>

### Let's Practice :computer:

Try to guess the result before you check it. If it is not what you expected, try to find out why not

* Check: `!false && true`
* Check: `false || true`

```js
const a = true;
const b = false;
```
* Check: `a && a == b`
* Check: `!true || !false && !false`
* Check: `8 > 1 && true || false`

<br>
<hr>



## IF Statements

Basic if statement

```
if (BOOLEAN EXPRESSION) {
  // run this code
}
```

The curly braces denote a `block`. The `block` will run if the `BOOLEAN EXPRESSION` evaluates to `true`.

**Example**

```js
constnumber = 10;

if (number === 10){
  console.log("The number is 10!")
}
```

### Let's Practice Together :computer:

#### Reporting for Duty
_Strings as conditionals_

1) Make a variable called `name` and save a name to it.

3) Log the variable to confirm what you've stored.<br>
`console.log(name);`

4)Add a basic **if statement** to add control flow depending on the input.

```
if (input === "Kermit") {
  console.log("Hi ho! Kermit the frog here.");
}
```

- If the input name is `Kermit`, the code is run. Otherwise, the code never runs.

- Control flow with conditionals means that not every line is run. The code in front of us is separate from the process going on behind the scenes.

- Lines of code will be excluded during execution in order to take us on a particular 'branch'

- Which lines are excluded depends on Boolean values, and whether expressions evaluate to `true` or `false`

<br>
<hr>

#### Have a Drink
_Numbers as conditionals_

```js
constage = 21;

if (age >= 21) {
    console.log ('You are allowed to buy beer');
}
```

#### Oddball
_Modulus as conditionals_

`%`

Check for odd numbers:
```js
if (5 % 2 == 0) {
    console.log('number is even);
}
```

**Let's add an `else` to our `if` statement**

### If / else

```js
if (5 % 2 ==0) {
    console.log('Number is even');
} else {
    console.log('Number is odd');
}
```


<hr>

# LOOPS: Conditionals within loops

:elephant: **Reminder** <br>

#### For Loop

```js
for (initial expression; condition; increment expression) {
    Code that will be executed
}
```

**Example:**
Looping through an array called `cars` and log each car in the array.

```js
cars = ["Chevy", "Audi", "Nissan", "Toyota", "Lexus", "Tesla"];

for (let i = 0; i < cars.length; i++) {
    console.log(cars[i]);
}
```

**note** We can use this method to iterate over an array! More on that this afternoon. 

#### Conditionals within a for loop

- Only runs code if conditions are met

**Example:**
For the numbers 1 through 10, if the number is an even number, let's print a message "even number", otherwise, let's print a message "odd number"

```
for (let i = 1; i < 11; i++) {
  if (i % 2 === 0){
    console.log(i + " is an even number");
  } else {
     console.log(i + " is an odd number");
  }
}
```

## Further Reading

- [Mozilla - Control Flow](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)
