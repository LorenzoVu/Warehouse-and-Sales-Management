# Warehouse and Sales Management

This Python script manages a simple warehouse and records sales. It allows you to add products, view inventory, record sales, and calculate profits. Warehouse and sales data are saved to a text file.

## Features

*   **Add Products**: Add new products to the warehouse or update the quantity of existing products.
*   **List Products**: Display the list of products currently in the warehouse with available quantity and selling price.
*   **Record Sale**: Allows you to record a sale of one or more products, updating the quantity in the warehouse and recording the sale for profit calculation.
*   **Calculate Profits**: Calculates gross and net profits based on recorded sales and the purchase prices of sold products.
*   **Data Saving**: Automatically saves current warehouse and sales data to a text file specified by the user at the beginning of the program.
*   **Data Loading**: Loads data from an existing file on program startup, if the file exists.
*   **Help**: Displays a list of available commands.
*   **Close**: Exits the program.

## How to use the script

1.  Run the code cell.
2.  You will be asked to enter the warehouse file name (with extension). If the file does not exist, it will be created.
3.  Once the file is loaded or created, the program will wait for a command input.
4.  Enter one of the available commands (`aggiungi`, `elenca`, `vendita`, `profitti`, `aiuto`, `chiudi`) to interact with the program.
5.  Follow the on-screen instructions for each command.

## Code Structure

*   `items_list`: A list of dictionaries representing products in the warehouse. Each dictionary contains `Nome` (Name), `Quantità` (Quantity), `Prezzo di acquisto` (Purchase Price), and `Prezzo di vendita` (Selling Price).
*   `sold_items_list`: A temporary list of dictionaries that tracks items sold during a single "vendita" (sale) operation.
*   `sold_items_list_fixed`: A list of dictionaries that records all sales made for profit calculation.
*   `start()`: The main function that handles user interaction and calls other functions based on the entered command.
*   `help()`: Displays available commands.
*   `is_valid_name(name)`: Checks if the product name is valid (only letters and spaces).
*   `add_items()`: Manages adding or updating products in the warehouse.
*   `view_items()`: Displays products in the warehouse.
*   `find_product()`: Checks if a product exists in the warehouse.
*   `find_product_price()`: Returns the selling price of a product.
*   `update_quantity()`: Updates the quantity of a product in the warehouse after a sale.
*   `update_sold_items_list_fixed()`: Updates the list of recorded sales.
*   `sold_item()`: Manages the process of recording a sale.
*   `revenue()`: Calculates and displays profits.
*   `read_file()`: Reads warehouse and sales data from a file.
*   `update_file()`: Writes current warehouse and sales data to a file.
*   `check_and_create_file()`: Checks if a file exists and creates it if necessary.
*   `main()`: The program's entry point that handles file loading and starts user interaction.

## Data File Format

The data file is a simple text file with warehouse and sales data separated by commas. The first section contains warehouse data, followed by a blank line, the line "Vendite:" (Sales:), another blank line, and then the sales data.
