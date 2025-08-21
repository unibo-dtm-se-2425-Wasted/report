---
title: Future work
has_children: false
nav_order: 13
---

# Known issues and future work

This section should describe:
- What is missing
- What does not work as it should
- Potential future developments to improve/expand the software

N.B. Be honest, no impact on the final mark.
Although the current version of the Food Waste Manager provides a functional prototype, several areas remain incomplete or require refinement. This section outlines existing limitations and possible future developments.

1.What is Missing?

Notifications & Reminders: At present, expiration alerts only appear in the interface. Proactive notifications (via email, push messages, or SMS) are not yet implemented.

User Authentication: The app only supports a simple username login. Secure authentication with passwords and account management is missing.

Full Item Management: While users can add food items, editing and deleting entries is still limited.

Mobile Optimization: The current design is desktop-focused and not fully responsive for mobile devices.

2.What Does Not Work as Intended?

Date Handling: Invalid or missing expiration dates sometimes generate errors when calculating food status.

Recipe API Integration: The recipe API provides a wide variety of results, but occasionally the images do not match the actual recipe content, which can confuse users.

Recipe Suggestions Reliability: If ingredients are too few or the API limit is reached, results may be incomplete or irrelevant.

3.Potential Future Developments?

3.1. Enhanced Notifications

Push and mobile notifications for items about to expire.

Calendar integration (Google/Outlook).

AI-powered reminders (e.g., “Use tomatoes and cheese today for a pasta dish”).

3.2. Improved User Experience (UX)

Barcode scanning for automatic food entry.

Modern, mobile-first design with dark mode and accessibility features.

Cleaner, verified images for recipes (e.g., using an additional API or internal image curation).

3.3. Data & Insights

Show money and CO₂ savings based on prevented waste.

Personal consumption trends and analytics.

Exportable reports in CSV/Excel.

3.4. Community & Integrations

Integration with Too Good To Go or local donation platforms for surplus food.

A community recipe-sharing feature where users can upload photos and ideas using expiring items.

3.5. Scalability

Migration from SQLite to a cloud-hosted database.

Multi-user support (families, roommates).

IoT integration (smart fridges, kitchen devices).
