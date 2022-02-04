# Tips for Assessment 5

## Table of Content

- [Rounding to 1 Decimal Place](#rounding-to-1-decimal-place)
- [Declaration of Random Object](#declaration-of-random-object)
- [How to Deny Casing](#how-to-deny-casing)
- [Code Structure](#code-structure)

---

## Rounding to 1 Decimal Place

1. Multiply the decimal number by `10.0 `first. For example, if you have `56.7898`, then the result should be `567.898`.

2. Use `Math.round(...)` to round the method to an integer. Continuing from the example above, `Math.round(567.89)` will give us `568`.

3. Divide the result from step 2 by 10.0. `568 / 10.0` will give us `56.8`.

4. Combining the three steps above, we will get the formula:

   ```
   Math.round(someDecimalHere * 10.0) / 10.0;
   ```

5. If you want to make it into a method, feel free to copy the code below:

   ```java
   public static double round(double input) {
       return Math.round(someDecimalHere * 10.0) / 10.0;
   }
   ```

---

## Declaration of Random Object

Remember to declare both **Scanner object** and **Random object** in main and passing it to any method that needs it using parameter.

---

## How to Deny Casing

You can deny casing by converting the user input into either all lower case first using `.toLowerCase()` or all upper case first using `.toUpperCase()`.

Example:

```java
Scanner console = new Scanner(System.in);
String userInput = console.next();
userInput = userInput.toUpperCase();

if (userInput.equals("HEY")) {
    System.out.println("Hello!");
}
```

---

## Code Structure

Ideally, your code should look like the following:

1. Have exactly **one** while loop in main.
2. Does not have a nested while loop in main.
3. Your code will calculate the **best game** and the **total guesses** in the main method.
4. You may use conditional in main to find your **best game**. Alternatively, you can use `Math.min(...)`
5. You will have 3 to 4 non-trivial methods beside main. The breakdown is as follow:

   1. Method for your Haiku
   2. Method for a single game
   3. Method for printing the statistic
   4. **[OPTIONAL]** Method for rounding to one decimal place

6. The first three methods above should be **strictly** called from main instead of being called from one another.
