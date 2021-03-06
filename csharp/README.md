# C Sharp Style Guide{} using c#

## Table of Contents

  1. [About the C# Coding Style Guide.](#AbouttheC#CodingStyleGuide)
  1. [Projects and Solutions.](#ProjectsandSolutions)
  1. [File Organization.](#FileOrganization)
  1. [Indentation.](#Indentation.)
  1. [Comments.](#Comments.)
  1. [Declarations.](#Declarations)
  1. [Statements.](#Statements)
  1. [White Space.](#WhiteSpace)
  1. [Naming Conventions.](#NamingConventions)
  1. [Namespaces.](#Namespaces)
  1. [Classes](#Classes)
  1. [#Types](#Types)
  1. [Interfaces](#Interfaces)
  1. [Enumeration Types](#EnumerationTypes)
  1. [Methods](#Methods)
  1. [Properties](#Properties)
  1. [Fields and Variables](#FieldsandVariables)
  1. [Constants](#Constants)
  1. [Code Layout](#CodeLayout)
  1. [Programming Practices](#ProgrammingPractices)
  1. [Code Examples.](#CodeExamples.)
  1. [C# Docs.](#Csharp-Docs)

  ## AbouttheC#CodingStyleGuide

   This document may be read as a guide to writing robust and reliable programs. It focuses on programs
written in C ♯, but many of the rules and principles are useful even if you write in another programming
language. 
  
**[⬆ back to top](#table-of-contents)**

  ## ProjectsandSolutions
- The name of the solution should match the name of its main project.
- Solution files (*.sln and *suo) in a single project solution should be placed inside the main source code.
- Solution files (.sln and .suo) in multiple project solutions should be placed inside the main directory, whereas each individual project should be in a subdirectory of this main solution directory.
- Use project folder to group source files that define types in a nested namespace. For example, create a folder named Configuration for all the source files containing types in the CompanyName.ProjectName.Configuration namespace.
- Use Pascal Case for source files and name them after the main type they contain. 

**[⬆ back to top](#table-of-contents)**

## FileOrganization
- Each source file should define one class or a few closely related classes or interface.
- The filenames should be the same as the class name, or the name of the most important of the classes.
- Source file name are Pascal Case.

**[⬆ back to top](#table-of-contents)**

##Indentation

**[⬆ back to top](#table-of-contents)**

## Comments
- Use two forms of comment: single-line comments and delimited comments. 
- Do not comment self-evident code:
```c#
//BAD
// declare user id
int userId;
```

**[⬆ back to top](#table-of-contents)**
##Declarations


**[⬆ back to top](#table-of-contents)**

##Statements


**[⬆ back to top](#table-of-contents)**

##White Space

**[⬆ back to top](#table-of-contents)**


## NamingConventions
- Spell words using correct English spelling. For the most part, avoid abbreviations.
- Make names clearly unique. Avoid similar-sounding names and similarly-spelled names.
- Use two naming convention: Pascal (PascalCase) and Camel (camelCase).
- Don't use abbreviations in type and member names
- Use all-uppercase style for acronyms.

**[⬆ back to top](#table-of-contents)**

## Namespaces
- The general rule for naming namespace is to use the company name followed by the technology name (project name) and optionally the feature
```c#
CompanyName.TechnologyName[.Feature][.Design]
Example: MyCompany.XRay.Data
```

- Ues Pascal Case
- Use plural namespace names if it is semantically appropriate.
```c#
System.Collections
vs
System.Collection
```
**[⬆ back to top](#table-of-contents)**
## Classes
- Use a noun or noun phrase to name a class.
- Use Pascal Case.
- Do not use the underscore character (_).

**[⬆ back to top](#table-of-contents)**

## Types
- Use Pascal Case for type names.
- Don’t use underscores inside type names.
**[⬆ back to top](#table-of-contents)**

## Interfaces
- Name interfaces with nouns or noun phrases, or adjectives that describe behavior. For example, the interface name IComponent uses a descriptive noun. The interface name ICustomAttributeProvider uses a noun phrase. The name IPersistable uses an adjective.
- Use Pascal Case
- Prefix interface names with the letter I, to indicate that the type is an interface.
- Do not use the underscore character (_).
- Avoid interfaces with more than 10-12 methods. If more methods are required, consider creating base interfaces from which you derive more complex interfaces.
- You might want to enclose the implementation of any interface in #region blocks to collapse and expand it easily only when a class implement multiple interfaces.

**[⬆ back to top](#table-of-contents)**
## EnumerationTypes
- Use Pascal Case for Enum types and value names. 
- Do not use an Enum suffix on Enum types names.
- Use a singular name for most Enum types, but use a plural name for Enum types that are bit fields. 
- Always add the FlagsAttribute to a bit field Enum type. 
- Mark bit-coded types with the Flags attribute.
**[⬆ back to top](#table-of-contents)**

## Methods
- Use verbs or verb phrases to name methods. 
- Use Pascal Case.

**[⬆ back to top](#table-of-contents)**
## Properties
- Use a noun or noun phrase to name properties. 
- Use Pascal Case.

**[⬆ back to top](#table-of-contents)**
## FieldsandVariables
- Use nouns, verbs, noun phrases, or abbreviations of nouns.
- If variable is bool type use ‘is’, ‘has’, etc, prefix.
```C#
public SomeMethod()
{
    bool isEnabled;
}
```

- Use camel Case for local variable names and parameter names.
- Use underscore (_) camel Case for member variable.
```C#
public class User
{
	private bool _isPrincipal;
}
```

- Do not use variable names that differ only by the use of uppercase and lowercase letters in the same method.
- Use meaningful names for fields and variables.
- Use letters and digits in field and variable names, but keep in mind that some letters and digits look similar:  letter O and digit 0.
- Use the explicit private keyword to define the scope of a type level field.
- Don’t declare multiple variables on the same line.
- Use the const keyword if the value of the constant is assigned at declaration otherwise use readonly if the constructor assigns the value.
- Avoid this keyword to reference a field or a property unless it helps make the code less ambiguous.
**[⬆ back to top](#table-of-contents)**
## Constants
- Use a noun or noun phrase to name constants.
- Use Uppercase and underscore to name constant.
```C#
private const string DAYS_IN_A_WEEK = 7;
```
**[⬆ back to top](#table-of-contents)**
## CodeLayout
- Put one statement per line.
- Always use C# predefined types rather than the aliases in System namespace.

```C#
// BAD
System.Object
System.String
System.Int32

// GOOD
object
string
int
```

- Do not provide public member variables. Use properties instead.
- Avoid methods with more than 5 arguments. Use structure for passing multiple arguments.
- Lines should not exceed 80 characters.
- Avoid writing very long methods. A method should typically have 1~25 lines of code. If a method has more than 25 lines of code, you must consider re factoring into separate methods.
- Compile with Warning Lever 4, don’t suppress specific warnings.
- Treat warning as errors
- Avoid having too large files. If a file has more than 400~500 lines of code, you must consider refactoring code into helper classes. 

**[⬆ back to top](#table-of-contents)**

# }