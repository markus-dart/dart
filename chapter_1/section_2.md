# **Types**

As it was discussed in the previous section, variables can store various *types* of values.

Now, before diving into the topic, understand that, *types*, in this case, is not regarding those defined within the source code of the language, rather it is an *abstract* concept.

In general, any *abstract* concept of a programming language is standardized using something called a *specification* from which a programmer can build a compiler.

> **Note:** Most open source languages, provide such specifications to allow contributions to the language.

The programmer can then ascertain as to what is needed for *implementation* based on their target platform.

Having this basic distinction, we can understand what *types* are in the context of programming.

## **The Data Type**

> A ***data type*** or simply ***type*** refers to the *attribute* of data, that defines the general *characteristics* of that particular data.

To understand clearly as to what the above definition conveys, consider this analogy,

> Dart is a programming language.  
> Dart is an *efficient* programming language.

In the above sentence, *efficient* is an **adjective** and *programming language* is a **noun**. Here, the first sentence would be enough to convey the general meaning.

So, what is the actual purpose of an *adjective*? An adjective ***modifies*** a *noun*. More simply, an adjective provides a ***description*** for the *noun*.

In a similar way, consider this,

```dart
var number = 42;
int integer = 42;
```

The variables `number` and `integer` both convey the same meaning, i.e., they hold the same data, but `number` is similar to a sentence without an adjective, it does not provide a description as to *what* `number` can hold.

Therefore, when we introduce `int`, as a type ***modifier***, it provides a *characteristic* to the variable `integer`, i.e. it can hold any integer data, as **described** by the type `int`.

> **Note**: The Dart compiler is intelligent enough to *infer* the type of `number` to be an `int`, this is called *implicit type conversion*.

***

In general, data types are ***modifiers*** to any *data* or *expression*, just like adjectives are to nouns, that provides a ***description*** for that data.

The ***description*** can contain the meaning of the data, the operations that can be performed on the data, and how it can be stored, all based on the programming language.

>Remember that `var`, `final` and `dynamic` are modifiers to a *variable*. They only provide *context* as to *how* the variable behaves.

## **Types in Dart**

An important point to remember, before understanding the type system of any language, is that, types ***describe*** *data* and not *variables*.

The basic *constructs* that are required to represent all the types of the language are called *primitive* or *atomic* types.

These can be thought of as the *building blocks* of data in the language, from which other types can be constructed, called *user-defined* types.

In Dart, the primitive or atomic types are the following,

- Basic Types
  - numbers
  - strings
  - booleans

- Collections
  - lists
  - sets
  - maps

- Other Types
  - runes
  - symbols

In any language, every primitive type generally has a *literal*, which is nothing but a value that can be defined in the program.

### **Literal**

> A literal is the representation of a fixed value in a source code.

```dart
var name = 'Markus';
var age = 42;
var colours = ['Green', 'Blue', 'Red'];
if (age > 50) {
  //Statement
}
```

In the above code `'Markus'`, `42` and `['Green', 'Blue', 'Red']`, `50`, are all *values* belonging to some *type*.

Notice that `50` is not assigned to any variable, but within an expression, which implies that literals are ***any*** primitive values within a program, that is supported by the language.

Therefore, the definition becomes,

> Any discrete *value* of a primitive *type*, is called a **literal** of that particular *type*.

Therefore, we can declare *literals* directly in a program that the compiler understands, which means it will be evaluated during compilation, making it a *compile-time constant*.

> **Note:** Every literal is an object of some *type* because dart implements *types* through [***classes***][class].

## **Implementation of Types**

Recall that in Dart, everything that can be stored in a variable is an Object. Now, what is this '*thing*'? The '*thing*' refers to any literal or a runtime value, generally some data, belonging to a particular *type*.

This type, can be primitive or user-defined, but the important thing to understand is that the value is an *Object*.

How does a literal, runtime value, or some other data become an object?

The answer lies in the implementation of types in Dart. Due to Dart striving to be a purely object oriented language, even *prmitive types* are implemented using [*classes*][class].

Consider the following,

```dart
int x = 50;
double y = 15.5;
```

Here `x` and `y` are not just variables, but are *objects* of *type* `int` and `double` respectively, i.e., `int` and `double` are literally classes.

Dart follows this pattern to allow for values to be treated as objects which can be extremely useful to manipulate values.

Now that we have a basic understanding of *types* and *literals*, we can discuss the types supported by Dart.

### **Numbers**

Numbers, as the name suggests, denotes any integer or decimal point values otherwise called *floating points*.

Dart provides support for these types through `int` for integer values and `double` for floating point integers. Here `int` and `double` are subtypes of `num`.

**`int`**

In Dart, integers can be 64 bits i.e. values can range from -2<sup>63</sup> to 2<sup>63</sup> - 1 (which is quite large) on the Dart compiler.

**`double`**

Doubles are again 64 bits, but they facilitate usage of floating points.

Integers and doubles can be defined similar to,

```dart
var dec = 50; //decimal int literal
var hex = 0xABCD; //hexadecimal int literal
var float = 1.5; //floating point double literal
var exp = 1.5e5 //exponent double literal
```

Notice that the prefix `int` or `double` is not necessary when declaring literal values, Dart readily infers the *type*.

> If it is required for a variable to hold some *type*, say `int`, without knowing the value at compile time, use the type annotation (prefix) `int`.

### **Strings**

Strings are a sequential collection of characters, i.e. plain text can be reffered to as strings.

Strings are implemented using the `String` type, which is a sequence of *UTF-16* code units. String literals can be created using either `''` (*single*) or `""` (*double*) quotes. `'''` (*triple quotes*) can be used for constructing multi-line strings.

```dart
var dart = 'Dart is a programming language' //Valid String
var string = '''This is
an example for
a multi-line string'''; //valid String
```

String interpolation, or using expression within strings is also supported by Dart through `${`*expression*`}` within a string.

```dart
var name = 'Markus';
print('My name is $name'); //Output: 'My name is Markus'
print('My name is ${name.toUpperCase()}'); //Output: 'My name is MARKUS'
```

> **Note:** `name.toUpperCase()` is an expression. Also, the curly braces `{}` are not required if only variables are used in string interpolation.

### **Booleans**

For representing boolean values (true and false), Dart provides the `bool` type.

The boolean literals `true` and `false`, which are compile-time constants, are the only objects that fall under the `bool` type.  

> Generally booleans need not be declared, and are most often used in conditional or looping statements.

### **Collections**

[TODO]

***

Before moving on to *functions*, try and explore different possibilities with *types* and *variables* using the [*dartpad*][dartpad].  
As when learning any programming language, it is always essential to get a good grip by practicing and testing out different scenarios.

[class]: https://github.com/markus-dart/dart/blob/master/chapter_3
[dartpad]: https://dartpad.dev
