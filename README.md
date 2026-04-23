# LOST-ITEM-LOGGER-SYSTEM
import json

FILE "lost_items.json"

#Load data def load items(): try: with open(FILLE, "r") as f: return json.load(1) except: return

#Save data

def save items(items): with open(FILE, "w") as f: json.dump(items, f

#Backup

def backup): with open("hackup.json", "w") as f: json.dump(load_items(), f)

#Main Program

lost items

load items()

while True: print("\n1. Report Lost Item") print("2. View Lost Items") print("3. Exit")

choice = int(input("Enter your choice:

if choice 1:

item= "item name"; input("Enter Item Name: "), "color": input("Enter Item Color: ")

"location": input("Enter Place Lost: "), "date": input("Enter Date (DD-MM-YYYY): "),

"contact": input("Enter Student Name: ")

1

lost items.append(item) save items(lost_items)

print("inLost item has been successfully recorded.") print("Thank you for helping maintain campus records.")

elif choice == 2:

if len(lost items) == 0: print("\nNo lost items reported yet.") else:

print("\n-Lost Item Details \n")

for item in lost items:

print("Item Name:", item["item_name"]) print("Color:", item["color"])

print("Lost At;", item["location"]) print("Date :", item["date"])

print("Reported By:", item["contact"])

print("\n")

elif choice3:

hackup()

print("\nThank you for using the system.") break

else: print("\nInvalid choice. Please try again.")
