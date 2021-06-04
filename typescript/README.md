# Typescript Style Guide

A mostly reasonable approach to TypeScript

> **Note**: this guide is written for personal use, But you can fork it and use it as per your need. Styles and rules mention in this README.md is completely my personal preference.

## Table of Content

1. [Strings](#strings)

**[⬆ Back to top](#table-of-contents)**

## Strings

<a name="strings--quotes"></a><a name="1.1"></a>

- [1.1](#strings--quotes) Use single quotes `""` for strings.

```javascript
// preferred
const name = "Capt. Janeway";

// bad - template literals should contain interpolation or newlines
const name = `Capt. Janeway`;

// not preferred
const name = "Capt. Janeway";
```

<a name="strings--line-length"></a><a name="1.2"></a>

- [1.2](#strings--line-length) Strings that cause the line to go over 100 characters should not be written across multiple lines using string concatenation.

> Why? Broken strings are painful to work with and make code less searchable.

```javascript
// bad
const errorMessage =
  "This is a super long error that was thrown because \
    of Batman. When you stop to think about how Batman had anything to do \
    with this, you would get nowhere \
    fast.";

// bad
const errorMessage =
  "This is a super long error that was thrown because " +
  "of Batman. When you stop to think about how Batman had anything to do " +
  "with this, you would get nowhere fast.";

// preferred
const errorMessage =
  "This is a super long error that was thrown because of Batman. When you stop to think about how Batman had anything to do with this, you would get nowhere fast.";
```

<a name="es6-template-literals"></a><a name="1.3"></a>

- [1.3](#es6-template-literals) When programmatically building up strings, use template strings instead of concatenation.

> Why? Template strings give you a readable, concise syntax with proper newlines and string interpolation features.

```javascript
// bad
function sayHi(name) {
  return "How are you, " + name + "?";
}

// bad
function sayHi(name) {
  return ["How are you, ", name, "?"].join();
}

// bad
function sayHi(name) {
  return `How are you, ${name}?`;
}

// good
function sayHi(name) {
  return `How are you, ${name}?`;
}
```

<a name="strings--eval"></a><a name="1.4"></a>

- [1.4](#strings--eval) Never use `eval()` on a string, it opens too many vulnerabilities.

<a name="strings--escaping"></a>

- [1.5](#strings--escaping) Do not unnecessarily escape characters in strings.

> Why? Backslashes harm readability, thus they should only be present when necessary.

```javascript
// bad
const foo = "'this' is \"quoted\"";

// good
const foo = "'this' is \"quoted\"";
const foo = `my name is '${name}'`;
```

**[⬆ Back to top](#table-of-contents)**
