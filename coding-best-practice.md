# Coding Best Practice / Guide

KISS - Keep It Simple, Stupid

YAGNI - “You Aren’t Gonna Need It;” developers often make things too general to cater to future requirements, and this is usually not a good idea.

DRY - “Don’t Repeat Yourself,” reminds us that duplicate code leads to more code, and more code is harder and more expensive to maintain.

SOLID:
- Single responsibility principle - each class only does one thing and every class or module only has responsibility for one part of the software’s functionality
- Open-closed principle - existing, well-tested classes will need to be modified when something needs to be added. Yet, changing classes can lead to problems or bugs. Instead of changing the class, you simply want to extend it.
- Liskov substitution principle - every derived class should be substitutable for its parent class
- Interface segregation principle - it’s better to have a lot of smaller interfaces than a few bigger ones. Clients should not be forced to implement interfaces they do not use.”
- Dependency inversion principle - high level modules should not depend upon low level modules. Both should depend on abstractions.” Further, “abstractions should not depend on details. Details should depend upon abstractions

NASA:
- Simple Control Flow - don't use goto, setjmp, longjmp, recursion
- Limit All Loops - hard limit the number of iterations in all loops
- Don't Use the Heap - use only stack memory, don't use malloc or free
- Limit Function Size - function should be no longer than 60 lines
- Practice Data Hiding - declare variables in the lowest scope required
- Check Return Values - explicitly cast all ignored return values to a void type
- Limit the Preprocessor - limit the use of the C preprocessor to file inclusions and very simple conditional macros, don't use conditional compilation
- Restrict Pointers Use - pointers should not be able to be dereferenced more than one layer at a time, also don't use function pointers
- Be Pedantic - compile with all warnings enabled and in pedantic mode, analyze the code with multiple static code analyzers with different rulesets, also unit test the code

GOOGLE:
- tabs vs spaces - use only spaces and indent two spaces at a time. use spaces for indentation. do not use tabs in your code
- type deduction - use type deduction only if it makes the code clearer to readers who aren't familiar with the project or if it makes the code safer. do not use it to merely avoid the inconvenience of writing an explicit type
-  ownership and smart pointers - limiting the use of dynamically allocated memory to the lowest point possible, using it only in the class that it was allocated by. if two classes need to use the data, use a Smart pointer to explicitly pass ownership of the data from one class to another
- exceptions - do not use exceptions at all. the benefits of using exceptions outweigh the costs especially in new projects. however, for existing code the introduction of exceptions has implications on all dependent code. if exceptions can be propagated beyond a new project, it also becomes problematic to integrate the new project into existing exception free code
- inheritance - limit the use of implementation inheritance and instead use only interface inheritance or use composition instead
