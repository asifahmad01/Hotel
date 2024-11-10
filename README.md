# Node Hotel Management System

The **Hotel Management** application is a hotel management system built with **Node.js** and **Express.js**. It manages hotel staff and menu items, allowing CRUD (Create, Read, Update, Delete) operations for each. This application uses **MongoDB** as the database to store staff (persons) and menu item data.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Endpoints](#endpoints)
  - [Persons](#persons)
  - [Menu Items](#menu-items)
- [Data Models](#data-models)
  - [Person](#person)
  - [Menu Item](#menu-item)
- [Usage](#usage)

## Features

- **Person Management**: Add, update, retrieve, and delete hotel staff information.
- **Menu Management**: Add, update, retrieve, and delete menu items, with filtering by taste.

## Installation

To set up the application, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/node-hotel.git
    ```
2. Navigate to the project directory:
    ```bash
    cd node-hotel
    ```
3. Install dependencies:
    ```bash
    npm install
    ```
4. Set up your MongoDB connection string in `.env` (see `.env.example` for guidance).

5. Start the server:
    ```bash
    npm start
    ```
   By default, the server runs on `http://localhost:3000`.

## Endpoints

### Persons

- **Add a Person**  
  - **Endpoint**: `POST /person`
  - **Description**: Adds a person with details such as name, role, etc.

- **Get All Persons**  
  - **Endpoint**: `GET /person`
  - **Description**: Retrieves a list of all persons in the system.

- **Get Persons by Work Type**  
  - **Endpoint**: `GET /person/:workType`
  - **Description**: Retrieves a list of persons based on their work type (e.g., chef, waiter, manager).

- **Update a Person**  
  - **Endpoint**: `PUT /person/:id`
  - **Description**: Updates the details of a specific person identified by their ID.

- **Delete a Person**  
  - **Endpoint**: `DELETE /person/:id`
  - **Description**: Deletes a person based on their ID.

### Menu Items

- **Add a Menu Item**  
  - **Endpoint**: `POST /menu`
  - **Description**: Adds a menu item with details such as name, price, taste, etc.

- **Get All Menu Items**  
  - **Endpoint**: `GET /menu`
  - **Description**: Retrieves a list of all menu items.

- **Get Menu Items by Taste**  
  - **Endpoint**: `GET /menu/:taste`
  - **Description**: Retrieves menu items based on their taste (e.g., sweet, spicy, sour).

- **Update a Menu Item**  
  - **Endpoint**: `PUT /menu/:id`
  - **Description**: Updates the details of a specific menu item identified by its ID.

- **Delete a Menu Item**  
  - **Endpoint**: `DELETE /menu/:id`
  - **Description**: Deletes a menu item based on its ID.

## Data Models

### Person

The `Person` model represents staff members in the hotel. The following fields are required:

- `name` (String): Person's name
- `age` (Number): Person's age
- `work` (Enum): Role in the hotel (e.g., chef, waiter, manager)
- `mobile` (String): Person's mobile number
- `email` (String): Unique email address
- `address` (String): Person's address
- `salary` (Number): Person's salary

**Example**:
```json
{
  "name": "John Doe",
  "age": 30,
  "work": "waiter",
  "mobile": "123-456-7890",
  "email": "john@example.com",
  "address": "123 Main Street",
  "salary": 30000
}
