# Cafes-RESTful-API-Python

This project is a simple API for managing a database of cafes, built using Flask and SQLAlchemy. The API allows you to perform CRUD operations (Create, Read, Update, Delete) on the cafe data.

## Features

- Retrieve a random cafe from the database
- Get a list of all cafes
- Search for a cafe by location
- Add a new cafe
- Update the coffee price of an existing cafe
- Delete a cafe from the database

## Prerequisites

- Python 3.x
- Flask
- Flask-SQLAlchemy

## Getting Started

### Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/cafe-api.git
   cd cafe-api
2. Create and activate a virtual environment:
  python -m venv venv
  source venv/bin/activate  # On Windows use `venv\Scripts\activate`

3. Install the required packages:
  pip install -r requirements.txt

## Database Setup
1. Initialize the database:
  flask shell
  >>> from your_app import db
  >>> db.create_all()
  >>> exit()

2. (Optional) Populate the database with initial data by adding some records manually or using an external script.

## Running the Application
1. Start the Flask application:
  flask run
2. Open your browser and navigate to http://127.0.0.1:5000/ to see the home page.

## API Endpoints

### Get a Random Cafe
- **Endpoint:** `/random`
- **Method:** `GET`
- **Response:** JSON object containing a random cafe's details.

### Get All Cafes
- **Endpoint:** `/all`
- **Method:** `GET`
- **Response:** JSON array of all cafes.

### Search Cafe by Location
- **Endpoint:** `/search`
- **Method:** `GET`
- **Query Parameter:** `loc` - the location to search for.
- **Response:** JSON object of the cafe at the specified location, or an error message if not found.

### Add a New Cafe
- **Endpoint:** `/add`
- **Method:** `POST`
- **Form Data:**
  - `name`: Name of the cafe
  - `map_url`: URL to the cafe's location on a map
  - `img_url`: URL to an image of the cafe
  - `loc`: Location of the cafe
  - `sockets`: Boolean indicating if the cafe has power sockets
  - `toilet`: Boolean indicating if the cafe has a toilet
  - `wifi`: Boolean indicating if the cafe has Wi-Fi
  - `calls`: Boolean indicating if you can take calls in the cafe
  - `seats`: Number of seats in the cafe
  - `coffee_price`: Price of coffee at the cafe
- **Response:** JSON object indicating success or failure.

### Update Cafe Coffee Price
- **Endpoint:** `/update-price/<int:cafe_id>`
- **Method:** `PATCH`
- **Query Parameter:** `new_price` - the new price of the coffee.
- **Response:** JSON object indicating success or failure.

### Delete a Cafe
- **Endpoint:** `/reported-close/<int:cafe_id>`
- **Method:** `DELETE`
- **Query Parameter:** `api-key` - the API key for authorization.
- **Response:** JSON object indicating success or failure.


