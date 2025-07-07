# Equipment Ordering app App

This is a comprehensive Zendesk app for placing and managing equipment orders, designed to work seamlessly within the Zendesk support interface. The app provides a modern, user-friendly experience for both creating new orders and processing cancellations, making equipment management efficient for support teams.

## Features

### New Order Form
- **Smart Customer Info Auto-fill:** Customer information is automatically populated from Zendesk ticket data and initially displayed as read-only
- **Editable Delivery Address:** Click "Change Delivery Address" to modify delivery details when needed
- **Dynamic Item Management:** Add multiple items with automatic quantity validation
- **Item-Specific Quantity Limits:**
  - DNS, Router Upgrade, Pod Order, Wi-Fi Guarantee Order, Existing Customer Wi-Fi Guarantee Order: Maximum 4 items
  - Returns Bag, Ethernet Cable, Power Cable: Maximum 1 item
- **UK Phone Number Validation:** Enforces strict UK format (11 digits, starts with 0, no spaces)
- **Existing Order Detection:** Automatically checks for existing orders by ticket ID and provides appropriate warnings
- **Auto-Generated Order IDs:** Creates unique order IDs in format `FN-{ticketID}-{YYMMDDHHmm}`
- **Expected Delivery Date:** Automatically calculated and displayed for customer reference

### Cancel Order Form
- **Ticket-Based Search:** Search for orders using Zendesk ticket ID
- **Detailed Order Display:** Shows comprehensive order information including item names, part numbers, status, delivery details, and quantities
- **Smart Processing:** Grey overlay during processing with appropriate error handling
- **Modal Management:** Intelligent modal closing based on error types

### General Features
- **Modern UI/UX:** Clean, professional interface with accessible color schemes
- **Smart Notifications:** 
  - Success notifications: Light green background with dark green text
  - Error notifications: Light red background with dark red text
  - Dismissible notifications with clear action buttons
- **Responsive Design:** Optimized for various screen sizes within Zendesk
- **Ticket Status Awareness:** Automatically disables order functions for closed/solved tickets
- **Backend Integration:** Communicates with Logic Apps using operation_type parameters:
  - `newOrder` for order submissions
  - `queryOrder` for order lookups
  - `cancelOrder` for order cancellations

## Supported Equipment Types

The app supports the following equipment categories with their respective part numbers and delivery methods:

- **DNS** (B2C1) - DHL delivery
- **Router Upgrade** (B2C2) - DHL delivery  
- **Pod Order** (B2C3) - DHL delivery
- **Wi-Fi Guarantee Order** (B2C4) - DHL delivery
- **Existing Customer Wi-Fi Guarantee Order** (B2C5) - DHL delivery
- **Returns Bag** (FNESTRTNBAG1) - RM2MAIL delivery
- **Ethernet Cable** (L67-8010) - RMT48 delivery
- **Power Cable** (17600093F1) - RMT48 delivery

## Setup

1. **Installation:**
   - Place all files in your Zendesk app assets directory
   - Ensure your Zendesk instance is configured to allow custom apps
   - The app will appear in the ticket sidebar

2. **Configuration:**
   - Update the Logic Apps endpoint URL in both forms to match your backend
   - Customize item types, part numbers, and delivery methods as needed
   - Adjust quantity limits by modifying the `itemMaxQuantities` object

## Usage

### Placing New Orders
1. Open a Zendesk ticket and locate the Equipment Order app in the sidebar
2. Click "New Order" to launch the order form
3. Customer information is auto-filled; click "Change Delivery Address" if modifications are needed
4. Add items by selecting from the dropdown and entering quantities (limits are enforced automatically)
5. Verify the UK phone number format (11 digits, starts with 0)
6. Review the expected delivery date and order details
7. Click "Confirm Order" to submit

### Cancelling Orders
1. Click "Cancel Order" in the sidebar
2. Enter the Zendesk ticket ID to search for existing orders
3. Review the detailed order information displayed
4. Click "Cancel Order" to process the cancellation
5. Confirm the action when prompted

## Technical Details

### Order ID Generation
Orders are automatically assigned unique IDs in the format: `FN-{ticketID}-{YYMMDDHHmm}`

### Validation Rules
- **Phone Numbers:** Must be exactly 11 digits, start with 0, contain no spaces
- **Quantities:** Enforced per item type (1 or 4 maximum)
- **Required Fields:** All customer and delivery information must be complete
- **Existing Orders:** System checks for duplicate orders and provides appropriate guidance

### API Integration
The app communicates with backend Logic Apps using JSON payloads with operation_type parameters to distinguish between different operations.

## Customization

### Modifying Item Types
Update the item mappings in the JavaScript code:
- `itemToCategoryMap`: Maps items to business categories
- `itemToPartNumberMap`: Maps items to part numbers
- `itemToDeliveryMethodMap`: Maps items to delivery methods
- `itemMaxQuantities`: Sets quantity limits per item

### Styling
The app uses modern CSS with:
- Consistent color scheme (blue primary, red for actions, green for success)
- Responsive design principles
- Accessible contrast ratios
- Professional typography using Inter font family

### Error Handling
- Comprehensive validation with user-friendly error messages
- Graceful handling of API failures
- Smart modal management based on error types

## Support

For technical support, questions, or feature requests, please contact your development team or refer to the Zendesk developer documentation for app customization guidance.

---

*This app is designed to streamline equipment order management within Zendesk, providing a seamless experience for support teams while maintaining data integrity and compliance with business rules.*
