```cpp
#include <iostream>
#include <string>
using namespace std;

template <typename T>
class Stack
{
    private:
        T* arr;
        int top;
        int maxsize;

    public:

        Stack(int size)
        {
            maxsize = size;
            arr = new T[maxsize];
            top = -1;
        }

        void push(const T& value)
        {
            if (top >= maxsize - 1)
            {
                cout << "Stack Overflow!!" << endl;
                return;
            }

            top++;
            arr[top] = value;
        }

        void pop()
        {
            if (top == -1)
            {
                cout << "Stack is Empty" << endl;
                return;
            }

            cout << "Deleted Element: " << arr[top] << endl;
            top--;
        }

        void display()
        {
            if (top == -1)
            {
                cout << "Stack is Empty" << endl;
                return;
            }

            cout << "Stack Elements:" << endl;

            for (int i = top; i >= 0; i--)
            {
                cout << arr[i] << endl;
            }

            cout << endl;
        }

        ~Stack()
        {
            delete[] arr;
        }
};

int main()
{
    Stack<int> s1(5);

    s1.push(10);
    s1.push(20);
    s1.push(30);

    cout << "Integer Stack:" << endl;
    s1.display();

    Stack<float> s2(3);

    s2.push(1.1);
    s2.push(2.2);

    cout << "Float Stack:" << endl;
    s2.display();

    Stack<string> s3(5);

    s3.push("Hello");
    s3.push("World");

    cout << "String Stack:" << endl;
    s3.display();

    return 0;
}
```
# Output:
```
Integer Stack:
Stack Elements:
30
20
10

Float Stack:
Stack Elements:
2.2
1.1

String Stack:
Stack Elements:
World
Hello
```
