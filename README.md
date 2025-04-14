# Orinoco

A Minimum Viable Product (MVP) for an e-commerce website built using an existing API.

## General Architecture

The web application consists of 4 pages:

*   A list view page, showing all available items for sale.
*   A "product" page, dynamically displaying the item selected by the user, allowing them to customize the product and add it to their cart.
*   A "cart" page containing a summary of the products in the cart, the total price, and a form to place an order. The form data must be correct and well-formatted before being sent to the backend (e.g., no text in date fields).
*   An order confirmation page, thanking the user for their order and displaying the total price and the order ID sent by the server.

## Featured Products

Initially, only one category of products will be featured. Choose from the following three options:

*   Handmade teddy bears
*   Vintage cameras
*   Oak furniture

## Data Types

All products have the following attributes:

| Field       | Type     |
| :---------- | :------- |
| `_id`       | ObjectID |
| `name`      | string   |
| `price`     | number   |
| `description`| string   |
| `imageUrl`  | string   |

Each product type includes an array containing strings for customization options:

| Product Type    | Customization Array |
| :-------------- | :------------------ |
| Cameras         | `lenses`            |
| Teddy bears     | `colors`            |
| Oak furniture   | `varnish`           |

## Technologies Used

*   HTML
*   CSS
*   JavaScript (Vanilla)
*   Node.js (for the backend API)

## API Endpoints

The backend provides the following API endpoints:

*   Handmade teddy bears: `http://localhost:3000/api/teddies`
*   Vintage cameras: `http://localhost:3000/api/cameras`
*   Oak furniture: `http://localhost:3000/api/furniture`

### API Parameters

Each API supports 3 endpoints:

| Verb | Endpoint | Expected Request Body | Response                                                                 |
| :--- | :------- | :-------------------- | :----------------------------------------------------------------------- |
| GET  | `/`      | -                     | Returns an array of all items.                                           |
| GET  | `/:_id`  | -                     | Returns the item corresponding to the given `_id`.                       |
| POST | `/order` | JSON object containing `contact` (object) and `products` (array of strings) | Returns the `contact` object, the `products` array, and an `orderId` (string). |

## Data Validation

For the `POST /order` route, the `contact` object sent to the server must contain the fields `firstName`, `lastName`, `address`, `city`, and `email`. The `products` array sent to the backend must be an array of product `_id` strings. The types and presence of these fields must be validated on the front-end before sending the data to the server.

## Installation and Setup

To run this project locally, follow these steps:

**Prerequisites:**

*   Node.js and npm installed on your machine.

**Backend Setup:**

1.  Navigate to the `back-end` directory in your terminal:
    ```sh
    cd back-end
    ```
2.  Install the dependencies (though `package.json` shows dependencies, there's no `npm install` step mentioned, assuming they might be pre-installed or handled differently):
    *Note: If dependencies are needed, run `npm install` here.*
3.  Start the backend server:
    ```sh
    node server.js
    ```
    The server should now be running on `http://localhost:3000`.

**Frontend Setup:**

1.  Open the `index.html` file in your web browser. No additional build steps or servers are required for the frontend as it's built with vanilla HTML, CSS, and JavaScript.

You can now interact with the e-commerce site locally.


