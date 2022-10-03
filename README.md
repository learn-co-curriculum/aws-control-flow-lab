# Control Flow Lab

## Learning Goals

* Practice writing `if...else if...else` statements.
* Practice working with the ternary operator.
* Practice writing `switch` statements.

## Introduction

You have been hired as a contractor for Scuber, a burgeoning startup that helps
busy parents transport their children to and from all of their activities on
scooters.

Scuber's drivers charge their passengers a variable amount based on how far
they need to travel. Modify the `index.js` file to make sure that Scuber's drivers
are properly telling their passengers how much the ride will cost.

## Read the Tests 

As always, this lab includes tests for you to check your work as you go. 
First, install the required dependencies with `npm i` and run an initial test with
`npm test` to see what tasks you need to accomplish. 

After running the `npm test` command in your terminal, you should see all of them will
fail. This is expected, of course, since we haven't written anything yet. Let's 
look at the first test together. It should say: 

```sh
1) index.js
      scuberGreetingForFeet()
        gives customers a free sample if the ride is less than or equal to 400 feet:
        AssertionError: expected undefined to equal 'This one is on me!'
```

We can see that this test is for the `scuberGreetingForFeet()` function. It says that
_if_ a ride is less than or equal to 400 feet, the function should return the string
`'This one is on me!'`. 

We will tackle the details of functions in depth later on. For now, here is a quick
example of how functions are declared: 

```js
function addFive(someNumber) {
  //Everything I want my function to do I put inside these curly braces
  //In this example, let's say I want my function, addFive, to add 5 to
  //any number I pass in (someNumber), but only IF the number is greater
  //than zero:
  let result
  if (someNumber > 0) {
    result = someNumber + 5;
  }
  //at the end, if I want my function to return something, I need to state it:
  return result
}
```

Now that we've briefly learned about functions, let's open the `index.js` file. 
You'll see there are three functions declared for you. Let's focus on `scuberGreetingForFeet()`
to pass the first test. We can see that the function has a variable inside its
parentheses `(feet)`. This is called a parameter, we'll learn more about it in
the future. 

For now, all we need to know is that is the variable we will compare against in
our statements. As an example, let's pass the first test together. It asked us
to say `'This one is on me!'` _if_ the ride is less than 400 feet. 

Or, in other words: 

```js
function scuberGreetingForFeet(feet){
  if(feet < 400) {
    // ... say 'This one is on me!'
  }
}
```

How do we say 'This one is on me!'? In the function example given earlier, we
learned about the `return` statement. Let's do something similar. Above the `if`
statement, declare a variable called `driverGreeting` with no value. We will 
set the value accordingly inside the `if...else`'s. Don't forget to return
the variable below the `if...else`. 


```js
function scuberGreetingForFeet(feet){
  let driverGreeting

  if(feet < 400) {
    driverGreeting = 'This one is on me!';
  }

  return driverGreeting
}
```

When you run your test now, the first one should pass! 

## Instructions

As you saw, there are three functions that have been declared for you. Again, we will 
learn about functions in more detail later on, so for now all you need to focus on is 
writing `if...else`, ternary, and `switch` statements within these given functions.

Below is a brief summary of what each function is expected to do and which selection
flow you should use. Remember to also read the test outputs when running `npm test` 
to find out what each function should do exactly for you to pass them.

* `scuberGreetingForFeet()` — Use `if` and `else if` statements to return the
correct greeting based on the distance the passenger desires to travel.
* `ternaryCheckCity()` — Use a ternary operator to return the correct response
based on the desired destination of the passenger.
* `switchOnCharmFromTip()` — Use a `switch` statement to return a different
response based on the generosity of the passenger's tip.

***NOTE***: Beware a gotcha! In JavaScript, you cannot express the concept of
'between' in the following way:

```js
2 < 5 < 4
// => true
```

It seems like that expression should evaluate to `false` because `5` is not less
than `4`. However, we're forgetting about the order of operations — let's
think about how the JavaScript engine evaluates that expression. First, the
engine compares `2 < 5`, which evaluates to `true`. At that point, it's as
though the value `true` has replaced `2 < 5` in the expression, resulting in
`true < 4`. The engine sees that we're trying to compare a non-number (`true`)
against a number (`4`), and under the hood it converts `true` into a number:

```js
Number(true);
// => 1
```

That leaves us with `1 < 4`, which the JavaScript engine correctly evaluates to
`true`. Can you figure out how to properly evaluate whether `5` is greater than
`2` **AND** `5` is less than `4` using logical operators? Ponder that as you work
through the assignment.

Good luck!

## Submission 

Once all your tests pass, submit your assignment on Canvas. 

> Don't quite remember how to submit an assignment? Refer back to the very first 
> assignment's submission instructions.