General Coding Guidelines
=========================

Language
--------

The preferred spelling is American English in all code parts and at all times to ensure readability for every user regardless 
of country, state or culture.

Comments
--------

Code should always be self-explaining over the use of comments so if commenting just write in style of comment should say "why"
am I doing something, not "what" is it doing. The only comments should be things that may need clarification.

In code and implementation files you can use either the // or the /* */ syntax; however, is much more common and preferred for 
single line comments. Be consistent with how you comment and what style you use where. In code and implementation files of the 
C# family, you however have to use /// .Net syntax when you put comments to class and member documentation.

Always try to keep comments rare and small to prevent wasting the code with allegedly important notes but provide as much
information as possible at well-chosen code parts.

Documentation
-------------

An exceptional case where you need to add comments to classes, functions and members is in order to keep code documentation in
header files for those users that are supposed to work with their IDE’s documentation ability. A class/function comment should 
provide the reader with enough information to know how and when to use the class/function, as well as any additional 
considerations necessary to correctly use the class if not self-explaining.

```
/** 
 A brief description about what this is useful for 
*/
```

This comment decorating documented code parts should never be more than 2/3 of the code page wide and no more than 3 lines of 
text height to ensure legibility. Single line comments may be without conclusive dot where detailed descriptions always end up 
with an ending dot on each sentence.

```
/**
 A brief description about what this is useful for. 
 Any further details following the brief description if necessary. 
*/
```

It is not necessary to document redundant or implied code parts like operators or such code that was added by inheritance and is
already documented in the base file it inherits from. Do not state the obvious, in particular, do not literally describe what 
code does, unless the behavior is nonobvious at all.

When writing C#, there exists a different documentation style using the XML summary-tag inside a comment. Write your in-code 
documentation as usual except use this XML style tags

```
///<summary>
/// A brief description about what this is useful for
///</summary>
```

Classes
--------

Classes should be organized with the reader in mind rather than the writer. Since most readers will be using the public 
interface of the class, that should be declared first, followed by the class's private implementation.

Naming
------

The first letter of each word in an enumeration, method, structure or class name is capitalized, and there is usually no 
underscore between words where variable names start with a lowercase letter. Variable, enumeration, method, structure and 
class names should be clear, unambiguous, and descriptive. The greater the scope of the name, the greater the importance of 
a good, descriptive name. Avoid over-abbreviation.

Some type names should be prefixed using an additional capital in the case of:

* Interfaces/Anonymous Classes should be marked with the I letter

Type and variable names are nouns where method names are verbs that describe the method's effect, or describe the return value 
of a method that has no effect.

All variables should be declared one at a time so that a comment on the meaning of the variable can be provided. You can use an 
optional blank line for grouping variables and methods.

All letters of each word in a macro are capitalized, and there are underscores between words where function-like macro names 
consist only of lowercase lettered words. Macro names should be clear, unambiguous, and descriptive. The greater the scope of
the name, the greater the importance of a good, descriptive name. Avoid over-abbreviation.

C++ Alias
---------

You can use an alias declaration to declare a name to use as a synonym for a previously declared type. Those names follow the 
naming rules and start either with a capitalized or lower case letter.

This types are aliases for build-in native types and common structures/classes defined:

* **bool** for boolean values
* **char** for a character
* **byte** for generic unsigned bytes (1 byte)
* **uint8** for unsigned bytes (1 byte)
* **int8** for signed bytes (1 byte)
* **uint16** for unsigned short integers (2 bytes)
* **int16** for signed short integers (2 bytes)
* **uint32** for unsigned integers (4 bytes)
* **int32** for signed integers (4 bytes)
* **uint64** for unsigned long integers (8 bytes)
* **int64** for signed long integers (8 bytes)
* **float** for single precision floating point numbers (4 bytes)
* **double** for double precision floating point numbers (8 bytes)

C++ 11
---------

To provide a compiler independent and portable code base, you should refrain from using C++11, 14, 17 and compiler-specific 
language features unless they are wrapped in preprocessor macros or conditionals and used sparingly.

Namespaces
----------

Namespaces subdivide the global scope into distinct, named scopes, and so are useful for preventing name collisions in the
global scope and separating sets of functionality into unique self-describing chapters in usage and design.

With few exceptions, all functionality is included into at least one full-qualified namespace encapsulating the project. You 
may use sub namespaces if necessary but never use using-directives nor anonymous namespaces.

Use namespaces to encapsulate global enumerations from conflicting with other similar named types and to encapsulate global 
functions into a class like subset not wasting the root namespace too much.

Pointer and References
----------------------

When passing an object to a function or retrieving a return type from a function do this always by reference or pointer. Both 
references and pointers can be used to change variables inside a function and can also be used to save copying objects when 
passed as arguments to functions or returned from functions, to get efficiency gain.

Use pointers when the passed arguments can be declared as void and the function provides certain error checking on them, 
otherwise use references as they can never be void and should be assumed as non-zero.

Const Correctness
-----------------

*const* is documentation as much as it is a compiler directive, so all code should strive to be const-correct. This includes 
passing function arguments by const pointer or reference if those arguments are not intended to be modified by the function 
and flagging methods as const if they do not modify the object.

Never use const on a return type, as this inhibits move semantics for complex types and will give compile warnings for built-in 
types. This rule only applies to the return type itself, not the target type of a pointer or reference being returned.

Strong Typing
-------------

You should use strong typing as a simple and efficient tool for improving code expressiveness whenever possible. Do not use 
the ‘auto’ keyword in C++ code or the ‘var’ keyword in C#. You must always be explicit about the type you're initializing. This 
means that the type must be plainly visible to the reader.

Brackets
--------

Are a major part of the coding language and also a tool for structuring your code. You may use opening and closing brackets in 
a single code line as well as on multiple lines. You should avoid using an opening bracket in the same row following an 
instruction but placing the closing bracket a few lines behind.
