# Random Object

For Checkpoint 5 and Take-Home Assessment 5, you will need to generate Random numbers! To do that, you will need the help of a Random objet.

---

## Table of Content

- [How to Use Random Object I](#how-to-use-random-object-i)
- [How to Use Random Object II](#how-to-use-random-object-ii)
- [Seeding Random Object](#seeding-random-object)

---

## How to Use Random Object I

Here are the steps to use Random object in Java:

1. Add `import java.util.*;` before your class header
2. Declare your Random object (like how you would declare a Scanner object):

   ```java
   Random someVariableNameHere = new Random();
   ```

3. Generate a random number using `.nextInt(lowerBound, upperBound)`. Here is an example:

   ```java
   Random myRandomObject = new Random();
   myRandomObjectl.nextInt(5, 20);
   ```

   The second line above generates a Random number in the range of 5 - 19 inclusive.

   > Keep in mind that the _lower bound_ that you include inside the `.nextInt(lowerBound, upperBound)` is **inclusive (included)**, but the _upper bound_ is **exclusive (not included)**.

   Example:

   - If you want to generate a random number from 5, you want to write 5 as the first `.nextInt(...)` parameter. Since the lower bound is **inclusive**, writing 5 as the lower bound means Java may also generate 5 as your random number.

     ```java
     Random myRandomObject = new Random();
     myRandomObject.nextInt(5, ...)
     ```

   - If you want to generate a random number where 19 is the **highest possible included number**, you want to write 20 as the second`.nextInt(...)` parameter because the Java won't include 20 **(exclusive)** and only generates until 19.

     ```java
      Random myRandomObject = new Random();
     `myRandomObject.nextInt(..., 20)
     ```

   - Combining the two examples above, if we want to generate a random number from 5 - 19 (where 5 and 19 are included), we can write them as:

     ```java
      Random myRandomObject = new Random();
     `myRandomObject.nextInt(5, 20)
     ```

4. Save the generated random number into an `int` variable so that you can use it for something else later!

   ```java
      Random myRandomObject = new Random();
      int someRandomNumber = myRandomObject.nextInt(5, 20);
   ```

---

## How to use Random Object II

Here are another version of how you can generate random numbers!

1. Add `import java.util.*;` before your class header

2. Declare your Random object (like how you would declare a Scanner object):

   ```java
   Random someVariableNameHere = new Random();
   ```

3. Generate a random number using `.nextInt(upperBound)`. Here is an example:

   ```java
   Random myRandomObject = new Random();
   myRandomObject.nextInt(15);
   ```

   > - Notice that there is only one number inside the parenthesis. This number is the upper bound and it is also **exclusive** (only includes up to one number earlier)!
   > - When you are only using one parameter for your `.nextInt(...)`, the lower bound is automatcially set to 0!
   > - The code above generates a random number from 0 - 14 (0 and 14 included).

4. Let's say you want to adjust your lower bound to start from 5, you can do the following:

   ```java
   Random myRandomObject = new Random();
   myRandomObject.nextInt(15) + 5;
   ```

   Key observations:

   1. The `myRandomObject.nextInt(15)` part is going to generate a random number between 0 - 14.
   2. Any random number that you generate will be added by 5! This means that the lowest possible number is 5 (0 + 5) and the highest possible number is 19 (14 + 5)

   Key takeaways:

   1. Think about the lower bound first! If you need a lower bound of 7, then you would need a `+ 7` to get the lower bound from 0 to 7.

   2. Next, think about the upper bound! If you need an upper bound of 25, then you want to reduce 7 from 25. _This will give you 18_

   3. Next, try to write the equation out and see if it gives you what you are looking for. For example, if we want to generate a random number between 7 and 25, using the 2 steps above:

      ```java
      Random someRandomObject = new Random();
      someRandomObject.nextInt(18) + 7;
      ```

      Notice that the `someRandomObject.nextInt(18)` part is goign to generate a random number between 0 and 17. Adding the random number by 7 will give you a random number between 7 and 24 (which is not quite what we want).

   4. To adjust this, let's adjust the upper bound by 1! To do that, we will change `someRandomObject.nextInt(18)` to `someRandomObject.nextInt(19)`

      Final formula:

      ```java
      Random someRandomObject = new Random();
      someRandomObject.nextInt(19) + 7;
      ```

5. Don't forget to save your Random number to a variable!

   ```java
   Random someRandomObject = new Random();
   int randomNumber = someRandomObject.nextInt(19) + 7;
   ```

---

## Seeding Random Object

Randomness can cause code testing and debugging to be very difficult because of the unpredictable nature. To resolve this, we can use something called "Seeding".

Here are the steps on how to seed your Random object:

1. Declare your Random object!

```java
Random myRandomObject = new Random();
```

2. Put a number inside the parentheses after the keyword `new Random`. **The number can be any number that you want!**

```java
Random myRandomObject = new Random(839247);
```

_The number that you put inside the parenthesis is what we call the Seeding number_

> Seeding is going to cause your Random object to generate the same sequence of numbers from one run to another run, under two circumstances:
>
> 1. You do not change the Seeding number from one run to another.
> 2. You do not change both the lower bound and the upper bound of the number you are generating.
