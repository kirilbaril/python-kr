expenses = []
categories = ['Їжа', 'Транспорт', 'Розваги', 'Житло', 'Інше']

def add_expense():
    amount = float(input("Enter the amount: "))
    category = input("Enter the category: ")
    description = input("Enter the description: ")
    new_expense = {'amount': amount, 'category': category, 'description': description}
    expenses.append(new_expense)

def choose_category():
    print("Доступні категорії:")
    for i, category in enumerate(categories, 1):
        print(f"{i}. {category}")

    choice = input("Оберіть номер категорії або введіть нову: ")

    if choice.isdigit() and 1 <= int(choice) <= len(categories):
        return categories[int(choice) - 1]
    else:
        return input("Введіть нову категорію: ")


selected_category = choose_category()
print(f"Вибрана категорія: {selected_category}")

def generate_report():
    for expense in expenses:
        print(f"Amount: ${expense['amount']}, Category: {expense['category']}, Description: {expense['description']}")

while True:
    command = input("Enter a command (add/report/quit): ")

    if 'add' in command:
        add_expense()
    elif 'report' in command:
        generate_report()
    elif 'quit' in command:
        break
    else:
        print("Invalid command. Please try again.")


        def track_expenses_by_category(category):
            category_expenses = [expense for expense in expenses if expense['category'] == category]

            if not category_expenses:
                print(f"Немає витрат у категорії '{category}'.")
                return

            print(f"Звіт про витрати у категорії '{category}':")
            for expense in category_expenses:
                print(f"Сума: {expense['amount']}, Опис: {expense['description']}")


        # Приклад використання:
        expenses = [
            {'amount': 50, 'category': 'Їжа', 'description': 'Обід'},
            {'amount': 20, 'category': 'Транспорт', 'description': 'Проїзд'},
            {'amount': 100, 'category': 'Їжа', 'description': 'Вечеря'},
        ]

        track_expenses_by_category('Їжа')
        
