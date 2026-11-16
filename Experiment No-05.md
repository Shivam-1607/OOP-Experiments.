```cpp
#include <iostream>
using namespace std;

// Abstract Base Class
class Shape
{
    public:
        virtual void area() = 0;

        virtual ~Shape() {}
};

// Rectangle Class
class Rectangle : public Shape
{
    int length;
    int breadth;

    public:
        Rectangle(int l, int b)
        {
            length = l;
            breadth = b;
        }

        void area()
        {
            cout << "Area of Rectangle: "
                 << length * breadth << endl;
        }
};

// Triangle Class
class Triangle : public Shape
{
    int base;
    int height;

    public:
        Triangle(int b, int h)
        {
            base = b;
            height = h;
        }

        void area()
        {
            cout << "Area of Triangle: "
                 << 0.5 * base * height << endl;
        }
};

// Circle Class
class Circle : public Shape
{
    int radius;

    public:
        Circle(int r)
        {
            radius = r;
        }

        void area()
        {
            cout << "Area of Circle: "
                 << 3.14 * radius * radius << endl;
        }
};

int main()
{
    Rectangle r(5, 10);
    Triangle t(5, 10);
    Circle c(5);

    Shape* s;

    s = &r;
    s->area();

    s = &t;
    s->area();

    s = &c;
    s->area();

    return 0;
}
```
# Output:
```
Area of Rectangle: 50
Area of Triangle: 25
Area of Circle: 78.5
```
