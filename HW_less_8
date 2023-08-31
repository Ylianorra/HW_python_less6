import csv
PATH = 'Home_Work_8\contacts.csv'

def main_menu():
    print("Главное меню:")
    print("1. Показать контакты")
    print("2. Создать контакт")
    print("3. Найти контакт")
    print("4. Изменить контакт")
    print("5. Удалить контакт")
    print("6. Выход")

def show_contacts():
    with open(PATH, mode='r', encoding='UTF-8') as file:
        reader = csv.reader(file)
        for row in reader:
            print(row)
        print()
def create_contact():
    name = input("Введите Имя: ")
    email = input("Введите почту: ")
    phone = input("Введите телефон: ")

    with open(PATH, mode='a', encoding='UTF-8', newline='') as file:
        writer = csv.writer(file)
        writer.writerow([name, email, phone])
    print('Контакт успешно добавлен')
    print()

def find_contact():
    search_term = input("Введите имя для поиска: ")
    with open(PATH, mode='r', encoding='UTF-8') as file:
        reader = csv.reader(file)
        for row in reader:
            if search_term.lower() in row[0].lower():
                print(row)
                print()
                break
        else:
            print("Контакт не найден")
            print()

def update_contact():
    search_term = input("Введите имя контакта для изменения: ")
    with open(PATH, mode='r', encoding='UTF-8') as file:
        contacts = list(csv.reader(file))
        for i, row in enumerate(contacts):
            if search_term.lower() in row[0].lower():
                name = input("Введите новое имя: ")
                email = input("Введите новую почту: ")
                phone = input("Введите новый телефон: ")
                contacts[i] = [name, email, phone]
                break
        else:
            print("Контакт не найден")
            print()

    with open(PATH, mode='w', encoding='UTF-8', newline='') as file:
        writer = csv.writer(file)
        writer.writerows(contacts)
    print('Контакт успешно изменен')
    print()

def delete_contact():
    search_term = input("Введите имя контакта для удаления: ")
    with open(PATH, mode='r', encoding='UTF-8') as file:
        contacts = list(csv.reader(file))
        for row in contacts:
            if search_term.lower() in row[0].lower():
                contacts.remove(row)
                break
        else:
            print("Контакт не найден")
            print()

    with open(PATH, mode='w', encoding='UTF-8', newline='') as file:
        writer = csv.writer(file)
        writer.writerows(contacts)
    print('Контакт успешно удален')
    print()

while True:
    main_menu()
    print()
    choice = input("Выберите пункт меню: ")

    if choice == '1':
        show_contacts()
    elif choice == '2':
        create_contact()
    elif choice == '3':
        find_contact()
    elif choice == '4':
        update_contact()
    elif choice == '5':
        delete_contact()
    elif choice == '6':
        break
    else:
        print("Некорректный выбор пункта меню")
        print()

print()
print("До свидания! Программа завершена")