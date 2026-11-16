```cpp
#include <iostream>
#include <string>
using namespace std;

int main()
{
    // Data Types
    int age = 20;
    float marks = 85.5;
    double salary = 25000.75;
    char grade = 'A';
    string name = "Shivam";
    bool pass = true;

    // Constant
    const float PI = 3.14;

    // Display Variables
    cout << "Name: " << name << endl;
    cout << "Age: " << age << endl;
    cout << "Marks: " << marks << endl;
    cout << "Salary: " << salary << endl;
    cout << "Grade: " << grade << endl;
    cout << "Pass: " << pass << endl;
    cout << "PI: " << PI << endl;

    // Operators
    int a = 10, b = 5;

    cout << "\nArithmetic Operators" << endl;
    cout << "Addition: " << a + b << endl;
    cout << "Subtraction: " << a - b << endl;
    cout << "Multiplication: " << a * b << endl;
    cout << "Division: " << a / b << endl;
    cout << "Modulus: " << a % b << endl;

    // Input and Output
    int num;
    cout << "\nEnter a number: ";
    cin >> num;

    cout << "You entered: " << num << endl;

    return 0;
}
```
# Output:
```
Name: Shivam
Age: 20
Marks: 85.5
Salary: 25000.8
Grade: A
Pass: 1
PI: 3.14

Arithmetic Operators
Addition: 15
Subtraction: 5
Multiplication: 50
Division: 2
Modulus: 0

Enter a number: 0
You entered: 0
```
