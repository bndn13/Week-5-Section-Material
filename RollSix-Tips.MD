# Tips For RollSix Problem

The problem specification can be found here:
https://edstem.org/us/courses/16200/lessons/27351/slides/154462/solution

---

## PseudoCode

```java
public static void rollSix(Random r) {
        int timesDiceRolled = 0;
        int numberRolled = 1;
        while numberRolled is not equal to 6 {
            1. Generate a number between 1 to 6
            2. Print out "Rolled: " followed by the number we just generated
            3. Increment the timesDicedRolled by one
        }
        Print out "You got a six in " + timesDiceRolled +  "turns."
    }
}
```

Key observations:

1. `int timesDiceRolled` keeps track of how many times we have "rolled a rice" (generate a random number between 1 and 6 inclusive)

2. `int numberRolled` keeps track of how what number we get from "rolling the dice (the random number that we get between 1 and 6 inclusive)

3. We prime the `numberRolled = 1` to get into the while loop at least once.

4. **In most cases, it is easier to finish your while-loop and everything inside it as this helps you to figure out whether you need to prime your loop or not.**
