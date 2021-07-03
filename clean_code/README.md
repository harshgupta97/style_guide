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

## Long Parameter List

```c++
checkNotification(null, 1, true, false, DateTime.Now);
```

### Method Parameter Best Practise

- Less then 3 parameters

## Output Parameters


