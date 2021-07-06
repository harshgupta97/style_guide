# Clean Code

## Table of Content

1.  [Poor Names](#poor-names)
2.  [Poor Naming Convention](#poor-naming-conventions)
3.  [Poor Method Signature](#poor-method-signature)
4.  [Long Parameter List](#long-parameter-list)
5.  [Output Parameters](#output-parameters)
6.  [Variable Declarations on the Top](#variable-declarations-on-the-top)
7.  [Magic Numbers](#magic-numbers)
8.  [Nested Conditionals](#nested-conditionals)
9.  [Switch Statements](#switch-statements)
10. [Duplicate Code](#duplicate-code)
11. [Comments](#comments)
12. [Long Methods](#long-methods)

**[⬆ Back to top](#table-of-contents)**

## Poor Names

- Mysterious name

```c++
int od;
```

- Meaningless name

```c++
void beginCheckFunctionality_StoreClientSideCheckBox();
```

- Name with encoding

```c++
int iAge;
```

- Ambiguous name

```c++
int? incidentNameId;
```

- Noisy Name

```c++
Customer theCustomer();
```

**[⬆ Back to top](#table-of-contents)**

## Poor Naming Convention

```c++
Customer GetCustomer(int _id);

Customer SaveCustomer(Customer Customer);

private int customerId;
```

### Naming convention

- PascalCase

- camelCase

```C++
public class Customer{
    private int _id;

    public string Name { get; set; }

    public void charge(int amount)
    {
        var tax = 0;
    }
}
```

**[⬆ Back to top](#table-of-contents)**

## Poor Method Signature

```c++
Orange GetCustomer(int airplane);
```

```c++
// Wrong
void Parse(int command);

// Correct
void Parse(string command);
```

**[⬆ Back to top](#table-of-contents)**

## Long Parameter List

```c++
checkNotification(null, 1, true, false, DateTime.Now);
```

### Method Parameter Best Practise

- Less then 3 parameters

**[⬆ Back to top](#table-of-contents)**

## Output Parameters

```c++
int count = 0;
bool more = false;

var customer = GetCustomers(pageIndex, out count, out more);
```

**[⬆ Back to top](#table-of-contents)**

## Variable Declarations on the Top

- Declare them close to their usage.

**[⬆ Back to top](#table-of-contents)**

## Magic Numbers

Avoid magic number all time use constant or enumeration

```c++
// Bad
if(status == 1){
    // ...
} else if(status == 2) {
    // ...
}
```

```c++
if(status == Draft){
    //
} else if(status == Lodge){
    //
}
```

**[⬆ Back to top](#table-of-contents)**

## Nested Conditionals

### Use ternary operator

```c++
// Ex 1
// bad
if(a) {
    c = somevalue;
} else {
    c = anotherValue;
}

// good
c = (a) ? someValue : anotherValue;
```

```c++
// Ex 2
// Bad
if(customer.TotalOrder > 50) {
    discount = 0.1f;
} else {
    discount = 0.01f;
}

// Good
discount = (customer.TotalOrder > 50) ? 0.1f : 0.01f;
```

```c++
// Ex 3
// Bad
if(customer.TotalOrder > 50) {
    return  0.1f;
} else {
    return  0.01f;
}

// Good
return (customer.TotalOrder > 50) ? 0.1f : 0.01f;
```

### Ternary Operator abuse

```c++
// Bad
c = a ? b: d ? e: f;
```

### Simplify true and false

```c++
// Bad
if(a){
    b = true;
} else {
    b = false;
}

// Good
b = a;
```

```c++
// Okay
if(customer.TotalOrder > 50) {
    isGoldCustomer = true;
} else {
    isGoldCustomer = false;
}

// Optimal
isGoldCustomer = (customer.TotalOrder > 50) ? true : false;
```

```c++
// Not optimal
if(a){
    if(b){
        // statement
    }
}

// Optimal aka (Combine)
if(a && b) {
    // statement
}

// Early exit
if(!a) // Guard statement
    return;

if(!b) // Guard statement
    return;

statement;

// Early exit + Combine
if(!a || !b){
    // statement
}
```

### Swap Orders

```c++
if(a) {
    if(b){
        isValid = true;
    }
}
if(c) {
    if(b){
        isValid = true;
    }
}

// Optimize
if(b) {
    if(a){
        isValid = true;
    }
    if(c){
        isValid = true;
    }
}

// Optimize (Combine again)
if(b) {
    if(a || c){
        isValid = true;
    }
}

isValid = (b && (a || C));
```

### Eveerything in moderation

```c++
// STINKS !!!
if(a && (b || c) && !d || e && (f && !g || h))
```

**[⬆ Back to top](#table-of-contents)**

## Switch Statements

Carefull, Don't use switch statement where there is a change that more codition will come along with time.

**[⬆ Back to top](#table-of-contents)**

## Duplicate Code

DRY - Don't Repeat Yourself

**[⬆ Back to top](#table-of-contents)**

## Comments

- Stating the Obvious

The Ultimate comment for the code is "the code itself"

### Version history (Don't)

```c++
// prior to v1.3
if(isActive) {}
```

### Clarify the Code

```c++
// don't
var pf = 10; // pay frequency

// do

var payFrequency = 10;

```

### Dead Code

```c++
// public class WorkScheduler
// {
// }
```

### Comments Best Practises

- Don't write comments, re-write your code!
- Don't explain "whats" (the obvious)
- Explain "why" and "hows"

**[⬆ Back to top](#table-of-contents)**

## Long Methods

Long method is the one with more then 10 line of code.

### Problem with Long Methods

- Hard to understand
- Hard to change
- Hard to re-use

We want methods that specialise in one thing

### Cohesion Principle

- Things that are related, should be together.
- Things that are not related, should not be together.

### Cohesion at the Class Level

### Single Responsibility Principle

- A class/method should do only one thing, and do it very well.
