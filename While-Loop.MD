# While Loop

A while-loop acts like an `if(...) {...}` structure. However, instead of running the code inside the curly brackets once, it will keep running as long as the _conditional statement_ inside the conditional evaluates to `true`.

---

## Table of Content

- [While Loop Template](#while-loop-template)
- [Example of While Loop](#example-of-while-loop)
- [While Loop Priming](#while-loop-priming)

---

## While Loop Template

```java
while (/*conditional statement here*/) {
    // your code here
}
```

---

## Example of While Loop

```java
int number = 4;
while (number < 7) {
    System.out.println(number);
    number++;
}
```

_Line Execution Log:_

```
Line 1 (number = 4)
Line 2 (while 4 < 7) -> True
Line 3
Line 4 (number = 5)

Line 2 (while 5 < 7) -> True
Line 3
LIne 4 (number = 6)

Line 2 (while 6 < 7) -> True
Line 3
LIne 4 (number = 7)

Line 2 (while 7 < 7) -> false
Line 5
```

_Output:_

```
4
5
6
```

---

## While Loop Priming

Sometimes, your while-loop conditional statement involves a variable which value is updated inside the loop itself. _Example:_

```java
Scanner console = new Scanner(System.in);
while (userInputNumber < 10) {
    int userInputNumber = console.nextInt();
    for (int i = 1; i <= userInputNumber; i++) {
        System.out.println("Hello!");
    }
}
```

Notice that I am checking for the value of `int userInputNumber` in my conditional, but the variable `int userInputNumber` is declared inside the loop.

When Java initially reads the code, line 2 of the code above is going to be executed first before line 3. This means that Java is trying to evaluate the conditional involving `userInputNumber` when it has not been declared yet.

To avoid this, we should declare our `int userInputNumber` before the start of the loop!

```java
Scanner console = new Scanner(System.in);
int userInputNumber = ?
while (userInputNumber < 10) {
    int userInputNumber = console.nextInt();
    for (int i = 1; i <= userInputNumber; i++) {
        System.out.println("Hello!");
    }
}
```

Key observations:

1. Since we already declare our `int userInputNumber` on line 2, we should avoid re-declaring the same variable again on line 4. We can avoid this by removing the keyword `int` before `userInputNumber`.

2. What should we set the value of `int userInputNumber` on line 2 to?

   1. We should not set it to `console.nextInt()` because we are going to "waste" a user input by replacing it immediately with another user input on line 4 before doing anything with the initial user input.

   2. We should set the value into any number that allows us to get into our while-loop for the first time. In this case, we can input any number between `-infinity` up to `9` so that the conditional statement `userInputNumber < 10` is `true` and we can enter our loop for the first time!

Final code:

```java
Scanner console = new Scanner(System.in);
int userInputNumber = 7;
while (userInputNumber < 10) {
    userInputNumber = console.nextInt();
    for (int i = 1; i <= userInputNumber; i++) {
        System.out.println("Hello!");
    }
}
```
