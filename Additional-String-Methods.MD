# Additional String Methods for A5!

## Table of Content

- [String Method `.startsWith(...)`](#string-method-startswith)
- [String Method `.toLowerCase()`](#string-method-tolowercase)
- [String Method `.toUpperCase()`](#string-method-touppercase)

---

## String Method `.startsWith(...)`

The String Method `.startsWith(...)` takes in a letter or a phrase and returns `true` if your String starts with that letter or phrase.

_Example:_

```java
String input = "hello";
boolean startWithH = input.startsWith("h");
System.out.println(startWithH)
```

_Output:_

```
true
```

_Example II :_

```java
String input = "hello";
boolean startWithLo= input.startsWith("lo");
System.out.println(startWithLo);
```

_Output:_

```
false
```

---

## String Method `.toLowerCase()`

String method `.toLowerCase()` **gives back a copy of** your String in all lower case.

_Example:_

```java
String input = "HeLLo";
boolean lowerCased = input.toLowerCase();
System.out.println(lowerCased)
```

_Output:_

```
hello
```

> Warning! .toLowerCase() and .toUpperCase() does not change your original String! It only gives you a copy of the changed String!

---

## String Method `.toUpperCase()`

String method `.toUpperCase()` **gives back a copy of** your String in all upper case.

_Example:_

```java
String input = "heLLo";
boolean upperCased = input.toLowerCase();
System.out.println(upperCased)
```

_Output:_

```
HELLO
```
