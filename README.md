C# Coding Guidelines
=========


This is a set of C# Coding Guidelines I'm putting together for myself and others in the community who would like to contribute. It will be both coding guidelines and tips / best practices for C#.

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


##Classes

###Use a method instead of a property

Whenever you have a property that:

- Contains logic
- performs more work than setting a value
- returns a different value with similar arguments (rand, guid, etc)
- Changest the state of another property or object

Use a method instead. 


    
