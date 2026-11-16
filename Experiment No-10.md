```cpp
#include <iostream>
#include <fstream>
#include <string>
using namespace std;

int main()
{
    fstream file;

    // Open File for Reading and Writing
    file.open("students.csv", ios::in | ios::out | ios::trunc);

    if (!file)
    {
        cout << "File Opening Failed!" << endl;
        return 1;
    }

    // Writing Student Records
    file << "RollNo,Name,Marks" << endl;
    file << "101,Shivam,90" << endl;
    file << "102,Rahul,85" << endl;
    file << "103,Aman,75" << endl;

    cout << "Student Records Written Successfully!" << endl;

    // tellp() - Get Current Writing Position
    cout << "\nCurrent Write Position: " << file.tellp() << endl;

    // seekp() - Move Writing Pointer
    file.seekp(0, ios::end);

    cout << "Write Position at End: " << file.tellp() << endl;

    // Append New Student Record
    file << "104,Arjun,88" << endl;

    // Flush Data
    file.flush();

    // seekg() - Move Reading Pointer to Beginning
    file.seekg(0, ios::beg);

    cout << "\nCurrent Read Position: " << file.tellg() << endl;

    // Reading Student Records
    string line;

    cout << "\nStudent Records:" << endl;

    while (getline(file, line))
    {
        cout << line << endl;
    }

    // tellg() - Get Reading Position
    cout << "\nFinal Read Position: " << file.tellg() << endl;

    // Close File
    file.close();

    return 0;
}
```