```cpp
#include <iostream>
#include <string>
using namespace std;

// Base Class
class Person
{
    protected:
        string name;
        int age;

    public:
        void getPerson()
        {
            cout << "Enter Name: ";
            cin >> name;

            cout << "Enter Age: ";
            cin >> age;
        }

        void displayPerson()
        {
            cout << "Name: " << name << endl;
            cout << "Age: " << age << endl;
        }
};

// Single Inheritance
class Student : public Person
{
    protected:
        int rollNo;

    public:
        void getStudent()
        {
            getPerson();

            cout << "Enter Roll Number: ";
            cin >> rollNo;
        }

        void displayStudent()
        {
            displayPerson();
            cout << "Roll Number: " << rollNo << endl;
        }
};

// Multilevel Inheritance
class GraduateStudent : public Student
{
    private:
        string researchTopic;

    public:
        void getGraduate()
        {
            getStudent();

            cout << "Enter Research Topic: ";
            cin >> researchTopic;
        }

        void displayGraduate()
        {
            displayStudent();
            cout << "Research Topic: " << researchTopic << endl;
        }
};

int main()
{
    GraduateStudent g1;

    cout << "Enter Graduate Student Details" << endl;

    g1.getGraduate();

    cout << "\nGraduate Student Details" << endl;

    g1.displayGraduate();

    return 0;
}
```