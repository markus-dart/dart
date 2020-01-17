# Chapter One - *The Basics*

## Hello World

A general '*hello world*' program in dart

```dart
void main() {
  print('Hello, World!');
}
```

The above code shows the general structure of a dart program.

> It is important to note that in dart everything is an object, even a *function* is an object and can be treated as such.

## Variables  

Variables are generally references to some values in memory.

### **`var`**

As dart is not strictly typed, per se, one can declare variables using the `var` keyword. For example :

```dart
var name = 'Markus';
name = 'Connor'; //can assign values of type String
```

Realize that `var` behaves as if it creates a *reference* to a space of memory, which when initialized gets the type inferred from the value.

Therefore, one cannot change the *type* of a `var` variable but can only change its *value*, as in the variable **name** becomes a `String` once initialized.

> Note: Uninitialized variables default to `null`

### **`dynamic`**

Due to the flexible nature of dart, one can assign different *types* of values for the same variable using `dynamic`. For exmaple :

```dart
dynamic age = '20';
age = 20; //Valid assignment of int to a String variable
```

### **`final`**  

Now that we understand how we can store data i.e. *values*, we can apply certain constraints on them. For example :

```dart
final name = 'Markus';
name = 'Connor'; //Cannot change value of final field
```

As the above code shows, a `final` variable is one that can only be initialized once, from where it cannot be modified. It creates an *immutable* object, in this case a `String` variable.

> So far, every *variable type* we have been discussing are instantiated at *runtime* i.e. the Dart VM gets to know the *types* or even *values* only at *runtime*.

### **`const`**

Sometimes we may require values that need to be *hardcoded*, say the height of a *form* in some application, for that, we already know the value, say `50`, at *compile-time*. To facilitate such cases, `const` is used. For Example :

```dart
const height = 50;
const list = [];
```

### Where to use `const`

[TODO]
