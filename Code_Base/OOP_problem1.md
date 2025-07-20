# Create a Class for Bank Account

### Problem Statement:
###### Create a class BankAccount with the following:

Fields: accountNumber, accountHolderName, balance

###### Methods:

 deposit(amount) – Adds the amount to balance.

withdraw(amount) – Deducts the amount if sufficient balance is available, otherwise print "Insufficient balance".

display() – Prints account details.

###### Requirements:

Create at least 2 objects of BankAccount.

Demonstrate class and object usage.


# Answer:
```java
class BankAccount {
    private String accountNumber;
    private String accountHolderName;
    private double balance;

    // Constructor
    public BankAccount(String accountNumber, String accountHolderName, double balance) {
        this.accountNumber = accountNumber;
        this.accountHolderName = accountHolderName;
        this.balance = balance;
    }

    // Deposit method
    public void deposit(double amount) {
        balance += amount;
        System.out.println("Deposited: " + amount + ", New Balance: " + balance);
    }

    // Withdraw method
    public void withdraw(double amount) {
        if (amount <= balance) {
            balance -= amount;
            System.out.println("Withdrawn: " + amount + ", Remaining Balance: " + balance);
        } else {
            System.out.println("Insufficient balance");
        }
    }

    // Display account details
    public void display() {
        System.out.println("Account No: " + accountNumber + ", Holder: " + accountHolderName + ", Balance: " + balance);
    }

    public static void main(String[] args) {
        BankAccount acc1 = new BankAccount("1001", "Sibasish", 5000);
        acc1.deposit(2000);
        acc1.withdraw(1500);
        acc1.display();

        BankAccount acc2 = new BankAccount("1002", "John", 3000);
        acc2.display();
    }
}
```
