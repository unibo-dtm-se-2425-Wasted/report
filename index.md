---
title: Home
layout: home
has_children: false
nav_order: 1
---

# WASTED

### Authors

- [Sara Marrocolo](mailto:sara.marrocolo@studio.unibo.it)
- [Viola Morgia](mailto:viola.morgia@studio.unibo.it)
- [Vu Ngoc Mai Nguyen](mailto:vungocngocmai.nguyen@studio.unibo.it)
## Abstract

Food waste is one of the most pressing challenges in modern societies. It not only represents a significant economic loss for households and businesses but also has far-reaching environmental and ethical consequences. The project Wasted was conceived as a practical software solution to raise awareness of food waste at the domestic level and to empower users to manage their household inventories more efficiently. The application combines database management, user authentication, data visualization, and external API integration within a streamlined web interface built with Streamlit. Its main objective is to provide an accessible platform that helps individuals monitor food purchases, track expiration dates, and receive suggestions on how to reuse ingredients before they spoil. This extended abstract presents the motivation, design, implementation, and evaluation of the project.

The main goals of the system are to:
* Allow users to register and log in securely.
* Enable them to record food items with details such as purchase date, expiration date, quantity, and cost.
* Provide clear indicators of each item’s status (OK, Expiring Soon, or Expired).
* Estimate the financial loss associated with expired products.
* Offer recipe suggestions for items that are about to expire.

From an implementation perspective, the system is built around a SQLite database with two core tables: one for user credentials and one for food items. Passwords are stored using hashing to ensure basic security. The application’s interface, developed in Streamlit, focuses on usability and clarity: food items are color-coded according to their status, statistical summaries are shown through tables and pie charts, and visual feedback is provided with dialogs and notifications. Moreover, the integration with the Spoonacular API extends functionality by offering recipes based on ingredients close to expiration, turning passive tracking into proactive decision-making.
The correctness and robustness of the project were validated through unit tests covering database operations (insertions, retrievals, authentication) and application logic (status calculation, waste statistics). These tests confirm that the system behaves reliably under typical usage scenarios.
In conclusion, Wasted demonstrates how a lightweight, modular, and user-friendly web application can contribute to reducing food waste at the household level. By combining inventory tracking, cost awareness, and recipe suggestions, it fosters more sustainable consumption habits. Future work could explore push notifications, stronger security mechanisms, and scalability improvements, but even in its current form, Wasted offers a practical and impactful tool for everyday use.