# USD Currency Converter Application

## Overview

This repository contains the code and documentation for Task 5 of my Python Developer internship at **Main Flow Services and Technologies**. The task involved developing a USD currency converter application with a graphical user interface (GUI) using Python. The application allows users to input an amount in USD and convert it to various other currencies based on the latest exchange rates.

## Project Description

The goal of this task was to create a user-friendly and accurate currency converter application that can be used to convert USD to a range of other currencies. The application was built using Python's Tkinter library for the GUI and the `requests` library to fetch live exchange rates from an external API.

## Learning Objectives

- **Environment Setup:** Install and configure Python along with necessary libraries, including Tkinter for GUI development and `requests` for API calls.
- **Currency Conversion Logic:** Implement the logic to accurately convert USD to selected currencies using real-time exchange rates.
- **GUI Design:** Create a graphical user interface that is intuitive and easy to use, with features like input fields, dropdown menus, and buttons for conversion and rate updates.

## Tools and Technologies

- **Python 3.x**
- **Tkinter (for GUI)**
- **Requests (for API calls)**


## How to Run the Application

### Prerequisites

Ensure that Python 3.x is installed on your machine. The following Python libraries are required:

- Tkinter (usually included with Python)
- Requests

You can install the `requests` library using pip:

```bash
pip install requests
```

To get the API You need to sign up the website to get the own API for free
https://currencylayer.com/dashboard


### Running the Application

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/Dj-gamer007/usd-currency-converter.git
   cd usd-currency-converter/src
   ```

2. **Run the Converter Application:**

   ```bash
   python converter.py
   ```

3. **Using the Application:**

   - Enter the amount in USD that you wish to convert.
   - Select the target currency from the dropdown menu.
   - Click the "Convert" button to see the converted amount.
   - Use the "Refresh Rates" button to update the exchange rates to the latest available data.

## Example Code Snippet

Here’s a small snippet showing the conversion logic:

```python
import requests

def get_exchange_rate(target_currency):
    url = f"https://api.exchangerate-api.com/v4/latest/USD"
    response = requests.get(url)
    data = response.json()
    return data['rates'].get(target_currency)

def convert_usd_to_currency(usd_amount, target_currency):
    rate = get_exchange_rate(target_currency)
    if rate:
        return usd_amount * rate
    else:
        return "Error: Invalid target currency or rate unavailable."
```

## Features

- **Real-time Exchange Rates:** Fetches the latest exchange rates from a reliable API.
- **User-Friendly GUI:** Simple and intuitive interface using Tkinter.
- **Multiple Currencies:** Convert USD to a wide range of currencies.
- **Error Handling:** Gracefully handles errors, such as invalid input or API issues.
