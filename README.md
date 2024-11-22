# ☕ Cafe API Flask Application

Welcome to the **Cafe API**! This Flask-based project provides a RESTful API to manage cafe data, including locations, amenities, and prices.

---

## 🌟 Features

- **View Random Cafe**: Get details of a random cafe.
- **View All Cafes**: Retrieve a list of all cafes.
- **Search by Location**: Find cafes in a specific location.
- **Add New Cafe**: Add a new cafe to the database.
- **Update Cafe Price**: Update the coffee price of an existing cafe.
- **Delete Cafe**: Remove a cafe using its unique ID.

---

## 🛠️ Installation

Before running the app, install the required packages.

### On Windows:
```bash
python -m pip install -r requirements.txt
```
### On MacOS:
```bash
pip3 install -r requirements.txt
```
---
## 🚀 How to Run
1. Ensure the database is set up by running the app at least once:
```bash
python app.py
```
2. Access the application at:
http://127.0.0.1:5000
---
## 🔗 API Endpoints
### 1. Home Page
- Route: /
- Description: Renders the homepage.
### 2. Get Random Cafe
- Route: /random
- Method: GET
- Response: Returns a random cafe in JSON format.
### 3. Get All Cafes
- Route: /all
- Method: GET
- Response: Returns a list of all cafes in JSON format.
### 4. Search by Location
- Route: /search?loc=<location>
- Method: GET
- Query Parameter: loc (e.g., "Paris")
- Response: Returns all cafes in the specified location or a 404 error if none found.
### 5. Add a New Cafe
- Route: /add
- Method: POST
- Body Parameters:
  - name, map_url, img_url, loc, sockets, toilet, wifi, calls, seats, coffee_price
- Response: Confirms successful addition.
### 6. Update Cafe Price
- Route: /update-price/<int:cafe_id>?new_price=<price>
- Method: PATCH
- Query Parameter: new_price
- Response: Updates the coffee price of the cafe with the given ID.
### 7. Delete a Cafe
- Route: /report-closed/<int:cafe_id>?api-key=<key>
- Method: DELETE
- Query Parameter: api-key (use TopSecretAPIKey for access)
- Response: Deletes the cafe with the specified ID
---
## 📂 Project Structure
```plaintext
.
├── app.py                 # Main application
├── templates/
│   └── index.html         # Home page template
├── requirements.txt       # Project dependencies
└── cafes.db               # SQLite database
```
---
## 📑 Notes
- Use Postman or any API testing tool for testing POST, PATCH, and DELETE requests.
- Make sure to include the correct API key for deletion requests (TopSecretAPIKey).
---
## 🎨 Sample Usage
Add a Cafe (Postman Example):
1. Set Request Type: POST
2. URL: http://127.0.0.1:5000/add
3. Body (x-www-form-urlencoded):
```plaintext
name=BlueCafe
map_url=http://maps.bluecafe.com
img_url=http://images.bluecafe.com
loc=London
sockets=1
toilet=1
wifi=1
calls=0
seats=20
coffee_price=£3.50
```
Update Price Example:
- Route: /update-price/3?new_price=£4.00
- Method: PATCH
---
## 💻 Technologies Used
- Python
- Flask
- SQLAlchemy
- SQLite
