# Food Ordering System

Welcome to the **Food Ordering System**, a C-based console application designed to manage food orders efficiently. This project provides a straightforward interface for placing, removing, searching, and displaying orders, as well as calculating total sales. It's perfect for small restaurants, cafes, or anyone looking to streamline their order management process.

## Table of Contents
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)

## Features
- **Place Orders**: Add new food orders with details like dish name, quantity, and total cost.
- **Remove Orders**: Delete individual orders by order number.
- **Search Orders**: Find specific orders by their order number and view details.
- **Display All Orders**: View a list of all orders with their details.
- **Calculate Total Sales**: Compute the total sales across all orders.
- **Clear All Data**: Reset the system by formatting all records.
- Simple console-based interface with clear prompts and navigation.
- Dynamic memory management using a linked list for efficient order storage.

## Installation
To set up the **Food Ordering System**, follow these steps:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/food-ordering-system.git
   cd food-ordering-system
   ```

2. **Compile the Code**:
   Ensure you have a C compiler installed (e.g., GCC). Compile the source code using:
   ```bash
   gcc -o food_ordering main.c
   ```

3. **Run the Program**:
   On Windows:
   ```bash
   food_ordering.exe
   ```
   On Linux/Mac:
   ```bash
   ./food_ordering
   ```

   **Note**: The program uses `system("cls")` for screen clearing, which is Windows-specific. For Linux/Mac, replace it with `system("clear")` or remove it for portability. The code is otherwise cross-platform compatible, using standard C libraries (`stdio.h`, `stdlib.h`, `string.h`).

## Usage
Upon running the program, you'll see the main menu:
```
                FOOD ORDERING SYSTEM
                ---------------------------------

                enter:
                1 To Place Order
                2 To Remove Order
                3 To Display Order Information
                4 To Display All Orders
                5 To Calculate Total Sales
                6 To Clear all data
                7 To Exit

                Enter your choice:
```
- Enter a number (1–7) to select an option.
- Follow the on-screen prompts to input or retrieve order details.
- The program runs in a loop, allowing multiple operations until you choose to exit (option 7).

## How It Works
The program uses a singly linked list to store order records, where each node contains:
- Order Number (auto-incremented serial number)
- Dish Name (string)
- Quantity (integer)
- Total Cost (integer)

### Key Functions
- **Place Order (`add()`)**: Prompts for dish name, quantity, and total cost, assigns a unique order number, and appends the order to the linked list.
- **Remove Order (`delp()`)**: Deletes an order by its order number, updating the linked list accordingly.
- **Search Order (`search()`)**: Finds an order by its order number and displays its details, or notifies if not found.
- **Display All Orders (`display()`)**: Lists all orders with their details in a formatted manner.
- **Calculate Total Sales (`tc()`)**: Sums the total cost of all orders to display the total sales.
- **Clear All Data (`delt()`)**: Resets the linked list and order number counter, clearing all records.

### Data Structure
The program uses a linked list (`struct node`) for dynamic storage. Each node holds order data and a pointer to the next node. The `start` pointer tracks the list's head, and the `on` variable maintains the order number sequence. Memory is allocated dynamically using `malloc` and freed during deletion.

### Error Handling
- Checks for empty lists before performing operations.
- Notifies users if an order number is not found during search or deletion.
- Handles invalid menu choices with an error message.
- Ensures proper input handling with `getchar()` to clear input buffer before reading strings.
