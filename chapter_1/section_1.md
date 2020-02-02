# **Variables and Values**

## **Variables**  

Variables are generally references to some values in memory. A good distinction to make, before understanding variables, is that *variables* and *values* mean entirely different things.

One must understand that *variables* are some **name** given to a space in memory, through which certain characteristics can be enforced on that memory.  

The memory space can then be **initialized** with a *value* that fulfills this characteristic demand.  

Initialization means, the first or *initial* assignment (storage) of a *value* to a variable using the "`=`" operator.

A *value* is any valid *data* that can be used in the program.

Hence, the very name *variable* means something that may *vary* depending on its characteristics.

### **`var`**

As dart is not strictly *typed*, per se, one can declare variables using the `var` keyword. For example :

```dart
var name = 'Markus';
name = 'Connor'; //can assign values of type String
```

Realize that `var` behaves as if it creates a *reference* to a space of memory, which when initialized gets the [*type*][types] *inferred* from the value.

Therefore, one cannot change the *type* of a `var` variable but can only change its *value*, as in the example above, the variable **name** adheres to the `String` *type*, once initialized.

> Note: Uninitialized variables default to the `null` *type*.

To get a better understanding of types, go through the [*types*][types] section in this chapter.

### **`dynamic`**

Due to the flexible nature of Dart, one can assign different *types* of values for the same variable using `dynamic`. For exmaple :

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

As the above code shows, a `final` variable is one that can only be *initialized* once, from where it cannot be modified. It creates an *immutable* object, in this case a `String`.

### **The `const` keyword**

So far, every *variable type* discussed are instantiated at *runtime* i.e. the Dart VM gets to know the *types* or even *values* only at *runtime*.

But Dart also has a special yet sometimes misunderstood keyword, named `const`. At this point, one may ponder as to why such a keyword is required, when there is the concept of `final`.

>`const` enables identifiers and values to be evaluated at compile-time.

To understand this, we need to understand *how* and more importantly ***when*** variables are ***initialized***.

Variables that are assigned through `final`, `var` or `dynamic` are evaluated at *runtime* i.e. they obtain values only when the code is running.

Sometimes, situations may arise where a value, say the *height* of a *Button*, is known even before compilation. These values can be assigned right at *compile-time* using `const`.

#### **How does `const` modify variables?**  

>Memory is allocated to a `const` variable at compile-time and, for a `final` variable at runtime.

```dart
const height = 50;
```

Any *variable* prefixed with `const` is evaluated at compile-time. Notice that `50` is a [*literal*][literal] value and is therefore trivially a constant.

>Hence, a `const` variable or rather a `const` identifier is a compile-time object that takes only *constant* `values`.

#### **How does `const` modify values?**

>When `const` is prefixed on a value it generates a single memory for that *literal*, and any objects that have the same constant value refer to that memory.

```dart
const numbers = const [1, 2, 3];
var values = const [1, 2, 3]; //Also Valid
print(identical(numbers, values)); //results in 'true' as they point to the same memory

values = new List<int>(4); //can point to new object of same type
```

>`identical()` is used to know whether two objects are the exact same object.

Note that `[1, 2, 3]` is a collection literal which is primitive in nature, therefore it can be modified using a `const`.

The above code clearly distinguishes the working of `const` i.e. it modifies literal values as well as variables. Further more `const` also modifies *objects* which can be seen in the [*classes and objects*][chapter3] section.

In conclusion, a constant variable is an immutable *compile-time* variable that takes only constant values whereas a final variable is a *runtime* variable that can be assigned only *once*.

> In practice, the `const` on *values* is generally omitted for *`const` variables*, the below example implies the same meaning as the previous code,

```dart
const numbers = [1, 2, 3];
var values = const [1, 2, 3];
print(identical(numbers, values)); //is again 'true'

values = new List<int>(3); //can point to new object of same type
```

Another distinction made below, is that, `const` is applied to literals only when the variable is a `const`.

```dart
const numbers = /* const */ [1, 2, 3];
var values = [1, 2, 3];

/*here 'values' is initialized with a new primitive object by default, being a var variable */

print(identical(numbers, values)); //hence results in 'false'
```

[chapter3]: https://github.com/markus-dart/dart/blob/master/chapter_3
[literal]: https://github.com/markus-dart/dart/blob/master/chapter_2/section_2.md#literal
[types]: https://github.com/markus-dart/dart/blob/master/chapter_2/section_2.md#types
