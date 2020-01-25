# **Chapter One - *The Basics***

This chapter deals with the *building blocks* of the language, you many skip this chapter entirely and just learn the nuances of the *keywords*, if you are already familiar with these concepts.

## **The Sections**

- [**Section One**][section1] : Introduction to variables and values.
- [**Section Two**][section2] : Some insight to the built-in types.

Before proceeding let us first perform the ritual of the *Hello World* program, as is the case when learning any language.

## **Hello World**

A '*hello world*' program in dart,

```dart
void main() {
  print('Hello, World!');
}
```

The above code shows the general structure of a dart program.

- Notice that there is a *function* `main()` within which the `print()` resides.  
- `'Anything within quotes is a String'`.  
- Logical lines are terminated using `;`

>To understand the concept of *functions*, visit [Chapter 2][chapter2].

## **`main()`**

As already ascertained, Dart follows the *C* style syntax, which uses the concept of an ***entry point*** to a program.

This concept provides languages that are *compiled* to be extremely robust when implementing *Algorithms*.

Here `main()` acts as the *entry point* for the Dart program. It is just like any other *function*, except that, it is *called* first when a program is *executed*.

### **Points To Remember**

- It is important to note that in Dart, everything that can be stored in a *variable* is an *object*.

- An *object* is simply an *instance* of a class.

- Dart allows *functions* to behave as *objects*, it is due to Dart being *class* based, and hence one can store *functions* just like *values*.

- Dart is a *strongly typed* language, i.e. Dart provides primitive *types* (`int`, `double`...) for data, but it also has the ability to *infer* types, hence providing functionality as per need.

>To understand what *objects* are, and why *functions* can be treated as objects, visit [Chapter 3][chapter3].

[chapter2]: https://github.com/markus-dart/dart/tree/master/chapter_2
[chapter3]: https://github.com/markus-dart/dart/tree/master/chapter_3
[section1]: https://github.com/markus-dart/dart/blob/master/chapter_1/section_1.md
[section2]: https://github.com/markus-dart/dart/blob/master/chapter_1/section_2.md
