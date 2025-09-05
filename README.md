# StoreManagementSystem

A simple Python application to **manage products, customers, and sales** in a store.  
The system allows adding products, registering customers, and selling products while checking customer balance.

---

## ✨ Features
- Add products with name, price, and quantity
- Register customers with name and balance
- Display all products and customers
- Sell products to customers with balance check
- Prevent sales if customer has insufficient balance

---

## 🛠 Requirements
- Python 3.x  
> No external libraries are required — only Python standard library.

---

## ▶️ Usage

### 1. Run the program
```bash
python store_management.py

2. Example Output
Product Laptop added ✅
Product Phone added ✅
Customer Alice registered ✅
Customer Bob registered ✅

📦 Products:
Name: Laptop, Price: 1500, Quantity: 5
Name: Phone, Price: 800, Quantity: 10

🧑 Customers:
Customer: Alice, Balance: 2000, Purchases: []
Customer: Bob, Balance: 500, Purchases: []

💰 Selling:
Laptop purchased ✅
Laptop sold to Alice ✅
❌ Customer balance insufficient


📂 Project Structure
.
├── store_management.py  # Main program
└── README.md            # Project documentation
