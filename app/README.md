# CHM Lae Shop – Online Shopping Mobile Application

**IS223 Object Oriented Programming – Major Project**
Bachelor of Business in Information Technology, School of Business Studies, PNG University of Technology (2026)

**Group members:** _[Name – HEMBESAUSE Brendon ID - 25530218]_, _[Name – DAVID Danda ID - 25530352]_, _[Name – MARTIN Anthon ID - 25530225]_, [BENBARA Moira]_

---

## Project description

CHM Lae Shop is an Android prototype of an online shopping app for the **CHM store at Top Town, Lae (Morobe Province)**. Customers can browse CHM products by category, search, view product details, add products to a shopping cart, see subtotals and the total in Kina, enter their details and complete a **simulated** checkout that produces an order confirmation.

The app uses CHM's brand colours (blue and white). Product names, prices and images come from CHM promotional material.

> **Prototype notice:** This is an academic prototype. It does **not** process real payments, does not collect card or bank details, and is not an official CHM application.

## Objectives

1. Analyse the requirements of an online shopping app for a real Lae business (CHM).
2. Apply Java OOP: classes, objects, constructors, methods, encapsulation, inheritance, method overriding, polymorphism and ArrayList.
3. Build an Android interface with XML layouts and connect it to Java logic using event handling.
4. Implement a working shopping cart with subtotal and total calculation.
5. Test the application and document the results.

## Development tools

| Tool | Purpose |
|---|---|
| Android Studio | Development environment |
| Java | Programming language |
| Android SDK (min API 24) | Android libraries |
| XML | User interface layouts |
| Android Emulator / phone | Testing |
| JUnit 4 | Unit testing of the Java classes |
| Git / GitHub | Version control |

## Main features

- Splash screen, home screen with store image, welcome message and navigation buttons
- 5 product categories: Mobile Phones, Computers & Laptops, Smartwatches, Music & Instruments, Home Appliances
- 20 products with real CHM images, names and Kina prices
- Live product search (by name or brand)
- Product details with specifications and quantity selector
- Shopping cart: quantity +/−, remove item, clear cart, subtotals, total, item badge in the header
- Checkout with input validation (name, PNG phone number, delivery location) and confirmation dialog
- Order confirmation with order number, date and summary
- Clear prototype labels on checkout and confirmation screens

## Screens (8)

| # | Screen | Java class | Layout |
|---|---|---|---|
| 1 | Splash | `SplashActivity` | `activity_splash.xml` |
| 2 | Home | `MainActivity` | `activity_main.xml` |
| 3 | Categories | `CategoriesActivity` | `activity_categories.xml` |
| 4 | Product List | `ProductListActivity` | `activity_product_list.xml` |
| 5 | Product Details | `ProductDetailsActivity` | `activity_product_details.xml` |
| 6 | Shopping Cart | `CartActivity` | `activity_cart.xml` |
| 7 | Checkout | `CheckoutActivity` | `activity_checkout.xml` |
| 8 | Order Confirmation | `OrderConfirmationActivity` | `activity_order_confirmation.xml` |

## OOP concepts demonstrated

| Concept | Where to find it |
|---|---|
| **Classes** | `model/` – `Product`, `Smartphone`, `Computer`, `Smartwatch`, `MusicalInstrument`, `HomeAppliance`, `Cart`, `CartItem`, `Customer`, `Order`, `Category` |
| **Objects** | `ProductCatalog.loadProducts()` creates 20 product objects; `new Customer(...)` and `cart.checkout(...)` in `CheckoutActivity` |
| **Constructors** | `Product(int, String, String, double, int, String)` and overloaded `Product(String, double)`; child constructors call `super(...)` |
| **Methods** | `addProduct()`, `removeProduct()`, `calculateTotal()`, `displayProduct()`, `checkout()`, `generateOrderSummary()` |
| **Encapsulation** | All fields are `private`; `setPrice()` rejects negative prices; `Cart.getItems()` returns a read-only list |
| **Inheritance** | 5 child classes `extend Product`; on the Android side every screen `extends BaseActivity` |
| **Method overriding** | Each child overrides `getCategory()`, `getSpecifications()` and `displayProduct()` (`@Override`) |
| **Polymorphism** | `ArrayList<Product>` holds all child types; `ProductCatalog.getProductsByCategory()`, `ProductAdapter` and `MainActivity.logPolymorphismDemo()` call overridden methods through `Product` references |
| **Method overloading** | `Cart.addProduct(Product)` and `Cart.addProduct(Product, int)` |
| **ArrayList** | `Cart.items`, `Order.items`, `ProductCatalog.products` |
| **Interfaces / event handling** | `OnClickListener` lambdas, `TextWatcher` for search, adapter callback interfaces |

## Project structure

```
CHM-Lae-Shopping-App/
├── app/src/main/
│   ├── AndroidManifest.xml
│   ├── java/com/chm/laeshop/
│   │   ├── model/        Product + 5 child classes, Cart, CartItem, Customer, Order, Category
│   │   ├── data/         ProductCatalog (product data), ShopSession (shared cart)
│   │   ├── adapters/     CategoryAdapter, ProductAdapter, CartAdapter
│   │   └── activities/   BaseActivity + 8 screens
│   └── res/              layouts, drawables (product images), colours, strings, themes
├── app/src/test/java/com/chm/laeshop/
│   ├── CartUnitTest.java   13 JUnit tests
│   └── OopConsoleDemo.java plain-Java OOP demonstration (Phase 4)
├── documentation/        setup guide, testing report, code guide, UML diagrams
├── screenshots/
└── README.md
```

## Installation

1. Unzip the project and open the `CHMLaeShop` folder in Android Studio (**File → Open**).
2. Click **Trust Project** and wait for Gradle sync (internet needed the first time).
3. Select a phone or emulator and press **Run ▶**.
4. APK: **Build → Build App Bundle(s) / APK(s) → Build APK(s)** → `app/build/outputs/apk/debug/app-debug.apk`.

## Screenshots

See the `screenshots/` folder.

## Acknowledgements

- Product images and prices: CHM promotional material (used for academic purposes only).
- Icons: Google Material Icons (Apache License 2.0).
- Development assisted by Claude (Anthropic) AI; all code was reviewed, tested and is explained by the group members.
