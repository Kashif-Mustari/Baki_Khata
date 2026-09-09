# 📒 Baki Khata — Smart Digital Ledger

**Baki Khata** is a modern, offline-first Android application designed for **small business owners, shopkeepers, and local merchants** to manage customer accounts, credit/debit transactions, receipts, and business records digitally.

Built entirely with **Kotlin** and **Jetpack Compose**, the application provides a clean, secure, and user-friendly experience while keeping business data available offline.

---

## 📱 Overview

Managing customer credit manually in a traditional notebook can be difficult, time-consuming, and prone to errors.

**Baki Khata** transforms the traditional paper-based ledger into a simple digital solution where shopkeepers can:

* Manage customers
* Track credit (Baki) and payments
* View transaction history
* Generate PDF receipts and reports
* Print receipts using Bluetooth thermal printers
* Secure business information with App Lock
* Customize shop and owner information
* Work completely offline

---

## ✨ Key Features

### 📊 Dashboard & Analytics

Get a quick overview of your business transactions from a centralized dashboard.

* Total Credit (Baki)
* Total Payments
* Current Balance
* Transaction overview
* Customer-wise account information

### 👥 Customer Management

Easily create and manage customer profiles.

* Add new customers
* Update customer information
* Delete customers
* View individual customer accounts
* Access complete transaction history

### 💰 Transaction Ledger

Maintain a detailed digital ledger for every customer.

* Record credit transactions
* Record payment transactions
* View transaction history
* Track outstanding balances
* View transaction date and details

### 🖨️ Bluetooth Thermal Printing

Print transaction receipts directly from the application using supported Bluetooth thermal printers.

* Bluetooth printer connection
* Receipt formatting
* Instant transaction printing
* Suitable for small shops and businesses

### 📄 PDF Reports & Invoices

Generate professional PDF documents for transactions and business records.

* Generate transaction receipts
* Generate reports
* Preview PDF documents
* Share generated PDFs
* Save documents locally

### 🔐 App Security

Protect sensitive business information with the built-in App Lock system.

* PIN/Password protection
* Secure application access
* Prevent unauthorized access to business data

### 🏪 Shop & Owner Profile

Customize the application with your business information.

* Shop name
* Owner name
* Address
* Contact information
* Shop logo

Customized information can be displayed on receipts and reports.

### 📶 Offline-First Architecture

The application is designed to work without an internet connection.

All important business data is stored locally using **Room Database**, allowing users to access and manage their records anytime.

### 🎨 Modern UI/UX

Built using Jetpack Compose with a modern and responsive interface.

* Clean user interface
* Material Design
* Dark Mode
* Light Mode
* Responsive layouts
* Smooth navigation
* User-friendly forms

---

# 🛠️ Technology Stack

| Technology             | Purpose                       |
| ---------------------- | ----------------------------- |
| **Kotlin**             | Primary programming language  |
| **Jetpack Compose**    | Modern Android UI toolkit     |
| **MVVM**               | Application architecture      |
| **Room Database**      | Local data persistence        |
| **Coroutines**         | Asynchronous programming      |
| **Flow**               | Reactive data streams         |
| **Navigation Compose** | Screen navigation             |
| **PDFDocument API**    | PDF generation                |
| **EscPosFormatter**    | Thermal receipt formatting    |
| **Bluetooth**          | Thermal printer communication |

---

# 🏗️ Architecture

The application follows the **MVVM (Model–View–ViewModel)** architecture pattern to maintain a clean, scalable, and maintainable codebase.

```text
                ┌──────────────────────┐
                │     Jetpack Compose  │
                │         UI           │
                └──────────┬───────────┘
                           │
                           ▼
                ┌──────────────────────┐
                │      ViewModel       │
                │    Business Logic    │
                └──────────┬───────────┘
                           │
                           ▼
                ┌──────────────────────┐
                │     Repository       │
                │   Data Management    │
                └──────────┬───────────┘
                           │
                           ▼
                ┌──────────────────────┐
                │    Room Database     │
                │    Local Storage     │
                └──────────────────────┘
```

### Architecture Components

**View**

* Jetpack Compose UI
* Displays application state
* Handles user interaction

**ViewModel**

* Manages UI state
* Contains business logic
* Communicates with repositories

**Repository**

* Provides a single data access layer
* Handles database operations
* Connects ViewModels with data sources

**Room Database**

* Stores customer information
* Stores transaction records
* Provides offline data persistence

---

# 🗄️ Database

Baki Khata uses **Room Database** for reliable local data storage.

The database manages information such as:

```text
Customer
 ├── ID
 ├── Name
 ├── Phone
 ├── Address
 └── Created Date

Transaction
 ├── ID
 ├── Customer ID
 ├── Amount
 ├── Transaction Type
 ├── Description
 └── Date & Time

Shop Profile
 ├── Shop Name
 ├── Owner Name
 ├── Address
 ├── Contact
 └── Logo
```

Because the database is stored locally, the application can continue working even without an active internet connection.

---

# 📱 Application Modules

The application is organized into several major modules:

```text
Baki Khata
│
├── Dashboard
│
├── Customers
│   ├── Add Customer
│   ├── Edit Customer
│   └── Customer Details
│
├── Transactions
│   ├── Credit
│   ├── Payment
│   └── Transaction History
│
├── Reports
│   ├── PDF Receipt
│   └── Transaction Report
│
├── Bluetooth Printing
│
├── Shop Profile
│
├── App Lock
│
└── Settings
```

---

# 🔄 Transaction Flow

A typical customer transaction follows this workflow:

