To run:
create virtual enviroment,
pip install requirement.txt all

Wholesale Inventory & Sales Management System Documentation
Table of Contents
Overview
Features
Installation and Setup
User Guide
Managing Inventory
Recording Sales
Viewing Transactions
Printing Receipts
Technical Details
Troubleshooting
License
Overview
The Wholesale Inventory & Sales Management System is a Python-based desktop application designed for wholesale and retail shop owners to efficiently manage their inventory and sales operations. Built using Tkinter and pandas, the system operates entirely offline and stores all data in CSV files, making it ideal for businesses without reliable internet connections.

Key Benefits
Offline Operation: No internet connection required
Easy Data Management: All data stored in accessible CSV files
User-Friendly Interface: Intuitive design suitable for non-technical users
Receipt Printing: Integrated receipt printing functionality
Duplicate Prevention: Prevents duplicate stock entries
Features
Inventory Management
Add New Stock: Record product details including name, category, quantity, price, supplier, and date
Update Existing Stock: Modify product details as needed
Delete Stock: Remove discontinued items with confirmation
Search and Filter: Quickly find products by name, category, or supplier
Real-time Summary: View total items, inventory value, and low-stock alerts
Sales Management
Record Sales: Automatically deduct stock when items are sold
Customer Tracking: Record customer information with each transaction
Transaction History: Complete log of all sales transactions
Receipt Generation: Print or save sales receipts
Data Management
CSV Storage: All data stored in standard CSV format
Data Backup: Easy backup and sharing capabilities
Excel Integration: CSV files can be opened directly in Excel
Installation and Setup
System Requirements
Operating System: Windows, macOS, or Linux
Python: Version 3.6 or higher
Memory: Minimum 512MB RAM
Storage: 10MB free space
Printer (Optional): For receipt printing (thermal receipt printers like FT510 supported)
Step 1: Install Python
If Python is not already installed on your system:

Download Python from python.org
Run the installer and ensure "Add Python to PATH" is checked
Verify installation by opening Command Prompt/Terminal and typing:

Collapse
Copy
1
python --version
Step 2: Install Required Libraries
Open Command Prompt/Terminal and run:


Collapse
Copy
1
pip install pandas
Step 3: Download the Application
Download the inventory_app.py file
Save it to a folder on your computer (e.g., C:\InventoryApp)
Step 4: Run the Application
Navigate to the folder containing the application
Run the application using:

Collapse
Copy
1
python inventory_app.py
Optional: Create a Desktop Shortcut (Windows)
Right-click on your desktop and select "New" > "Shortcut"
Enter the location: python.exe "C:\InventoryApp\inventory_app.py" (adjust path as needed)
Name the shortcut "Inventory Management System"
Click "Finish"
Optional: Package as Executable
To distribute the application without requiring Python installation:

Install PyInstaller:

Collapse
Copy
1
pip install pyinstaller
Create the executable:

