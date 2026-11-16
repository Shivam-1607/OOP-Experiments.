```cpp
#include <iostream>
#include <exception>
using namespace std;

// Base Exception Class
class BankingException : public exception
{
    public:
        const char* what() const noexcept
        {
            return "Banking Exception Occurred";
        }
};

// Insufficient Balance Exception
class InsufficientBalance : public BankingException
{
    public:
        const char* what() const noexcept
        {
            return "Insufficient Balance!";
        }
};

// Invalid Amount Exception
class InvalidAmount : public BankingException
{
    public:
        const char* what() const noexcept
        {
            return "Invalid Amount!";
        }
};

// Bank Account Class
class BankAccount
{
    private:
        double balance;

    public:
        BankAccount(double b)
        {
            balance = b;
        }

        void deposit(double amount)
        {
            if (amount <= 0)
            {
                throw InvalidAmount();
            }

            balance = balance + amount;

            cout << "Amount Deposited: " << amount << endl;
        }

        void withdraw(double amount)
        {
            if (amount <= 0)
            {
                throw InvalidAmount();
            }

            if (amount > balance)
            {
                throw InsufficientBalance();
            }

            balance = balance - amount;

            cout << "Amount Withdrawn: " << amount << endl;
        }

        void display()
        {
            cout << "Current Balance: " << balance << endl;
        }
};

int main()
{
    BankAccount b1(5000);

    try
    {
        b1.display();

        b1.deposit(2000);

        b1.withdraw(1000);

        b1.withdraw(10000);
    }

    catch (InsufficientBalance& e)
    {
        cout << "Error: " << e.what() << endl;
    }

    catch (InvalidAmount& e)
    {
        cout << "Error: " << e.what() << endl;
    }

    catch (BankingException& e)
    {
        cout << "Error: " << e.what() << endl;
    }

    b1.display();

    return 0;
}
```
# Output:
```
Current Balance: 5000
Amount Deposited: 2000
Amount Withdrawn: 1000
Error: Insufficient Balance!
Current Balance: 6000
```
