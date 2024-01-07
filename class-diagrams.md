# Class diagrams
Refer: https://mermaid.js.org/syntax/classDiagram.html

The class diagram represents the classes and their relationships with UML notations.

## Class Members
UML provides how to represetn class members such as **attributes** and **methods**.
Mermaid distinguishes between attributes and functions/methods based on whether `()` are present or not.
```
classDiagram
class ClassName
    ClassName : +Type attribute
    ClassName : +method(arg1, arg2) return
```
Insetead of writing the class name every time, group members of a class using `{}` brackets.
```
classDiagram
class ClassName {
    +Type attribute
    +method(arg1, arg2) return
}
```

These two ways output the same diagram.
```mermaid
classDiagram
class ClassName
    ClassName : +Type attribute
    ClassName : +method(arg1, arg2) return
```

### Generic Types
"Generic Types" such as `List<T>` can be represented by enclosing the type in `~` in fields, parameters, and return types.
```
classDiagram
class MyList~T~ {
    List~T~ data
    +add~T~(T number)
    +Double(T) MyList~T~
}
```
```mermaid
classDiagram
class MyList~T~ {
    List~T~ data
    +add~T~(T number)
    +Double(T) MyList~T~
}
```

### Visibility
To describe the visilibity of a class member, use optional notation before the member name.
+ `+` public
+ `-` private
+ `#` protected
+ `~` package/internal

### Modifiers
To include modifiers/classifiers, use optional notation "after" the `()` or return type.
+ `*` Abstract
  + e.g.: `someAbstractMethod()*` or `someAbstractMethod() : void*`
+ `$` Static
  + (method) e.g.: `someStaticMethod()$` or `someStaticMethod() : void$`
  + (field) e.g.: `Type someStaticField$`

## Inheritance
When 'Vehicle' class inherits from 'Car' class, it is represented as follows:
```mermaid
classDiagram
    Vehicle <|-- Car
```

## About
```mermaid
classDiagram
note "From Duck till Zebra"
Animal <|-- Duck
note for Duck "can fly\ncan swim\ncan dive\ncan help in debugging"
Animal <|-- Fish
Animal <|-- Zebra
Animal : +int age
Animal : +String gender
Animal: +isMammal()
Animal: +mate()
class Duck{
    +String beakColor
    +swim()
    +quack()
}
class Fish{
    -int sizeInFeet
    -canEat()
}
class Zebra{
    +bool is_wild
    +run()
}
```