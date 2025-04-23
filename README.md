# Contact-Management-System-By-Python
Contact Management System By Python Language


This is a Contact Management System built using:

Python's Tkinter library for the GUI

SQLite for the database

The app allows users to:

Add new contacts

View contacts in a table

Update contacts

Delete contacts

1. Window Setup
python
Copy
Edit
root = Tk()
root.title("Contact List")
# Sets the window in the center of the screen
...
root.config(bg="#6666ff")
This part sets up the main window and makes it centered and non-resizable.

📦 2. Global Variables
python
Copy
Edit
FIRSTNAME = StringVar()
LASTNAME = StringVar()
GENDER = StringVar()
AGE = StringVar()
ADDRESS = StringVar()
CONTACT = StringVar()
These variables are linked to input fields (entries), and used to gather user input or update UI fields.

💽 3. Database Interaction
Database()
Connects to a SQLite database file called pythontut.db

Creates a table member if it doesn't exist

Retrieves all records and displays them in the treeview

SubmitData()
Validates input fields

Inserts a new contact into the database

Refreshes the contact list

UpdateData()
Updates an existing contact based on selected record (mem_id)

Also refreshes the contact list

DeleteData()
Deletes a selected contact after confirmation

Refreshes the list

🪟 4. Update Window
OnSelected(event)
Triggered when the user double-clicks a contact in the table

Opens a pop-up window to edit contact

Loads selected data into the input fields

The Update button updates the data in the database

🪟 5. Add New Contact Window
AddNewWindow()
Opens a new window

Shows input fields

Pressing Save will insert data via SubmitData()

🧩 6. Main UI Layout
The GUI layout is broken into frames for organizing the UI:

Top: App title

MidLeft / MidRight: Buttons to add or delete contacts

TableMargin: Table showing all contacts (treeview with scrollbar)

python
Copy
Edit
tree = ttk.Treeview(...)  # Displays all contact entries
tree.bind('<Double-Button-1>', OnSelected)  # Opens edit window
▶️ 7. Program Start
python
Copy
Edit
if __name__ == '__main__':
    Database()
    root.mainloop()
This makes sure:

Data is loaded on startup

Tkinter event loop runs (mainloop())

🧠 Summary of Features
Create new contacts

Read: View all contacts in a table

Update contacts with a double-click

Delete contacts with a button
