```cpp
#include <iostream>
#include <vector>
#include <map>
#include <unordered_map>
#include <algorithm>
#include <string>
using namespace std;

int main()
{
    // Vector to store student marks
    vector<int> marks = {75, 90, 65, 85, 95};

    cout << "Original Marks:" << endl;

    for (int m : marks)
    {
        cout << m << " ";
    }

    cout << endl;

    // Sorting Marks
    sort(marks.begin(), marks.end());

    cout << "\nSorted Marks:" << endl;

    for (int m : marks)
    {
        cout << m << " ";
    }

    cout << endl;

    // find_if Algorithm
    auto it = find_if(marks.begin(), marks.end(),
                      [](int m)
                      {
                          return m > 80;
                      });

    if (it != marks.end())
    {
        cout << "\nFirst Mark Greater Than 80: " << *it << endl;
    }

    // Transform Algorithm
    transform(marks.begin(), marks.end(), marks.begin(),
              [](int m)
              {
                  return m + 5;
              });

    cout << "\nMarks After Adding 5:" << endl;

    for (int m : marks)
    {
        cout << m << " ";
    }

    cout << endl;

    // Map Container
    map<string, int> studentMarks;

    studentMarks["Shivam"] = 90;
    studentMarks["Rahul"] = 85;
    studentMarks["Aman"] = 75;

    cout << "\nStudent Marks Using Map:" << endl;

    for (auto s : studentMarks)
    {
        cout << s.first << " : " << s.second << endl;
    }

    // Unordered Map Container
    unordered_map<string, int> studentRoll;

    studentRoll["Shivam"] = 101;
    studentRoll["Rahul"] = 102;
    studentRoll["Aman"] = 103;

    cout << "\nStudent Roll Numbers:" << endl;

    for (auto s : studentRoll)
    {
        cout << s.first << " : " << s.second << endl;
    }

    return 0;
}
```
# Output:
```
Original Marks:
75 90 65 85 95 

Sorted Marks:
65 75 85 90 95 

First Mark Greater Than 80: 85

Marks After Adding 5:
70 80 90 95 100 

Student Marks Using Map:
Aman : 75
Rahul : 85
Shivam : 90

Student Roll Numbers:
Aman : 103
Rahul : 102
Shivam : 101
```
