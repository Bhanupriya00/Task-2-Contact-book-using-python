class ContactBook:
    def __init__(self):
        self.contacts = {}

    def add_contact(self, name, phone_number):
        self.contacts[name] = phone_number
        print(f"Contact {name} added successfully.")

    def search_contact(self, name):
        if name in self.contacts:
            print(f"Name: {name}, Phone Number: {self.contacts[name]}")
        else:
            print(f"Contact {name} not found.")

    def display_contacts(self):
        if not self.contacts:
            print("Contact book is empty.")
        else:
            print("Contact List:")
            for name, phone_number in self.contacts.items():
                print(f"Name: {name}, Phone Number: {phone_number}")

def main():
    contact_book = ContactBook()

    while True:
        print("\nContact Book Menu:")
        print("1. Add Contact")
        print("2. Search Contact")
        print("3. Display Contacts")
        print("4. Exit")

        choice = input("Enter your choice (1-4): ")

        if choice == "1":
            name = input("Enter contact name: ")
            phone_number = input("Enter phone number: ")
            contact_book.add_contact(name, phone_number)

        elif choice == "2":
            name = input("Enter contact name to search: ")
            contact_book.search_contact(name)

        elif choice == "3":
            contact_book.display_contacts()

        elif choice == "4":
            print("Exiting Contact Book. Goodbye!")
            break

        else:
            print("Invalid choice. Please enter a number between 1 and 4.")

if __name__ == "__main__":
    main()
