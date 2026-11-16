```cpp
#include <iostream>
#include <cstring>
using namespace std;

class Student
{
    private:
        char* name;

    public:

        // Default Constructor
        Student()
        {
            name = new char[8];
            strcpy(name, "Unknown");
            cout << "Default Constructor Called" << endl;
        }

        // Parameterized Constructor
        Student(const char* n)
        {
            name = new char[strlen(n) + 1];
            strcpy(name, n);
            cout << "Parameterized Constructor Called" << endl;
        }

        // Copy Constructor
        Student(const Student& s)
        {
            name = new char[strlen(s.name) + 1];
            strcpy(name, s.name);
            cout << "Copy Constructor Called" << endl;
        }

        // Move Constructor
        Student(Student&& s) noexcept
        {
            name = s.name;
            s.name = nullptr;
            cout << "Move Constructor Called" << endl;
        }

        // Copy Assignment Operator
        Student& operator=(const Student& s)
        {
            if (this != &s)
            {
                delete[] name;
                name = new char[strlen(s.name) + 1];
                strcpy(name, s.name);
            }

            return *this;
        }

        // Move Assignment Operator
        Student& operator=(Student&& s) noexcept
        {
            if (this != &s)
            {
                delete[] name;
                name = s.name;
                s.name = nullptr;
            }

            return *this;
        }

        // Destructor
        ~Student()
        {
            delete[] name;
            cout << "Destructor Called" << endl;
        }

        void display()
        {
            if (name != nullptr)
                cout << "Student Name: " << name << endl;
            else
                cout << "Student Name: Empty" << endl;
        }
};

int main()
{
    Student s1;
    s1.display();

    Student s2("Shivam");
    s2.display();

    Student s3 = s2;
    s3.display();

    Student s4 = static_cast<Student&&>(s2);
    s4.display();

    Student s5;
    s5 = s3;
    s5.display();

    Student s6;
    s6 = static_cast<Student&&>(s4);
    s6.display();

    return 0;
}
```
# Output:
```
Default Constructor Called
Student Name: Unknown
Parameterized Constructor Called
Student Name: Shivam
Copy Constructor Called
Student Name: Shivam
Move Constructor Called
Student Name: Shivam
Default Constructor Called
Student Name: Shivam
Default Constructor Called
Student Name: Shivam
Destructor Called
Destructor Called
Destructor Called
Destructor Called
Destructor Called
Destructor Called
```
