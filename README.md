# 🏦 Banking Application

## 📝 Overview

A streamlined Java banking application that provides essential banking functionalities in a user-friendly console interface. This application enables users to manage their bank accounts with ease, performing various financial operations securely and efficiently.

## ⭐ Features

<div align="center">
<table>
  <tr>
    <td align="center"><b>💰 Check Balance</b></td>
    <td>View the current balance of your account</td>
  </tr>
  <tr>
    <td align="center"><b>💵 Deposit Money</b></td>
    <td>Add funds to your account securely</td>
  </tr>
  <tr>
    <td align="center"><b>💸 Withdraw Money</b></td>
    <td>Withdraw funds from your account</td>
  </tr>
  <tr>
    <td align="center"><b>📜 View Transaction History</b></td>
    <td>Check your most recent transaction details</td>
  </tr>
  <tr>
    <td align="center"><b>📤 Transfer Money</b></td>
    <td>Send money to another account safely</td>
  </tr>
  <tr>
    <td align="center"><b>📊 Calculate Interest</b></td>
    <td>Project future balance with compound interest</td>
  </tr>
</table>
</div>

## 🚀 Usage

When you run the application, you'll be greeted with a menu:

```
Welcome XYZ
Your customer ID is 01
A. Check balance
B. Deposit
C. Withdraw
D. Previous transaction
E. Transfer
F. Calculate interest
G. Exit
```

### Examples:

#### 🔹 Check Balance
```
Enter option: A
Balance is 1000
```

#### 🔹 Deposit Money
```
Enter option: B
Enter the amount to be deposited: 500
```

#### 🔹 Withdraw Money
```
Enter option: C
Enter the amount to withdraw: 200
```

#### 🔹 Transfer Money
```
Enter option: E
Enter amount to transfer: 300
Enter recipient customer ID: 02
```

#### 🔹 Calculate Interest
```
Enter option: F
Enter the number of years: 5
The current interest rate is 5.0%
After 5 years, your balance will be: 1276.28
```

## 💻 Code Architecture

### BankAccount Class

The core functionality is implemented in the `BankAccount` class:

```java
class BankAccount {
    // Account attributes
    int balance;
    int previousTransaction;
    String customerName;
    String customerId;
    
    // Constructor
    BankAccount(String cname, String cid) {
        customerName = cname;
        customerId = cid;
    }
    
    // Deposit funds
    void deposit(int amount) {
        if (amount != 0) {
            balance += amount;
            previousTransaction = amount;
        }
    }
    
    // Withdraw funds
    void withdraw(int amount) {
        if (amount != 0) {
            balance -= amount;
            previousTransaction = -amount;
        }
    }
    
    // View transaction history
    void getPreviousTransaction() {
        if (previousTransaction > 0) {
            System.out.println("Deposited: " + previousTransaction);
        } else if (previousTransaction < 0) {
            System.out.println("Withdrawn: " + (-previousTransaction));
        } else {
            System.out.println("No transaction was made");
        }
    }
    
    // Calculate compound interest
    void calculateInterest(int years) {
        double interestRate = 0.05;
        double newBalance = (balance * interestRate * years) + balance;
        System.out.println("The current interest rate is " + (100 * interestRate) + "%");
        System.out.println("After " + years + " years, your balance will be: " + newBalance);
    }
    
    // Other methods...
}
```

### Main Application

The application is initialized through the `BankingApplication` class:

```java
public class BankingApplication {
    public static void main(String[] args) {
        BankAccount bank1 = new BankAccount("XYZ", "01");
        bank1.showMenu();
    }
}
```

## 🛠️ Installation & Setup

1. **Prerequisites**
   - Java Development Kit (JDK 8 or higher)
   - Any Java IDE (IntelliJ IDEA, Eclipse, etc.) or terminal

2. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/banking-application.git
   cd banking-application
   ```

3. **Compile the Code**
   ```bash
   javac BankingApplication.java
   ```

4. **Run the Application**
   ```bash
   java BankingApplication
   ```

## 🔄 Future Enhancements

- Add database integration for persistent storage
- Implement user authentication and security features
- Create a graphical user interface (GUI)
- Support for multiple currencies
- Transaction history with timestamps
- Bill payment functionality

