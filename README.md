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


    
