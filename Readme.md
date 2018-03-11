
# C++ tips on how to write code that will help to manage the challenges that comes with large code bases

1. **Asserts** Always use asserts on the things that should never happen as per the algorithm (i.e programmers assumptions)
```e.g. assert(numIndicec >= 3) // the number of indices are always supposed to be greater than or equal to 3 ```

- Assert should not be used in user inputs because they can be anything and happens at runtime.
- Asserts should be ideally enabled only in debug builds and compiled out from production/release builds

- Advantages: Asserts helps to find bugs at the very early stages.
- Asserts acts as a micro unittests.
- Asserts acts as a self documentation.

*So use asserts early and often* :+1:

2. **const correctness** In C++ we have the advantages of using const in most of the places. 

- Prefer to use const for local variables that do not change.
- Prefer to use const for method arguments that are not POD. Pass them by const ref or const pointer.
- Prefer to use const for member functions that do not modify class state.
- const early const often.

- Advantages: The beauty of const which most people underestimate is correctness that it imposes on the code.
If one developer forgets to put a const in the variable which was supposed to be const, another developer can modify it without getting any warning from compiler. if developer put const in the variable and if another developer tries to modify it, he/she will get the warning from the compiler

- Another beauty of constness is that it acts as a self documentation to the developer about the state of the code. constness makes reading code very easy as const assures the developer to not care about its state. Thus making one less variable that developer has to hold in its working memory.

- The last benefit is if developer makes member function const which does not modify the state of the objects, then it assures the developer about its thread safety automatically (given you do not have any global states). This helps to call the member functions on threads safely. Also assures that method call will be side effect free.
