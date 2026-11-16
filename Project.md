# Hotel Management System
```cpp
#include <iostream>
#include <string>
using namespace std;

// Base Class
class Hotel
{
    protected:
        string hotelName;

    public:
        Hotel()
        {
            hotelName = "Grand Palace Hotel";
        }

        virtual void displayRooms() = 0;

        virtual ~Hotel() {}
};

// Derived Class
class Booking : public Hotel
{
    private:
        string customerName;
        string roomType;
        string bookingDate;
        int days;
        int price;
        int totalPrice;

    public:

        // Constructor
        Booking()
        {
            customerName = "";
            roomType = "";
            bookingDate = "";
            days = 0;
            price = 0;
            totalPrice = 0;
        }

        // Virtual Function
        void displayRooms() override
        {
            cout << "\nAvailable Rooms" << endl;
            cout << "1. Single Room - Rs.1000 per day" << endl;
            cout << "2. Double Room - Rs.1800 per day" << endl;
            cout << "3. Deluxe Room - Rs.2500 per day" << endl;
        }

        // Book Room Function
        void bookRoom()
        {
            int choice;

            cout << "\nEnter Customer Name: ";
            getline(cin >> ws, customerName);

            cout << "Enter Booking Date (DD/MM/YYYY): ";
            cin >> bookingDate;

            displayRooms();

            cout << "\nSelect Room Type (1-3): ";
            cin >> choice;

            switch(choice)
            {
                case 1:
                    roomType = "Single Room";
                    price = 1000;
                    break;

                case 2:
                    roomType = "Double Room";
                    price = 1800;
                    break;

                case 3:
                    roomType = "Deluxe Room";
                    price = 2500;
                    break;

                default:
                    cout << "Invalid Room Selection!" << endl;
                    return;
            }

            cout << "Enter Number of Days: ";
            cin >> days;

            if(days <= 0)
            {
                cout << "Invalid Number of Days!" << endl;
                return;
            }

            totalPrice = price * days;

            cout << "\nRoom Booked Successfully!" << endl;
        }

        // Friend Function Declaration
        friend void displayBill(Booking b);
};

// Friend Function
void displayBill(Booking b)
{
    cout << "\n========== HOTEL BOOKING RECEIPT ==========" << endl;

    cout << "Hotel Name: " << b.hotelName << endl;
    cout << "Customer Name: " << b.customerName << endl;
    cout << "Booking Date: " << b.bookingDate << endl;
    cout << "Room Type: " << b.roomType << endl;
    cout << "Price Per Day: Rs." << b.price << endl;
    cout << "Number of Days: " << b.days << endl;

    cout << "-------------------------------------------" << endl;

    cout << "Total Amount: Rs." << b.totalPrice << endl;

    cout << "===========================================" << endl;
}

int main()
{
    Booking b1;

    int choice;

    cout << "=================================" << endl;
    cout << "       HOTEL MANAGEMENT SYSTEM" << endl;
    cout << "=================================" << endl;

    do
    {
        cout << "\n1. Display Available Rooms" << endl;
        cout << "2. Book a Room" << endl;
        cout << "3. Display Booking Bill" << endl;
        cout << "4. Exit" << endl;

        cout << "\nEnter Your Choice: ";
        cin >> choice;

        switch(choice)
        {
            case 1:
                b1.displayRooms();
                break;

            case 2:
                b1.bookRoom();
                break;

            case 3:
                displayBill(b1);
                break;

            case 4:
                cout << "\nThank You for Visiting!" << endl;
                break;

            default:
                cout << "\nInvalid Choice!" << endl;
        }

    } while(choice != 4);
```
    return 0;
}
