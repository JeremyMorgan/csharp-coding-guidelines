C# Coding Guidelines
=========

This is a set of C# Coding Guidelines I'm putting together for myself and others in the community who would like to contribute. It will be both coding guidelines and tips / best practices for C#.

I have also added [some snippets](https://github.com/JeremyMorgan/csharp-coding-guidelines/tree/master/snippets "Code Snippets") to load into Visual Studio for time saving purposes. 

Feel free to contribute!

##Code Layout
Use Visual Studio Defaults
- 4 character indentation
- tabs saved as spaces

Source Code Layout

- One statement per line
- One declaration per line

Good:
``` C#
int price;
int tax;
int total;
```

Bad:
``` C#
int price, tax, total;
```
- separate method definitions from property definitions ( 1 blank line )
- bracket on line following statement:

Good:
``` C# 
public int returnInt()
{
    // stuff
}
```

Bad:
``` C# 
public int returnInt(){
    // stuff
}
```

## Variables

use camel case for fields and local variables:

``` C#
string myString
```

Use Pascal casing for all public member, type, and namespace names consisting of multiple words.

(From MSDN)

``` C# 
public class SampleClass
{
   public Color BackColor 
   {
      // Code for Get and Set accessors goes here.
   }
}
```

Use camel casing for parameters:

``` C#
public void RemoveString(string ourString) 
```

DO NOT use Hungarian notation or language specific naming ( IntMyInteger or ConvertToShort )

##Classes

###A class or interface should have a single purpose. 

A class can represent a primitive type or datastructure, abstraction or handle interaction between other classes. But don't mix any of these things. Follow the "Single Responsibility Principle" (from SOLID) 

Use design patterns to communicate the intent of the class. 

##Constructors

Constructors should only be used to create a useful object. If you have too many paramaters in your constructor your class may have too much responsibility.


###Use a method instead of a property

Whenever you have a property that:

- Contains logic
- performs more work than setting a value
- returns a different value with similar arguments (rand, guid, etc)
- Changest the state of another property or object

Use a method instead. 

Use Pascal casing

##Miscellaneous

###Throw exceptions not values

It's common for people throw a status value, such as a plain text friendly message or a boolean value to indicate success. Use the exception system to it's advantage. Catch the exception and out output it to a debug console or log it in another way. It's ok to append a friendly message or hint to what may have happened, but don't rely on this. Structured exception handling reduces debugging and repair time dramatically. 

###Return IEnumerable<T> instead of a concrete collection class

You generally don't want to expose your collection to a caller. Don't return collections such as Arrays, lists, etc. Push the data into an IEnumerable, or in .Net 4.5 a read only collection like IReadOnlyCollection<T>

    
