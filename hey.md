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
## STD::STRING MANUPULATIONS
### Concatenation
    
    string firstName = "John ";
    string lastName = "Doe";
    string fullName = firstName + lastName;
    cout << fullName;
    
or appending
    
    string firstName = "John ";
    string lastName = "Doe";
    string fullName = firstName.append(lastName);
    cout << fullName;
### Numbers and Strings
    You can't add number to a string, an error occurs
### String Length
To get the string length, use the length() function.
    string txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    cout << "The length of the txt string is: " << txt.length();
size() can be used too  
    string txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    cout << "The length of the txt string is: " << txt.size();
### Accesing strings
Strings are accessible by referring to their index number inside square brackets []
    
    string myString = "Hello";
    cout << myString[0];
    // Outputs H
    
    string myString = "Hello";
    myString[0] = 'J';
    cout << myString;
    // Outputs Jello instead of Hello
    
### Getline
std::cin.getline is a standard library function that can be used to read a line of text from the standard input stream (std::cin) and store it in a string. Here's an example of how to use std::cin.getline
    
    #include <iostream>
    #include <string>

    int main() {
        std::string line;
        std::cout << "Enter a line of text: ";
        std::getline(std::cin, line);
        std::cout << "You entered: " << line << std::endl;
        return 0;
    }
The std::cin.getline function takes two arguments: the first argument is the input stream (std::cin in this case), and the second argument is the string where the      line of text will be stored.

In this example, the program first outputs the message "Enter a line of text: " to prompt the user for input. Then, it calls std::getline(std::cin, line) to read a     line of text from the standard input stream and store it in the string line. Finally, the program outputs the contents of line to show the user what they entered.
## Pointers and Arrays
 Fixed arrays are implicitly converted to pointers. But in fact it's not a pointer its just a decayed version of the array.
    int array[5]{ 9, 7, 5, 3, 1 };

    // Deferencing an array returns the first element (element 0)
    std::cout << *array; // will print 9!

    char name[]{ "Jason" }; // C-style string (also an array)
    std::cout << *name << '\n'; // will print 'J'
    
As we can see from the code , it acts like a pointer.But what are the differences? The first difference is their size, while array's size is (type value * element     size) pointer has its unique size
    
### Arrays as function parameters
C++ does not copy an array when an array is passed into a function. When passing an array as an argument to a function, a fixed array decays into a pointer, and       the pointer is passed to the function:
    
    #include <iostream>

    void printSize(int* array)
    {
        // array is treated as a pointer here
        std::cout << sizeof(array) << '\n'; // prints the size of a pointer, not the size of the array!
    }

    int main()
    {
        int array[]{ 1, 1, 2, 3, 5, 8, 13, 21 };
        std::cout << sizeof(array) << '\n'; // will print sizeof(int) * array length

        printSize(array); // the array argument decays into a pointer here

        return 0;
    }
    
    This prints: 
    32
    4
Best practice

Favor the pointer syntax (*) over the array syntax ([]) for array function parameters because if you favor syntax (*) then you will know that youre working with pointers instead of an array.
## Pointer Arithmetic and Array Indexing
