
# Task 1 — Read the inventory Open inventory.json using a with block and load its contents into a variable called inventory. Print the total number of books currently in the file.
import json
•	Imports Python’s built-in JSON module.
•	This module allows reading and writing JSON (JavaScript Object Notation) data.
•	Required because inventory.json is a JSON file.
with open("inventory.json", "r") as file:
•	open("inventory.json", "r") → opens the file named inventory.json in read mode (r).
•	with → creates a context manager that automatically closes the file after use (best practice).
•	as file → assigns the opened file object to the variable file so it can be used inside the block.
    inventory = json.load(file)
•	json.load(file) → reads JSON content from the file object.
•	Converts JSON data into a Python structure (usually a list or dictionary).
•	Stores the result in the variable inventory.
•	In this task, inventory is expected to be a list of books.
print("Total number of books:", len(inventory))
•	len(inventory) → calculates the number of items in the inventory list.
•	"Total number of books:" → text label for clarity.
•	print(...) → displays the result on the screen.
•	Example output:
Total number of books: 2





# Task 2 — Update and save Append new_book to the inventory list. Write the updated list back to inventory.json using a with block, with an indentation of 4 spaces.
new_book = {"title": "Atomic Habits", "author": "James Clear", "price": 14.99, "in_stock": True}
•	Creates a Python dictionary representing a book.
•	Keys:
o	title → book name
o	author → author name
o	price → book price
o	in_stock → availability (True = available)

 Read existing inventory
with open("inventory.json", "r") as file:
•	Opens inventory.json in read mode (r).
•	with ensures file is automatically closed after reading.
•	File object stored in variable file.
    inventory = json.load(file)
•	Reads JSON data from the file.
•	Converts JSON into a Python object (usually a list of books).
•	Stores it in variable inventory.
 Append new book
inventory.append(new_book)
•	Adds the new book dictionary to the end of the inventory list.
•	Now inventory contains the old books + new book.
 Write updated inventory back
with open("inventory.json", "w") as file:
•	Opens the same file in write mode (w).
•	Write mode replaces old file content with new data.
    json.dump(inventory, file, indent=4)
•	Writes the updated inventory list back to inventory.json.
•	json.dump() converts Python object → JSON format.
•	indent=4 makes the JSON file neatly formatted (pretty printed).
print(inventory)
•	Displays the updated inventory list in the console.
•	Confirms the new book was added.








# Task 3 — Display the inventory Read the updated file again and print each book's details in the following format:
Title: The Alchemist | Author: Paulo Coelho | Price: $12.99
Title: 1984 | Author: George Orwell | Price: $9.99
Title: Atomic Habits | Author: James Clear | Price: $14.99
with open("inventory.json", "r") as file:
•	Opens the file inventory.json in read mode (r).
•	with ensures the file is automatically closed after reading.
•	The opened file object is stored in variable file.
    updated_inventory = json.load(file)
•	Reads JSON data from the file.
•	Converts JSON into a Python object (expected: list of book dictionaries).
•	Stores the result in variable updated_inventory.
for book in updated_inventory:
•	Starts a loop over each item in the inventory list.
•	Each item (book) is a dictionary representing one book.
•	Loop runs once per book.
    print(f"Title: {book['title']} | Author: {book['author']} | Price: ${book['price']}")
•	Uses an f-string (formatted string) to print book details.
•	book['title'] → gets the title value from the dictionary.
•	book['author'] → gets the author.
•	book['price'] → gets the price.
•	Output format example:

