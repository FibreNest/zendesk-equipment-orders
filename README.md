<<<<<<< HEAD
# zendesk-equipment-orders
=======
# Equipment Order App

This is a web-based solution for placing and managing equipment orders, designed to work seamlessly with Zendesk. The app provides a modern, user-friendly interface for both creating new orders and processing cancellations, making equipment management easy for support teams.

## Features
- **Easy Order Placement:** Quickly create new equipment orders with customer details auto-filled from Zendesk tickets.
- **Smart Validation:** Enforces UK phone number format, address confirmation, and item-specific quantity limits for accuracy and compliance.
- **Dynamic Item Handling:** Quantity limits are automatically set based on the selected item type (e.g., routers and pods up to 4, cables and bags up to 1).
- **Modern Notifications:** Clear, accessible notifications for errors and successes, styled for a professional look and feel.
- **Order Cancellation:** Cancel existing orders with confirmation dialogs and instant feedback.
- **Responsive Design:** Works well on various screen sizes within the Zendesk interface.

## Setup
1. Place all files in your Zendesk app assets directory.
2. Ensure your Zendesk instance is configured to allow custom apps.
3. Open a ticket and launch the app from the sidebar to start placing or cancelling orders.

## Usage
- **Placing Orders:**
  - Open a Zendesk ticket and launch the app.
  - Customer information is auto-filled; you can edit the delivery address if needed.
  - Select items and quantities (limits are enforced automatically).
  - Confirm the order and submit. You'll see a success or error notification.
- **Cancelling Orders:**
  - Use the cancel order form to look up and cancel existing orders.
  - Confirmation dialogs and notifications guide you through the process.

## Customization
- All validation and business rules are handled client-side for a smooth user experience.
- The app communicates with backend Logic Apps for order processing, but you can adapt endpoints as needed.
- To adjust item types or quantity limits, simply update the relevant mappings in the code.

---
If you have any questions, feedback, or need help, just reach out to your support team. Happy ordering!
>>>>>>> 4cc97f0 (Initial commit)
