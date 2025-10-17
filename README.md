# ✈️ Flight Club

A Python-based **Flight Price Tracker** that helps users find the cheapest flight deals and automatically notifies them when flight prices drop below their target price.

Developed with ❤️ by **Param Sangani**

---

## 🧭 Overview

The **Flight Club** project automates flight price tracking and alerts users via **SMS** and **Email** when flight prices fall below a predefined threshold.  
It integrates with **Google Sheets**, **Tequila Kiwi API** (for flight search), and **Twilio / SMTP** (for notifications).

---

## 🚀 Features

- ✈️ **Searches direct and indirect flights** using the Kiwi Tequila API  
- 🗓️ **Looks for deals within a 6-month window**  
- 🧮 **Automatically updates missing IATA airport codes** in Google Sheets  
- 📉 **Finds the cheapest available flight** for each destination  
- 📧 **Sends email and SMS alerts** for low-price flights  
- 🧠 **Stores destination and user data** via Google Sheets integration  

---

## 🧩 Project Structure

flight-club/
├── main.py # Main script to run the flight search and alerts
├── data_manager.py # Handles Google Sheet read/write operations
├── flight_search.py # Handles communication with the flight API
├── flight_data.py # Finds the cheapest flight among available options
├── notification_manager.py # Sends email and SMS alerts
├── requirements.txt # Required dependencies
└── README.md # You are here!

---

## ⚙️ How It Works

1. **Load Data**  
   - The script fetches destination data from a Google Sheet via the DataManager.  
   - Missing IATA codes are automatically retrieved and updated in the sheet.

2. **Search Flights**  
   - The system searches for flights from your origin (default: `LON`) to all destinations for the next 6 months.  
   - If no direct flights are available, it looks for indirect (stopover) flights.

3. **Find Cheapest Option**  
   - From the list of available flights, it identifies the cheapest one.

4. **Send Alerts**  
   - If a flight is cheaper than the target price in your sheet, the app sends:
     - 📱 **SMS** via Twilio  
     - 📧 **Email** to all registered users

---

## 🧠 Requirements

You’ll need:

- Python 3.9+
- A Google Sheet with destination and user data
- Tequila Kiwi API key
- Twilio account (for SMS)
- An SMTP-enabled email account (for sending notifications)

---

## 🧰 Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/flight-club.git
   cd flight-club
2. **Set up environment variables
SHEETY_ENDPOINT=your_google_sheet_endpoint
TEQUILA_API_KEY=your_tequila_api_key
TWILIO_SID=your_twilio_sid
TWILIO_AUTH_TOKEN=your_twilio_auth_token
TWILIO_PHONE_NUMBER=your_twilio_phone_number
EMAIL_USER=your_email@example.com
EMAIL_PASS=your_email_password

## Example Output
Getting direct flights for Paris...
Paris: £35
Check your email. Lower price flight found to Paris!

## 👨‍💻 Author
Param Sangani
🚀 Passionate about automation, data, and clean code.

📫 Reach me at: param16032006@gmail.com
