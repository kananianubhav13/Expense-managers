# Expense-managers
# Expense Manager in Python

expenses = []  # List to store expense records

def add_expense():
    """Add a new expense with description and amount."""
    try:
        description = input("Enter expense description: ")
        amount = float(input("Enter expense amount: "))
        if amount <= 0:
            print("Amount must be greater than zero.")
            return
        expenses.append({"description": description, "amount": amount})
        print("✅ Expense added successfully!\n")
    except ValueError:
        print("❌ Invalid amount! Please enter a number.\n")

def view_expenses():
    """View all expenses with total."""
    if not expenses:
        print("No expenses recorded yet.\n")
        return

    print("\n=== Expense List ===")
    total = 0
    for i, expense in enumerate(expenses, start=1):
        print(f"{i}. {expense['description']} - ₹{expense['amount']}")
        total += expense['amount']
    print(f"---------------------\nTotal Expenses: ₹{total}\n")

def menu():
    """Main menu for the expense manager."""
    while True:
        print("=== Expense Manager ===")
        print("1. Add Expense")
        print("2. View Expenses")
        print("3. Exit")
        choice = input("Choose an option (1-3): ")

        if choice == "1":
            add_expense()
        elif choice == "2":
            view_expenses()
        elif choice == "3":
            print("Goodbye! 👋")
            break
        else:
            print("❌ Invalid choice! Please select 1, 2, or 3.\n")


# Run the program
if __name__ == "__main__":
    menu()