Collapse
Copy
1
pyinstaller --onefile --windowed --name "InventoryApp" inventory_app.py
Find the executable in the dist folder
User Guide
Managing Inventory
Adding New Stock
In the left panel, fill in the "Add New Stock" form:
Product Name: Enter the name of the product
Category: Select or enter a category
Quantity: Enter the initial stock quantity
Price (Rs.): Enter the selling price per unit
Supplier: Enter the supplier name
Click "Add Stock"
A success message will display with the generated Product ID
Updating Existing Stock
Go to the "Inventory" tab
Select an item from the inventory list by clicking on it
Click the "Update Selected" button below the list
In the dialog window, modify the fields as needed
Click "Save Changes"
Deleting Stock
Go to the "Inventory" tab
Select an item from the inventory list
Click the "Delete Selected" button
Confirm the deletion in the popup dialog
Searching and Filtering
In the left panel, enter a search term in the "Search" field
Select a filter option (All, Name, Category, or Supplier)
Click "Search" to filter the inventory list
To clear the filter, leave the search field blank and click "Search"
Recording Sales
Recording a New Sale
In the left panel, fill in the "Record Sale" form:
Product ID: Enter the ID of the product being sold
Quantity: Enter the quantity being sold
Customer: Enter the customer name
Check or uncheck "Print Receipt" as needed
Click "Record Sale"
The stock will be automatically updated and a receipt printed if selected
Viewing Transaction History
Go to the "Transactions" tab
View all sales transactions in the list
The list shows transaction ID, product details, customer, and date
Printing Receipts
Printing During Sale
When recording a sale, ensure "Print Receipt" is checked
After recording the sale, the receipt will automatically print
Reprinting a Receipt
Go to the "Transactions" tab
Select a transaction from the list
Click "Print Receipt"
The receipt will be sent to the default printer
Saving a Receipt
Go to the "Transactions" tab
Select a transaction from the list
Click "Save Receipt"
Choose a location to save the receipt as a text file
Understanding the Dashboard
The top panel displays key metrics:

Total Items: Number of unique products in inventory
Total Value: Combined value of all inventory in Rupees
Low Stock Items: Number of products with less than 10 units in stock
Technical Details
Application Architecture
The application is built using:

Tkinter: For the graphical user interface
Pandas: For data manipulation and CSV file handling
Python Standard Libraries: For file operations, date handling, etc.
Data Storage
inventory.csv: Stores all product information
transactions.csv: Stores all sales transaction records
Both files use standard CSV format and can be opened in spreadsheet applications like Excel or Google Sheets.

File Structure

Collapse
Copy
1
2
3
4
5
InventoryApp/
├── inventory_app.py       # Main application file
├── inventory.csv          # Inventory data (created after first use)
├── transactions.csv      # Transaction data (created after first use)
└── README.md             # This documentation
Product ID Generation
Product IDs are automatically generated as 6-digit numeric codes
Each ID is unique and randomly assigned
IDs are used for quick product lookup during sales
Receipt Format
Receipts are formatted for thermal receipt printers (48mm, 58mm, or 80mm paper width) and include:

Transaction ID
Date
Customer name
Product details
Payment information
Total amount
Printer Compatibility
The application supports most standard printers, including:

USB thermal receipt printers (like FT510)
Network printers
Bluetooth printers
Standard inkjet/laser printers
Troubleshooting
Common Issues and Solutions
Application Won't Start
Problem: The application doesn't launch when running the script.
Solution:

Verify Python is installed correctly by running python --version
Ensure pandas is installed: pip install pandas
Check for syntax errors in the script
Data Not Saving
Problem: Inventory or transaction data is not being saved.
Solution:

Verify the CSV files are not open in another application
Check file permissions for the application folder
Ensure the application has write access to the directory
Receipts Won't Print
Problem: Receipts are not printing when expected.
Solution:

Verify the printer is properly connected and powered on
Ensure the printer is set as the default printer
Test the printer with other applications
Check the "Print Receipt" checkbox is selected
Large File Size When Packaged
Problem: The executable file is very large (30-50MB).
Solution: This is normal as it includes the Python interpreter and all libraries. To reduce size:

Use UPX compression: pyinstaller --onefile --windowed --upx-dir path/to/upx inventory_app.py
Exclude unnecessary modules: pyinstaller --onefile --windowed --exclude-module matplotlib inventory_app.py
Duplicate Product Error
Problem: Application shows error when adding a product that seems unique.
Solution: The application prevents duplicate entries with the same name, category, and supplier. Check for existing products with similar details.

Low Stock Alert Not Showing
Problem: Low stock items are not being highlighted.
Solution: The application considers items with less than 10 units as low stock. Verify the quantity of items in your inventory.

Getting Help
For additional support:

Check the application logs for error messages
Verify all system requirements are met
Ensure you have the latest version of the application
Contact technical support with details of your issue
