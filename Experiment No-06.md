```cpp
#include <iostream>
using namespace std;

class Complex
{
    public:
        int real;
        int img;

    public:

        // Default Constructor
        Complex()
        {
            real = 0;
            img = 0;
        }

        // Function Overloading
        void add(int r)
        {
            real = real + r;
        }

        void add(int r, int i)
        {
            real = real + r;
            img = img + i;
        }

        // Operator Overloading
        Complex operator+(Complex c)
        {
            Complex result;

            result.real = real + c.real;
            result.img = img + c.img;

            return result;
        }

        // Display Function
        void display()
        {
            cout << "The complex number is: "
                 << real << " + " << img << "i" << endl;
        }
};

int main()
{
    Complex c1;

    c1.add(5);
    c1.display();

    Complex c2;

    c2.add(3, 4);
    c2.display();

    Complex c3 = c1 + c2;

    c3.display();

    return 0;
}
```
# Output:
```
The complex number is: 5 + 0i
The complex number is: 3 + 4i
The complex number is: 8 + 4i
```
