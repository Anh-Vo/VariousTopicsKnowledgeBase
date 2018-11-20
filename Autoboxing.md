# What is Autoboxing?

**Autoboxing** is a Java language feature that does the conversion from primitive to wrapper classes automatically.
Take a look at Table 1 to see all of the primitive types and their matching wrapper classes.

Let's take a look a some code snippets to see things clearer:


```java
/** In this example we use autoboxing to get an Integer wrapper class from a primitive int */
int x = 3;     // 3 is a integer primitive here
Integer y = x; // Here 3 is wrapped into the Integer wrapper class 
```

# Can we go backwards?

If we are able to a wrap a primitive, are we able to unwrap it? As it turns out, we can! 

Let's take a look **unboxing**:

```java
/** In this example we auto-unbox a wrapper type and get a primitive type */
Integer x = 3; // Integer is a wrapper type
int y = x;     // int is the primitive type
```

# What's the use?

Autoboxing and unboxing is very useful in a strictly typed language like Java. Why? Well, in addition to the
simple examples above, we can do other things.

## Method Arguments
```java
/** We can use either pass a primitive or a wrapper class to Method Arguments */
int i = 2;
Integer j = 2;

takeInteger(i);
takeInteger(j);

void takeInteger(Integer i) { } // This methods takes an Integer but we can pass it either an int or Integer!

```

## Return values
```java
/** Here, our return value a, can of either type int or an Integer */
int returnInteger() {return a};
```

## Boolean expressions
```java
/** We can use either the boolean primitive or Boolean wrapper class with if expressions */
boolean b = true;
Boolean B = true;

if(B) { }
if(b) { }

```

# Table 1. Primitives and Wrappers

|Primitive type| Wrapper class|
|--------------|--------------|
|boolean	     | Boolean|
|byte	         | Byte|
|char	         | Character|
|float	       | Float|
|int	         | Integer|
|long	         | Long|
|short	       | Short|
|double	       | Double|
