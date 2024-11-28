# Banking System Application

This is a Python-based banking system application that provides basic functionality such as user account creation, login, deposit, withdrawal, and balance checking. It uses **MySQL** as the database backend to store user data and **Tkinter** for the graphical user interface.

---

## Features

1. **User Account Management**:
   - Sign up for new user accounts.
   - Secure login with username and password validation.

2. **Banking Transactions**:
   - Deposit funds into the user account.
   - Withdraw funds with balance validation.
   - View current account balance.

3. **Database Integration**:
   - MySQL database for persistent user data storage.
   - Stores and updates user balances in real-time.

4. **Command-Line Interface**:
   - Interactive text-based interface for user operations.

---

## File Structure

- **`main.py`**: The main Python script containing the banking system logic and MySQL integration.

---

## Prerequisites

1. **Python 3.7+**:
   Ensure you have Python installed. Download from [Python Official Website](https://www.python.org/downloads/).

2. **MySQL Database**:
   - Install and set up a MySQL server.
   - Create a database named `one` with the following table structure:

     ```sql
     CREATE DATABASE one;
     USE one;
     CREATE TABLE Users (
         username VARCHAR(50) PRIMARY KEY,
         password VARCHAR(50) NOT NULL,
         balance FLOAT NOT NULL
     );
     ```

3. **Required Python Libraries**:
   Install the necessary libraries using `pip`:
   ```bash
   pip install mysql-connector-python
   ```

---

## How to Run

1. Clone or download the repository to your local system.

2. Update the MySQL connection credentials in the `main.py` file:
   ```python
   connection = mysql.connect(user="your_username", database="one", password="your_password")
   ```

3. Run the `main.py` script:
   ```bash
   python main.py
   ```

4. Use the command-line interface to:
   - Sign up for a new account.
   - Log in to an existing account.
   - Perform banking operations like deposit, withdrawal, and balance checking.

---

## Code Overview

### `User` Class
Represents a user in the system with the following methods:
- `deposit(amount)`: Adds funds to the user’s balance and updates the database.
- `withdraw(amount)`: Deducts funds if the balance is sufficient and updates the database.
- `view_balance()`: Displays the current balance.
- `add_amount()`: Inserts the user data into the database.
- `exit()`: Updates the user balance in the database upon exit.

### `One` Class
Manages the overall banking system with these functionalities:
- `new_user(username, password)`: Creates a new user account.
- `log_in(username, password)`: Logs in a user after validating credentials.
- `home_screen()`: Main menu to navigate between sign-up, login, and exit options.
- `options(user)`: User-specific menu for performing deposit, withdrawal, balance checking, or exit.

---

## Example Workflow

1. **Sign Up**:
   - Enter a username and password to create a new account.
   - The account is initialized with a balance of $0.

2. **Log In**:
   - Enter your username and password to access your account.

3. **Perform Transactions**:
   - Choose options like deposit, withdraw, or check balance.
   - Transactions are processed, and the balance is updated in the database.

4. **Exit**:
   - Exit the application, ensuring all data is saved.

---

## Future Enhancements

- Add a **GUI interface** for a more user-friendly experience using Tkinter.
- Implement password hashing for better security.
- Add features like account transfer, transaction history, and email notifications.
- Optimize database queries for performance.

---

## Contact

For inquiries or support, please contact:  
**Email**: [your-email@example.com](mailto:your-email@example.com)  
**Phone**: +1 123-456-7890
