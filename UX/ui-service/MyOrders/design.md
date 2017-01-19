# My Orders

- My Orders is a primary navigation item
- Administrators
  - View and approve or deny orders for other users
- End Users
  - View status of placed orders

## Admin user

### Review Orders
![Image Title/Mockup Name](img/Order_01.png)
- The Admin User sees all orders that have been placed.

### Approve Order
![Image Title/Mockup Name](img/Order_02.png)
- The Administrator can check and approve the requests in an order.


#### Implementation Details
  - The orders list should use the [List View with simple expansion](https://www.patternfly.org/pattern-library/content-views/list-view/#/api#expanding-rows) pattern
  - Clicking the checkbox on an order should expand the order and select all the requests in the order.
  - The box on an order should be checked if and only if all the requests in the order are checked.

## End user

### View Orders
![Image Title/Mockup Name](img/Order_03.png)
- The End User sees only orders that they have placed
- They can check the status of their currently pending requests and view all past orders and their component requests

### View Requests
![Image Title/Mockup Name](img/Order_04.png)
- Users can cancel orders, or edit and remove component requests

### Edit a request
![Image Title/Mockup Name](img/Order_05.png)
- Clicking the edit button takes the user to a view of the request with editable dialog fields.

## Customer Feedback

### Customer Feedback Received
  - Overview of customer feedback received

### Necessary Customer Feedback
  - Questions to follow up with customers
