# Airplane Ticket Booking System

## Overview
This project is a **Graphical User Interface (GUI)** application developed using Python's **Tkinter** library. It is designed to simulate an airplane ticket booking system where users can select flights, input customer details, choose ticket classes, calculate the total cost, apply taxes, and generate a billing receipt. The system also includes functionality to save, print, and share the bill via WhatsApp.

## Features
- **Customer and Flight Details Input**: Users can enter customer names, phone numbers, and flight details like departing and arriving locations, flight names, departing dates, and times.
- **Ticket Booking and Cost Calculation**: Users can select ticket classes (Economy, Premium, Business, First Class) and the number of tickets for each class. The system automatically calculates the total ticket cost, tax (18%), and the grand total.
- **Billing Area**: The system generates a billing receipt that displays customer and flight information, along with the breakdown of ticket costs and taxes.
- **Saving and Printing Bills**: Users can save the bill in a `.txt` file and print it.
- **Sharing the Bill via WhatsApp**: The app provides an option to share the bill directly through WhatsApp.
- **Clear Function**: Reset all input fields to start a new booking.
  
## Project Structure
### 1. **Importing Required Libraries**
The application uses multiple libraries:
- **Tkinter**: For creating the GUI components.
- **Messagebox**: For displaying alerts and errors.
- **Random**: For generating a random booking number.
- **Tempfile**: For handling temporary files used during the print process.
- **Webbrowser**: To open WhatsApp in a browser for bill sharing.
- **Datetime, Timedelta**: For working with date and time.
- **Calendar (DateEntry)**: To handle calendar selection for departing dates.

```python
from tkinter import *
from tkinter import messagebox
import random
import tempfile
import webbrowser
import urllib.parse
from datetime import datetime, timedelta
from calendar import monthrange
from tkinter import ttk
from tkcalendar import DateEntry
```

### 2. **Cost Calculation and Tax Application**
The function `total()` calculates the cost of tickets based on the number of tickets chosen for each class and their respective prices. It also calculates the tax (18% of the total ticket cost) and updates the grand total.

```python
def total():
    ...
```

### 3. **Bill Generation and Display**
The `bill_area()` function gathers all user inputs and generates a formatted bill in the text area (`textarea`). This bill includes flight details, ticket costs, and a breakdown of CGST and SGST taxes (both at 9%).

- Validations are done to ensure the user provides necessary input fields before generating the bill.
- The generated bill is displayed in a formatted text area with customized fonts and layout.

```python
def bill_area():
    ...
```

### 4. **Saving the Bill**
The `save_bill()` function prompts the user to save the generated bill. If confirmed, it saves the bill in a `.txt` file with the booking number as the filename.

```python
def save_bill():
    ...
```

### 5. **Printing the Bill**
The `print_bill()` function allows the user to print the bill. It uses the `tempfile` module to create a temporary text file and opens it for printing.

```python
def print_bill():
    ...
```

### 6. **Sharing the Bill on WhatsApp**
The `share_on_whatsapp()` function enables the user to share the generated bill with the phone number entered. It creates a WhatsApp URL and opens it in the default web browser.

```python
def share_on_whatsapp():
    ...
```

### 7. **Clear All Inputs**
The `clear_all()` function clears all input fields and the generated bill, allowing the user to start a new booking.

```python
def clear_all():
    ...
```

### 8. **GUI Components**
The GUI is built using various Tkinter widgets:
- **Labels**: To display text for customer and flight information.
- **Entries and Comboboxes**: To input customer and flight details, such as names, phone numbers, and flight class.
- **Text**: A text widget used to display the billing area.
- **Buttons**: Buttons are provided to trigger bill generation, print, save, and share actions.

```python
# GUI Components Example
customer = LabelFrame(root, text="CUSTOMER DETAILS", font=("Segoe UI", 15, "bold"), ...)
name = Label(customer, text="NAME", font=("Segoe UI", 15, "bold"), ...)
nameEntry = Entry(customer, font=("ARIAL", 15, "bold"), bd=7, width=18)
nameEntry.grid(row=1, column=1, padx=25)
...
```

### 9. **Flight and Customer Details**
Two sections for input:
- **Customer Details**: Name and Phone Number.
- **Flight Details**: Flight Name, Ticket ID, Departing and Arriving Locations, Departing Date, and Time.

```python
customer = LabelFrame(root, text="CUSTOMER DETAILS", font=("Segoe UI", 15, "bold"), ...)
flight = LabelFrame(root, text="FLIGHT DETAILS", font=("Segoe UI", 15, "bold"), ...)
```

### 10. **Billing Section**
Displays the total cost of the tickets, tax applied, and the grand total.

```python
costofticket = Label(billsect, text="COST OF TICKET", font=("Segoe UI", 11, "bold"), ...)
tax = Label(billsect, text="TAX", font=("Segoe UI", 11, "bold"), ...)
totalbutton = Button(billsect2, text="TOTAL", font=("Segoe UI", 12, "bold"), ...)
```

## How to Run the Application
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/airplane-ticket-booking-system.git
   ```
2. Install required libraries:
   ```bash
   pip install tkcalendar
   ```
3. Run the `main.py` file:
   ```bash
   python main.py
   ```

## Screenshots
_Add screenshots of the interface and generated bill here._

## Future Improvements
- Adding more validation checks.
- Including more airlines and destinations.
- Enhancing the user interface for better UX.
- Adding a payment gateway integration for real-time payments.