```text
Add Customer
      │
      ▼
Open Customer Account
      │
      ▼
Add Transaction
      │
      ├───────────────┐
      ▼               ▼
   Credit           Payment
      │               │
      └───────┬───────┘
              ▼
       Update Balance
              │
              ▼
      Transaction History
              │
              ▼
      Generate Receipt
              │
        ┌─────┴─────┐
        ▼           ▼
       PDF      Bluetooth Print
```

---

# 🔐 Security

Business transaction information can be sensitive. Baki Khata therefore includes an application-level security mechanism.

Users can enable an **App Lock** using a PIN or password to prevent unauthorized access.

> **Note:** The App Lock protects access to the application interface; users should also use Android's device security features such as screen lock.

---

# 🖨️ Bluetooth Printing

Baki Khata supports Bluetooth thermal printing for quick receipt generation.

The general printing process is:

```text
Select Customer
      ↓
Select Transaction
      ↓
Generate Receipt
      ↓
Format Receipt
      ↓
Connect Bluetooth Printer
      ↓
Send Print Data
      ↓
Print Receipt
```

This feature is particularly useful for small retail stores where customers may require a physical transaction receipt.

---

# 📄 PDF Generation

The application can generate transaction-related PDF documents using Android's PDF capabilities.

Users can:

1. Select a customer or transaction.
2. Generate a receipt/report.
3. Preview the document.
4. Save or share the PDF.
5. Print it when required.

---

# 🎨 UI & Design

Baki Khata uses **Jetpack Compose** to provide a modern Android user interface.

### Design Principles

* Simple navigation
* Clear information hierarchy
* Responsive layouts
* Consistent components
* Easy-to-read transaction information
* Dark and Light themes
* Minimal and clean design

---

# 🚀 Getting Started

## Prerequisites

Before running the project, make sure you have:

* **Android Studio** — Koala or newer recommended
* **JDK 17+**
* Android SDK
* Android device or emulator
* Minimum SDK: **API 24 (Android 7.0)**

---

## 📥 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/enamulzishan/Baki_Khata.git
```

### 2. Open the Project

Open the cloned project using **Android Studio**.

### 3. Gradle Sync

Allow Android Studio to download and synchronize all required dependencies.

### 4. Connect a Device

Connect a physical Android device or start an Android Emulator.

### 5. Run the Application

Click **Run ▶** in Android Studio.

---

# 📸 Screenshots

Screenshots will be added soon.

### Dashboard

```text
[ Screenshot Coming Soon ]
```

### Customer Management

```text
[ Screenshot Coming Soon ]
```

### Transaction Details

```text
[ Screenshot Coming Soon ]
```

### PDF Receipt

```text
[ Screenshot Coming Soon ]
```

### App Lock

```text
[ Screenshot Coming Soon ]
```

> Replace the placeholders above with actual application screenshots when available.

---

# 📂 Project Structure

A typical project structure follows this organization:

```text
app/
└── src/
    └── main/
        ├── java/
        │   └── .../
        │       ├── data/
        │       │   ├── database/
        │       │   ├── dao/
        │       │   └── repository/
        │       │
        │       ├── model/
        │       │
        │       ├── ui/
        │       │   ├── screens/
        │       │   ├── components/
        │       │   └── theme/
        │       │
        │       ├── viewmodel/
        │       │
        │       └── navigation/
        │
        └── res/
            ├── drawable/
            ├── mipmap/
            └── values/
```

---

# 🌐 Offline-First Approach

One of the core design principles of Baki Khata is **offline-first functionality**.

Instead of depending on an internet connection for basic operations, the application stores business records locally.

### Benefits

* Works without internet
* Fast data access
* Suitable for areas with poor connectivity
* No server required for basic functionality
* Local transaction storage
* Better availability

---

# 🔮 Future Improvements

The project can be extended with additional features in future versions.

### Planned / Possible Features

* ☁️ Cloud backup and synchronization
* 📱 Multi-device synchronization
* 📊 Advanced business analytics
* 📈 Monthly and yearly reports
* 🔔 Payment reminders
* 📩 SMS/WhatsApp receipt sharing
* 👨‍💼 Multiple user accounts
* 🧾 Advanced invoice customization
* 📤 CSV/Excel data export
* 🔄 Automatic backup and restore
* 🌐 Optional online dashboard

---

# 🤝 Contributing

Contributions are welcome!

If you would like to improve the project:

1. Fork the repository.
2. Create a new feature branch.

```bash
git checkout -b feature/your-feature
```

3. Make your changes.
4. Commit your changes.

```bash
git commit -m "Add new feature"
```

5. Push the branch.

```bash
git push origin feature/your-feature
```

6. Open a Pull Request.

Bug reports, suggestions, feature requests, and improvements are also welcome.

---

# 🐛 Issues & Feature Requests

If you find a bug or have an idea for improving Baki Khata, please create an issue in the repository.

[Open Issues & Feature Requests](https://github.com/enamulzishan/Baki_Khata/issues?utm_source=chatgpt.com)

---

# 📜 License

This project is licensed under the **MIT License**.

See the `LICENSE` file for more information.

---

# 👨‍💻 Author

**Enamul Zishan**

Baki Khata is developed as an Android application project focused on providing a simple and practical digital ledger solution for small businesses.

---

# ⭐ Support the Project

If you find **Baki Khata** useful, consider giving the repository a ⭐ **Star** on GitHub.

Your support helps the project grow and encourages further development.

[Baki Khata on GitHub](https://github.com/enamulzishan/Baki_Khata?utm_source=chatgpt.com)

---

## 📌 Project Summary

**Baki Khata** provides a complete digital solution for managing customer credit and payment records.

> **Manage Customers. Track Transactions. Print Receipts. Stay Organized.**

Built with ❤️ using **Kotlin + Jetpack Compose + Room Database**.
