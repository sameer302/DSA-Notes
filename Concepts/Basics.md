# C++

## Boiler Plate Code
- We have C++ Standard Library which is a huge collection of pre-written classes and functions such as cout, cin, endl, etc.
- All these classes and functions are present in different header files which need to be included during runtime in order to use them.
- Example of header files are, iostream, vector, string, etc. 
- The C++ Standard Library puts functions like cout, cin, string, etc. inside a namespace called std. So their actual names are:
  - std::cout
  - std::cin
- This namespace avoid conflicts between user-defined keywords and pre-existing keywords. Without namespaces, the compiler would not know what are we referring to.
- In order to avoid writing std every time, we can write, 'using namespace std' at the begining of code. This can be costly in large codebases as we are importing complete namespace. In such cases using std:cout is a better option.
- Considering the above points, a standard code block for C++ looks like,

```cpp
#include<iostream>
using namespace std;

int main(){
cout << "Hello";
return 0;
}
```

## Input and Output

### Input
- For this we use **cin** function present in **iostream** header file.
- **cin** takes input sequentially considering spaces, tabs and newlines as separators.
- Example. The input code for following input format will be
4 6
1 2 3 4

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main(){
  int n, k;
  cin >> n >> k;

  vector<int> arr(n);

  for (int i = 0; i < n; i++){
    cin >> arr[i];
  }

  return 0;
}
```

### Output
- For this we use **cout** function present in **iostream** library.
- Examples of using cout
```cpp
cout << "Hello";
// Hello

int x = 5;
cout << "Value of x = " << x;
// Value of x = 5

cout << "Hello" << endl;
cout << "World";
// Hello
// World

cout << "Hello\n";
cout << "World";
```
