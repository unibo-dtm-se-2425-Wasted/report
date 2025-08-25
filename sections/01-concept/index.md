---
title: Concept
has_children: false
nav_order: 2
---

# Project concept: "smart fridge and pantry management"

---

### Type of product developed

This project involves the development of a **Web Application with a GUI** (Graphical User Interface). It will be accessible via a web browser on any internet-connected device.

---

### Use cases

The application aims to support users in managing food items at home to reduce waste.

* **Where are the users?** Users are individuals or families who manage their groceries and food supplies within their **homes**.
* **When and how frequently do they interact with the system?** Users will interact with the system **daily or several times a week**. Interaction primarily occurs:
    * When adding new purchases or removing consumed/expired products (after grocery shopping or during meal preparation);
    * When checking expiring food items to plan meals;
    * When asking for recipes inspiration.
* **How do they interact with the system? Which devices are they using?** Interaction happens through a standard web interface. Users will utilize **web browser-enabled devices**, primarily for **tablets or smartphones** for quick checks or while shopping,  but also for **desktops or laptops** for data entry and an overview.
* **Does the system need to store user's data? Which data? Where?** Yes, the system **needs to store user data** that will be stored in a **SQLite database**, managed by the Sreamlit backend logic.
    * **Food items data**: product name, category (e.g., dairy, vegetables, meat), purchase and expiration dates, quantity, unit of measurement and price.
    * **Waste statistics data**: proportion of expired versus consumed products, estimated economic loss due to waste.
    * **User data**: username and password
   

---

### Roles

For the initial development phase, only **one role** is foreseen:

* **Standard Household User:** This role encompasses all food management functionalities (adding, viewing, filtering), receiving in-app alerts, recipe suggestions, and accessing personal waste statistics.
