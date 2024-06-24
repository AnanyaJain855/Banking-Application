# Banking Application

## Description
This is a simple banking application that allows users to manage their bank accounts. Users can check their balance, deposit money, withdraw money, transfer money to another account, and calculate interest over a specified number of years. This project is implemented in Java.

## Features
- **Check Balance**: View the current balance of the account.
- **Deposit Money**: Add a specified amount of money to the account.
- **Withdraw Money**: Withdraw a specified amount of money from the account.
- **View Previous Transaction**: See the most recent transaction (deposit or withdrawal).
- **Transfer Money**: Transfer a specified amount of money to another account.
- **Calculate Interest**: Calculate the future balance based on a specified interest rate and number of years.

##Usage
1.	**Upon Running the Application**
Welcome XYZ
Your customer ID is 01
A. Check balance
B. Deposit
C. Withdraw
D. Previous transaction
E. Transfer
F. Calculate interest
G. Exit
2.	**Enter the Option: Type the corresponding letter to perform an action (e.g., A to check balance).**
Examples

•	Check Balance
Enter option: A
Balance is 1000

•	Deposit Money:
Enter option: B
Enter the amount to be deposited: 500

•	Withdraw Money:
Enter option: C
Enter the amount to withdraw: 200

•	Transfer Money:
Enter option: E
Enter amount to transfer: 300
Enter recipient customer ID: 02

•	Calculate Interest:
Enter option: F
Enter the number of years: 5
The current interest rate is 5.0%
After 5 years, your balance will be: 1276.28

#Code Snippets
**BankAccount Class**
class BankAccount {
    int balance;
    int previousTransaction;
    String customerName;
    String customerId;
    BankAccount(String cname, String cid) {
        customerName = cname;
        customerId = cid;
    }
    void deposit(int amount) {
        if (amount != 0) {
            balance += amount;
            previousTransaction = amount;
        }
    }
    void withdraw(int amount) {
        if (amount != 0) {
            balance -= amount;
            previousTransaction = -amount;
        }
    }
    void getPreviousTransaction() {
        if (previousTransaction > 0) {
            System.out.println("Deposited: " + previousTransaction);
        } else if (previousTransaction < 0) {
            System.out.println("Withdrawn: " + (-previousTransaction));
        } else {
            System.out.println("No transaction was made");
        }
    }
    void calculateInterest(int years) {
        double interestRate = 0.05;
        double newBalance = (balance * interestRate * years) + balance;
        System.out.println("The current interest rate is " + (100 * interestRate) + "%");
        System.out.println("After " + years + " years, your balance will be: " + newBalance);
    }
    // Other methods...
}
**Main Class**
public class BankingApplication {
    public static void main(String[] args) {
        BankAccount bank1 = new BankAccount("XYZ", "01");
        bank1.showMenu();
    }
}



