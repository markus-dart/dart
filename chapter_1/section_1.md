# Variables and Values

## Variables  

Variables are generally references to some values in memory. A good distinction to make, before proceeding to understanding variables, is that *variables* and *values* mean entirely different things.

One must understand that *variables* are some **name** given to a space in memory, through which certain characteristics can be enforced on that memory.

The memory space can then be **initialized** with a *value* that fulfills this characteristic demand.

A *value* is any valid *data* that can be used in the program.

Hence, the very name *variable* means something that may *vary* depending on its characteristics.

### **`var`**

As dart is not strictly typed, per se, one can declare variables using the `var` keyword. For example :

```dart
var name = 'Markus';
name = 'Connor'; //can assign values of type String
```

Realize that `var` behaves as if it creates a *reference* to a space of memory, which when initialized gets the type *inferred* from the value.

Therefore, one cannot change the *type* of a `var` variable but can only change its *value*, as in the example above, the variable **name** becomes a `String` once initialized.

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

As the above code shows, a `final` variable is one that can only be *initialized* once, from where it cannot be modified. It creates an *immutable* object, in this case a `String`.

## The `const` keyword

So far, every *variable type* discussed are instantiated at *runtime* i.e. the Dart VM gets to know the *types* or even *values* only at *runtime*.

But Dart also has a special yet sometimes misunderstood keyword, namely `const`. At this point, one may ponder as to why such a keyword is required, when there is the concept of `final` fields.

>`const` enables identifiers and values to be evaluated at compile-time.

To understand this, we need to understand *how* and more importantly ***when*** variables are ***initialized***.

Variables that are assigned through `final`, `var` or `dynamic` are evaluated at *runtime* i.e. they obtain values only when the code is running.

Sometimes, situations may arise where a value, say the *height* of a *Button*, is known even before compilation. These values can be assigned right at *compile-time* using `const`.

**What `const` does to variables ?**  

>Memory is allocated to a `const` variable at compile-time and, for a `final` variable at runtime.

```dart
const height = 50;
```

Any *variable* prefixed with `const` is evaluated at compile-time. Notice that `50` is a *literal* value and is therefore trivially a constant.

>Hence, a `const` variable or rather a `const` identifier is a compile-time object that takes only *constant* `values`.

**What `const` does to values ?**

```dart
const numbers = const [1, 2, 3];
var values = const [1, 2, 3]; //Also Valid
```

>Note that `[1, 2, 3]` is a collection literal which is primitive in nature, therefore it can be modified using a `const`.

The above code clearly distinguishes the working of `const` i.e. it modifies literal values as well as variables. This behaviour is possible due to the very nature of things in Dart.

In conclusion, a constant variable is an immutable *compile-time* variable that takes only constant values whereas a final variable is a *runtime* variable that can be assigned only *once*.

In practice, the `const` on *values* is generally omitted, the below example implies the same meaning as previous,

```dart
const numbers = [1, 2, 3];
var values = [1, 2, 3];
```

The nature of `const` can be further solidified in the classes and objects section.
