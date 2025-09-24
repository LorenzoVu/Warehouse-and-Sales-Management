# Warehouse and Sales Management

This Python script manages a simple warehouse and records sales. It allows you to add products, view inventory, record sales, and calculate profits. Warehouse and sales data are saved to a text file.

## Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [How to Use](#how-to-use)
- [Commands Reference](#commands-reference)
- [Code Structure](#code-structure)
- [Data File Format](#data-file-format)
- [Examples](#examples)
- [File Structure](#file-structure)
- [Contributing](#contributing)
- [License](#license)

## Features

*   **Add Products**: Add new products to the warehouse or update the quantity of existing products.
*   **List Products**: Display the list of products currently in the warehouse with available quantity and selling price.
*   **Record Sale**: Allows you to record a sale of one or more products, updating the quantity in the warehouse and recording the sale for profit calculation.
*   **Calculate Profits**: Calculates gross and net profits based on recorded sales and the purchase prices of sold products.
*   **Data Saving**: Automatically saves current warehouse and sales data to a text file specified by the user at the beginning of the program.
*   **Data Loading**: Loads data from an existing file on program startup, if the file exists.
*   **Help**: Displays a list of available commands.
*   **Close**: Exits the program.

## Requirements

- Python 3.6 or higher
- Jupyter Notebook (for running the `.ipynb` file)
- No external dependencies required (uses only Python standard library)

## Installation

1. Clone or download this repository:
   ```bash
   git clone https://github.com/LorenzoVu/Warehouse-and-Sales-Management.git
   cd Warehouse-and-Sales-Management
   ```

2. Open the Jupyter notebook:
   ```bash
   jupyter notebook Progetto_gestionale.ipynb
   ```

3. Run the code cell to start the program.

## How to Use

1. Run the code cell in the Jupyter notebook.
2. You will be asked to enter the warehouse file name (with extension). If the file does not exist, it will be created.
3. Once the file is loaded or created, the program will wait for a command input.
4. Enter one of the available commands to interact with the program.
5. Follow the on-screen instructions for each command.

## Commands Reference

| Command | Italian | Description |
|---------|---------|-------------|
| `aggiungi` | Add | Add new products to the warehouse or update quantity of existing products |
| `elenca` | List | Display all products currently in the warehouse |
| `vendita` | Sale | Record a sale transaction |
| `profitti` | Profits | Calculate and display gross and net profits |
| `aiuto` | Help | Display available commands |
| `chiudi` | Close | Exit the program |

### Detailed Command Usage

- **aggiungi (Add Products)**:
  - Enter product name (letters and spaces only)
  - For existing products: enter additional quantity to add
  - For new products: enter quantity, purchase price, and selling price

- **elenca (List Products)**:
  - Displays all products with available quantity > 0
  - Shows product name, quantity, and selling price

- **vendita (Record Sale)**:
  - Enter product name (must exist in warehouse)
  - Enter quantity to sell (must not exceed available stock)
  - Option to add multiple products to the same sale
  - Displays total sale amount

- **profitti (Calculate Profits)**:
  - Shows gross revenue (total sales)
  - Shows net profit (gross revenue - purchase costs)

## Code Structure

*   `items_list`: A list of dictionaries representing products in the warehouse. Each dictionary contains `Nome` (Name), `Quantità` (Quantity), `Prezzo di acquisto` (Purchase Price), and `Prezzo di vendita` (Selling Price).
*   `sold_items_list`: A temporary list of dictionaries that tracks items sold during a single "vendita" (sale) operation.
*   `sold_items_list_fixed`: A list of dictionaries that records all sales made for profit calculation.

### Functions

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

The data file is a simple text file with warehouse and sales data separated by commas. The file structure consists of:

1. **Header line**: `Nome,Quantità,Prezzo di acquisto,Prezzo di vendita`
2. **Warehouse data**: One line per product with comma-separated values
3. **Blank line**
4. **Sales header**: `Vendite:` (Sales:)
5. **Sales data header**: `Nome,Quantità,Prezzo di vendita`
6. **Sales data**: One line per sale record with comma-separated values

### Example File Content:
```
Nome,Quantità,Prezzo di acquisto,Prezzo di vendita
Apple,50,1.0,1.5
Banana,30,0.8,1.2

Vendite:
Nome,Quantità,Prezzo di vendita
Apple,10,1.5
Banana,5,1.2
```

## Examples

### Adding a New Product
```
Inserisci un comando: aggiungi
Nome del prodotto: Apple
Quantità: 50
Prezzo di acquisto: 1.0
Prezzo di vendita: 1.5
AGGIUNTO: 50 X Apple
```

### Listing Products
```
Inserisci un comando: elenca
PRODOTTO             QUANTITA        PREZZO    
Apple                50              €1.5       
Banana               30              €1.2       
```

### Recording a Sale
```
Inserisci un comando: vendita
Nome: Apple
Quantità: 10
Aggiungere un altro prodotto? (Si/No): no
VENDITA REGISTRATA
-10 X Apple: €1.5
Totale: €15.00
```

### Viewing Profits
```
Inserisci un comando: profitti
Profitto: lordo=€15.00 netto=€10.00
```

## File Structure

```
Warehouse-and-Sales-Management/
│
├── Progetto_gestionale.ipynb    # Main Jupyter notebook with the Python code
├── README.md                    # This documentation file
└── [data_files]                 # User-created data files (e.g., warehouse.txt)
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Make your changes
4. Add tests if applicable
5. Commit your changes (`git commit -am 'Add new feature'`)
6. Push to the branch (`git push origin feature/new-feature`)
7. Create a Pull Request

## License

This project is open source and available under the [MIT License](LICENSE).