Here’s a basic Python-based Trust Bank system that includes:

Account creation

Deposit

Withdraw

Balance check



---

Trust Bank – Sample Python Code

# trust_bank.py

class Account:
    def __init__(self, name, balance=0):
        self.name = name
        self.balance = balance

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            print(f"{amount} deposited. New balance: {self.balance}")
        else:
            print("Invalid amount")

    def withdraw(self, amount):
        if amount > self.balance:
            print("Insufficient funds")
        elif amount <= 0:
            print("Invalid amount")
        else:
            self.balance -= amount
            print(f"{amount} withdrawn. Remaining balance: {self.balance}")

    def check_balance(self):
        print(f"Current balance: {self.balance}")


# Sample usage
def main():
    print("Welcome to Trust Bank!")
    name = input("Enter your name: ")
    account = Account(name)

    while True:
        print("\n1. Deposit\n2. Withdraw\n3. Check Balance\n4. Exit")
        choice = input("Choose an option: ")

        if choice == '1':
            amount = float(input("Enter amount to deposit: "))
            account.deposit(amount)
        elif choice == '2':
            amount = float(input("Enter amount to withdraw: "))
            account.withdraw(amount)
        elif choice == '3':
            account.check_balance()
        elif choice == '4':
            print("Thank you for using Trust Bank!")
            break
        else:
            print("Invalid option. Try again.")

if __name__ == "__main__":
    main()
