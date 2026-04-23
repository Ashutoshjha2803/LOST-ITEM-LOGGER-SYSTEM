# LOST-ITEM-LOGGER-SYSTEM
import json

FILE = "lost_items.json"

# Load data
def load_items():
    try:
        with open(FILE, "r") as f:
            return json.load(f)
    except:
        return []

# Save data
def save_items(items):
    with open(FILE, "w") as f:
        json.dump(items, f, indent=4)

# Backup
def backup():
    with open("backup.json", "w") as f:
        json.dump(load_items(), f, indent=4)

# Main Program
lost_items = load_items()

while True:
    print("\n1. Report Lost Item")
    print("2. View Lost Items")
    print("3. Exit")

    try:
        choice = int(input("Enter your choice: "))
    except ValueError:
        print("\nInvalid input. Please enter a number.")
        continue

    if choice == 1:
        item = {
            "item_name": input("Enter Item Name: "),
            "color": input("Enter Item Color: "),
            "location": input("Enter Place Lost: "),
            "date": input("Enter Date (DD-MM-YYYY): "),
            "contact": input("Enter Student Name: ")
        }

        lost_items.append(item)
        save_items(lost_items)

        print("\nLost item has been successfully recorded.")
        print("Thank you for helping maintain campus records.")

    elif choice == 2:
        if len(lost_items) == 0:
            print("\nNo lost items reported yet.")
        else:
            print("\n--- Lost Item Details ---\n")
            for item in lost_items:
                print("Item Name:", item["item_name"])
                print("Color:", item["color"])
                print("Lost At:", item["location"])
                print("Date:", item["date"])
                print("Reported By:", item["contact"])
                print("\n")

    elif choice == 3:
        backup()
        print("\nThank you for using the system.")
        break

    else:
        print("\nInvalid choice. Please try again.")
