class Product:
    def __init__(self, name, price, quantity):
        self.name = name          # Product name
        self.price = price        # Product price
        self.quantity = quantity  # Available quantity

    def show_info(self):
        print(f"Name: {self.name}, Price: {self.price}, Quantity: {self.quantity}")


class Customer:
    def __init__(self, name, balance):
        self.name = name                # Customer name
        self.balance = balance          # Customer balance
        self.purchases = []             # List of purchases (initially empty)

    def show_info(self):
        print(f"Customer: {self.name}, Balance: {self.balance}, Purchases: {self.purchases}")

    def add_purchase(self, product_name, price):
        if self.balance >= price:
            self.purchases.append(product_name)   # Add product to purchase list
            self.balance -= price                 # Deduct from balance
            print(f"{product_name} purchased ✅")
        else:
            print("Insufficient balance ❌")


class Store:
    def __init__(self):
        self.products = []    # List of products
        self.customers = []   # List of customers

    def add_product(self, product):
        """Add a new product to the store"""
        self.products.append(product)
        print(f"Product {product.name} added ✅")

    def add_customer(self, customer):
        """Register a new customer in the store"""
        self.customers.append(customer)
        print(f"Customer {customer.name} registered ✅")

    def sell_product(self, product_name, customer_name):
        """Sell a product to a customer"""
        # Find the product
        product = next((p for p in self.products if p.name == product_name), None)
        if not product:
            print("❌ Product not found")
            return

        # Find the customer
        customer = next((c for c in self.customers if c.name == customer_name), None)
        if not customer:
            print("❌ Customer not found")
            return

        # Check balance and purchase
        if customer.balance >= product.price:
            customer.add_purchase(product.name, product.price)
            print(f"{product.name} sold to {customer.name} ✅")
        else:
            print("❌ Customer balance insufficient")


# ---------------- Sample Run ----------------
if __name__ == "__main__":
    store = Store()

    # Add products
    p1 = Product("Laptop", 1500, 5)
    p2 = Product("Phone", 800, 10)
    store.add_product(p1)
    store.add_product(p2)

    # Add customers
    c1 = Customer("Alice", 2000)
    c2 = Customer("Bob", 500)
    store.add_customer(c1)
    store.add_customer(c2)

    # Display information
    print("\n📦 Products:")
    for product in store.products:
        product.show_info()

    print("\n🧑 Customers:")
    for customer in store.customers:
        customer.show_info()

    # Sell products
    print("\n💰 Selling:")
    store.sell_product("Laptop", "Alice")  # Successful
    store.sell_product("Phone", "Bob")     # Unsuccessful (insufficient balance)
