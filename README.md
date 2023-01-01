# SBT IDE Boilerplate

## Installation
* Use Java 11
  * `brew install openjdk@11`
* Link the brew to jvm
  * `sudo ln -sfn /opt/homebrew/opt/openjdk@11/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-11.jdk`
* Add 11 to home path
  * `echo 'export PATH="/opt/homebrew/opt/openjdk@11/bin:$PATH"' >> ~/.zshrc`
* Install sbt
  * `brew install sbt`
* Use latest sbt version in new project
  * `cd sbt-ide-boilerplate`
  * `sbt`
  * `sbt:sbt-ide-boilerplate> set scalaVersion := "2.13.10"`
* Seed a template
  * `sbt new scala/scala-seed.g8`

## REPL
* Scala REPL
  * `sbt-ide-boilerplate sbt`
    * `sbt:sbt-ide-boilerplate> console`
      * `scala> :h`
      * `scala> :replay`
      * `scala> :save`
      * `scala> :load`
      * `scala> :paste`
      * `scala> :reset`
      * `scala> :q`
    * `sbt:sbt-ide-boilerplate> [ctrl+d]`
  * `sbt-ide-boilerplate`

## Types

### Fundamentals

<details>
<summary><a href="https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html">Datatypes</a></summary>

* **[byte](https://scala-lang.org/api/current/scala/Byte.html)**: The `byte` data type is an 8-bit signed two's complement integer. It has a minimum value of -128 and a maximum value of 127 (inclusive). The `byte` data type can be useful for saving memory in large [arrays](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html), where the memory savings actually matters. They can also be used in place of int where their limits help to clarify your code; the fact that a variable's range is limited can serve as a form of documentation.


* **[short](https://scala-lang.org/api/current/scala/Short.html)**: The `short` data type is a 16-bit signed two's complement integer. It has a minimum value of -32,768 and a maximum value of 32,767 (inclusive). As with `byte`, the same guidelines apply: you can use a `short` to save memory in large arrays, in situations where the memory savings actually matters.


* **[int](https://scala-lang.org/api/current/scala/Int.html)**: By default, the `int` data type is a 32-bit signed two's complement integer, which has a minimum value of -2<sup>31</sup> and a maximum value of 231-1. In Java SE 8 and later, you can use the `int` data type to represent an unsigned 32-bit integer, which has a minimum value of 0 and a maximum value of 2<sup>32</sup>-1. Use the Integer class to use int data type as an unsigned integer. See the section The Number Classes for more information. Static methods like `compareUnsigned`, `divideUnsigned` etc have been added to the [Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html) class to support the arithmetic operations for unsigned integers.


* **[long](https://scala-lang.org/api/current/scala/Long.html)**: The `long` data type is a 64-bit two's complement integer. The signed long has a minimum value of -2<sup>63</sup> and a maximum value of 2<sup>63</sup>-1. In Java SE 8 and later, you can use the `long` data type to represent an unsigned 64-bit long, which has a minimum value of 0 and a maximum value of 2<sup>64</sup>-1. Use this data type when you need a range of values wider than those provided by `int`. The [Long](https://docs.oracle.com/javase/8/docs/api/java/lang/Long.html) class also contains methods like `compareUnsigned`, `divideUnsigned` etc to support arithmetic operations for unsigned long.


* **[float](https://scala-lang.org/api/current/scala/Float.html)**: The `float` data type is a single-precision 32-bit IEEE 754 floating point. Its range of values is beyond the scope of this discussion, but is specified in the [Floating-Point Types, Formats, and Values](https://docs.oracle.com/javase/specs/jls/se7/html/jls-4.html#jls-4.2.3) section of the Java Language Specification. As with the recommendations for `byte` and `short`, use a `float` (instead of `double`) if you need to save memory in large arrays of floating point numbers. This data type should never be used for precise values, such as currency. For that, you will need to use the [java.math.BigDecimal](https://docs.oracle.com/javase/8/docs/api/java/math/BigDecimal.html) class instead. [Numbers and Strings](https://docs.oracle.com/javase/tutorial/java/data/index.html) covers `BigDecimal` and other useful classes provided by the Java platform.


* **[double](https://scala-lang.org/api/current/scala/Double.html)**: The `double` data type is a double-precision 64-bit IEEE 754 floating point. Its range of values is beyond the scope of this discussion, but is specified in the [Floating-Point Types, Formats, and Values](https://docs.oracle.com/javase/specs/jls/se7/html/jls-4.html#jls-4.2.3) section of the Java Language Specification. For decimal values, this data type is generally the default choice. As mentioned above, this data type should never be used for precise values, such as currency.


* **[boolean](https://scala-lang.org/api/current/scala/Boolean.html)**: The `boolean` data type has only two possible values: `true` and `false`. Use this data type for simple flags that track true/false conditions. This data type represents one bit of information, but its "size" isn't something that's precisely defined.


* **[char](https://scala-lang.org/api/current/scala/Char.html)**: The `char` data type is a single 16-bit Unicode character. It has a minimum value of `'\u0000'` (or 0) and a maximum value of `'\uffff'` (or 65,535 inclusive).

In addition to the eight primitive data types listed above, the Java programming language also provides special support for character strings via the [java.lang.String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html) class. Enclosing your character string within double quotes will automatically create a `new String object;` for example, `String s = "this is a string";`. `String` objects are _immutable_, which means that once created, their values cannot be changed. The `String` class is not technically a primitive data type, but considering the special support given to it by the language, you'll probably tend to think of it as such. You'll learn more about the String class in [Simple Data Objects](https://docs.oracle.com/javase/tutorial/java/data/index.html)

[Source](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html)


</details>

### `AnyVal` and `AnyRef`
<details>
<summary>Unified Types</summary>
<img src="https://docs.scala-lang.org/resources/images/tour/unified-types-diagram.svg">
</details>

### `val aShort: Short = 128`
> `val aInt: Int = aShort`

<details>
<summary>Type Casting</summary>
<img src="https://docs.scala-lang.org/resources/images/tour/unified-types-diagram.svg">
</details>

### Collections 

<details>
<summary>Collections Legend</summary>
<img src="https://docs.scala-lang.org/resources/images/tour/collections-legend-diagram.svg">
</details>
<details>
<summary>Collections 2.13</summary>
<img src="https://docs.scala-lang.org/resources/images/tour/collections-diagram-213.svg">
</details>
<details>
<summary>Collections</summary>
<img src="https://docs.scala-lang.org/resources/images/tour/collections-diagram.svg">
</details>

### Mutability

<details>
<summary>Mutable Collections 2.13</summary>
<img src="https://docs.scala-lang.org/resources/images/tour/collections-mutable-diagram-213.svg">
</details>
<details>
<summary>Mutable Collections</summary>
<img src="https://docs.scala-lang.org/resources/images/tour/collections-mutable-diagram.svg">
</details>
<details>
<summary>Immutable Collections 2.13</summary>
<img src="https://docs.scala-lang.org/resources/images/tour/collections-immutable-diagram-213.svg">
</details>
<details>
<summary>Immutable Collections</summary>
<img src="https://docs.scala-lang.org/resources/images/tour/collections-immutable-diagram.svg">
</details>

### `java.time`
[Date and Time](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/time/package-summary.html)


## References
* [scala](https://www.scala-lang.org/download/)
* [scala-sbt](https://www.scala-sbt.org/)