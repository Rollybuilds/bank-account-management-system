
# Bank Account Management System

A simple console-based Bank Account Management System written in Python. It is built using Object-Oriented Programming (OOP) concepts and saves all account data and transactions in CSV files.

## What the project does

This project helps manage basic bank accounts. A user can create a Savings or Current account, deposit money, withdraw money, check the balance, and view the transaction history of an account. All data is saved in CSV files, so nothing is lost when the program is closed.

## How the project works

1. When the program starts, it loads the saved accounts from `accounts.csv` and the saved transactions from `transactions.csv`. If the files do not exist, it starts with an empty bank.
2. A menu is shown and the user selects an option (1 to 6).
3. Each account has a unique account number (starting from 1001), a holder name, an account type, and a balance.
4. A Savings account must always keep a minimum balance of 500. A Current account has no minimum balance.
5. Every deposit and withdrawal is recorded with the date, time, amount, and the balance after the transaction.
6. After every change, the data is saved to the CSV files automatically.
7. Invalid input (wrong account number, negative amount, insufficient balance, file errors) is handled with exception handling, so the program does not crash.

## How to run the project

**Requirements:** Python 3.8 or above. No extra libraries are needed.

**On your computer:**

```
python bank_account_system.py
```

**On Google Colab:**

1. Paste the code into a cell and run it.
2. Use the menu by typing a number and pressing Enter.
3. Choose option 6 to exit and save. The `accounts.csv` and `transactions.csv` files will be created in the Colab files panel.

## Classes used

| Class | Type | Purpose |
|---|---|---|
| `BankError` | Custom exception | Raised when an action cannot be completed (insufficient balance, account not found, etc.) |
| `Account` | Abstract base class (`abc`) | Defines the common structure and actions (deposit, withdraw) for all accounts, with private attributes and abstract methods `account_type()` and `min_balance()` |
| `SavingsAccount` | Derived class | Inherits from `Account`. Minimum balance is 500 |
| `CurrentAccount` | Derived class | Inherits from `Account`. No minimum balance |
| `Bank` | Manager class | Stores all accounts and transactions, and handles creating accounts, deposits, withdrawals, history, and saving data |

## Main features implemented

- **Create accounts:** creates a Savings or Current account with an automatic account number
- **Deposit money:** adds money to an account
- **Withdraw money:** removes money from an account while following the minimum balance rule
- **Check balance:** shows the account details and the current balance
- **Maintain transaction history:** records every transaction with date, time, amount, and balance
- **Save data:** reads and writes data using CSV files (`accounts.csv` and `transactions.csv`)

## OOP concepts demonstrated

| Concept | Where it is used |
|---|---|
| Classes & Objects | `Account`, `SavingsAccount`, `CurrentAccount`, `Bank` |
| Encapsulation | Private attributes (`__balance`, `__holder`, `__acc_no`) with getters and setters using `@property` |
| Inheritance | `SavingsAccount` and `CurrentAccount` inherit from `Account` |
| Abstraction | `Account` is an abstract class using the `abc` module |
| File Handling | Data is read from and written to `accounts.csv` and `transactions.csv` |
| Exception Handling | `BankError`, `FileNotFoundError`, `ValueError`, and `OSError` are handled |

## Program output (Screenshots)

### 1. Main menu
The program shows the menu and asks the user to enter a choice.

![Main Menu](https://github.com/Rollybuilds/bank-account-management-system/blob/648aef6abe283436ec58ce1d7d621fe5fe5d94f8/Main%20Menu.png)

### 2. Create account (Choice 1)
The user enters the name, account type, and opening deposit. An account number is generated.

![Create Account](https://github.com/Rollybuilds/bank-account-management-system/blob/648aef6abe283436ec58ce1d7d621fe5fe5d94f8/Create%20Account.png)

### 3. Deposit money (Choice 2)
The user enters the account number and the amount. The new balance is shown.

![Deposit Money](https://github.com/Rollybuilds/bank-account-management-system/blob/648aef6abe283436ec58ce1d7d621fe5fe5d94f8/Deposit%20money.png)

### 4. Withdraw money (Choice 3)
The user enters the account number and the amount. The new balance is shown, or an error if the balance is not enough.

![Withdraw Money](https://github.com/Rollybuilds/bank-account-management-system/blob/648aef6abe283436ec58ce1d7d621fe5fe5d94f8/withdraw%20money.png)

### 5. Check balance (Choice 4)
The account details and the current balance are displayed.

![Check Balance](https://github.com/Rollybuilds/bank-account-management-system/blob/648aef6abe283436ec58ce1d7d621fe5fe5d94f8/Check%20balance.png)

### 6. Transaction history (Choice 5)
All transactions of the account are displayed with date, type, amount, and balance.

![Transaction History](https://github.com/Rollybuilds/bank-account-management-system/blob/648aef6abe283436ec58ce1d7d621fe5fe5d94f8/Transaction%20History.png)

### 7. Exit and save data (Choice 6)
The data is saved in the CSV files and the program closes.

![Exit and Save](https://github.com/Rollybuilds/bank-account-management-system/blob/648aef6abe283436ec58ce1d7d621fe5fe5d94f8/Exit.png)

## Project files

```
bank_account_system/
├── bank_account_system.py   # main program
├── accounts.csv             # saved account records
├── transactions.csv         # saved transaction history
├── screenshots/             # output screenshots
└── README.md                # project documentation
```
