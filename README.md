# ATM machine project by using function in python
<br>
class ATM:
    def __init__(self, balance=0, pin="1234"):
        self.balance = balance
        self.pin = pin

    def check_pin(self, entered_pin):
        return entered_pin == self.pin

    def check_balance(self):
        print("Current Balance:", self.balance)

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            print("Deposited:", amount)
        else:
            print("Invalid amount")

    def withdraw(self, amount):
        if amount > self.balance:
            print("Insufficient balance")
        elif amount <= 0:
            print("Invalid amount")
        else:
            self.balance -= amount
            print("Withdrawn:", amount)


# Main Program
atm = ATM(1000, "1234")

entered_pin = input("Enter PIN: ")

if atm.check_pin(entered_pin):
    while True:
        print("\n1. Check Balance")
        print("2. Deposit")
        print("3. Withdraw")
        print("4. Exit")

        choice = input("Choose option: ")

        if choice == "1":
            atm.check_balance()

        elif choice == "2":
            amount = int(input("Enter amount: "))
            atm.deposit(amount)

        elif choice == "3":
            amount = int(input("Enter amount: "))
            atm.withdraw(amount)

        elif choice == "4":
            print("Thank you!")
            break

        else:
            print("Invalid choice")

else:
    print("Wrong PIN")
