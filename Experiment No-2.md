```cpp
#include <iostream>
#include <string>
using namespace std;

class BankAccount
{
    private:
        int accountNumber;
        double balance;

    protected:
        string accountHolder;

    public:
        BankAccount(int acc, string name, double bal)
        {
            accountNumber = acc;
            accountHolder = name;
            balance = bal;
        }

        void deposit(double amount)
        {
            balance = balance + amount;
            cout << "Amount Deposited: " << amount << endl;
        }

        void display()
        {
            cout << "Account Number: " << accountNumber << endl;
            cout << "Account Holder: " << accountHolder << endl;
            cout << "Balance: " << balance << endl;
        }

        double getBalance()
        {
            return balance;
        }
};

class SavingsAccount : public BankAccount
{
    private:
        double interestRate;

    public:
        SavingsAccount(int acc, string name, double bal, double rate)
            : BankAccount(acc, name, bal)
        {
            interestRate = rate;
        }

        void calculateInterest()
        {
            double interest = getBalance() * interestRate / 100;
            cout << "Interest: " << interest << endl;
        }

        void showAccount()
        {
            display();
            cout << "Account Holder: " << accountHolder << endl;
            cout << "Interest Rate: " << interestRate << "%" << endl;
        }
};

int main()
{
    SavingsAccount s1(101, "Shivam", 10000, 5);

    cout << "Bank Account Details" << endl;

    s1.showAccount();

    s1.deposit(2000);

    s1.calculateInterest();

    return 0;
}
```