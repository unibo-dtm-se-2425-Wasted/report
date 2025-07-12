---
title: Concept
has_children: false
nav_order: 2
---

# Project Overview

This project aims to develop a **user-friendly application** designed to help users manage the contents of their fridge or pantry, with the ultimate goal of **reducing food waste at home**.  

The app will allow users to:  
- efficiently keep track of food items,  
- monitor expiration dates, and  
- receive alerts to avoid letting products spoil.  

---

## 📦 Core Functionality

The core functionality of the system includes:  

- **Adding food items** with key information such as:
  - product name
  - category (e.g., dairy, vegetables, meat)
  - purchase and expiration dates
  - quantity and unit of measurement  

- **Dashboard** displaying all stored food, organized and sorted by expiration date.  
  - Products close to expiry will be visually highlighted in red.  
  - Users can filter the list by category, date, or product name for easy browsing.  

- **Notifications and alerts** that warn users of soon-to-expire items.  
  - Alerts can be visual within the app or delivered via email or push notifications.  

- **Recipe suggestion feature** recommending simple dishes using ingredients about to expire, helping users make use of items before they go bad.  

- **Waste statistics module** tracking:
  - proportion of expired vs consumed products
  - estimated economic loss due to waste
  - insights into food usage habits  

---

## 💻 Technical Stack

- **Frontend**: HTML and CSS  
- **Backend**: Flask (Python)  
- **Database**: SQLite  
