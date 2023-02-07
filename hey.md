# THIS MY C++ NOTING PLACEE
## C Type strings
### A brief look to C type strings
C type strings are strings which are initialized by array of characters, and each character can be manipulated by [] operator 
```

#include <iostream>

int main()
{
    char myString[]{ "string" };
    myString[1] = 'p';
    std::cout << myString << '\n';

    return 0;
}
```
### Manipulating these strings (<cstring> header)
#### strcpy()
    Allows you to copy a string to another string. More commonly, this is used to assign a value to a string:
```
#include <cstring>
#include <iostream>

int main()
{
    char source[]{ "Copy this!" };
    char dest[50];
    std::strcpy(dest, source);
    std::cout << dest << '\n'; // prints "Copy this!"

    return 0;
}
```
#### strlen()
    This function directly prints the length of a string, excluding the null terminator whereas std::size() operator prints the size of an array.
### HOWEVER, AVOID USING C-STYLE STRINGS, USE Use STD::STRING OR STD::STRING_VIEW INSTEAD OF C-STYLE STRINGS CUZ THEY'RE MORE EASY,FLEXIBLE AND SAFE.
