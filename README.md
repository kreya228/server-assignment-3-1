# server-assignment-3-1

Assignment 3 – State Statistics Management API
📌 Objective

Build a complete REST API using Express.js that manages statistical data of Indian states using an in-memory JSON array.

This API allows you to:

View state statistics

Add new states

Replace state data (PUT)

Partially update state data (PATCH)

Delete state records

⚡ No database is used
⚡ No authentication
⚡ No external validation libraries
⚡ All operations modify in-memory array dynamically

🧾 State Data Structure

Each state follows this structure:

{
  "id": 1,
  "name": "Gujarat",
  "population": 63872399,
  "literacyRate": 78.03,
  "annualBudget": 243965,
  "gdp": 21000000
}
Field Meaning

id → Unique identifier (number)

name → State name (string)

population → Total population (number)

literacyRate → Literacy percentage (number)

annualBudget → Annual state budget in crores (number)

gdp → State GDP in crores (number)

📦 Sample Data

API is initialized with 28 Indian states stored in an in-memory array.

Example:

const states = [
  { id: 1, name: "Andhra Pradesh", population: 49386799, literacyRate: 67.02, annualBudget: 279279, gdp: 14000000 },
  { id: 2, name: "Arunachal Pradesh", population: 1383727, literacyRate: 65.38, annualBudget: 28000, gdp: 300000 },
  { id: 3, name: "Assam", population: 31205576, literacyRate: 72.19, annualBudget: 122000, gdp: 4500000 }
  ...
];
🚀 Technologies Used

Node.js

Express.js

CORS Middleware

In-Memory JSON Array

▶️ How to Run Locally

1️⃣ Clone Repository

git clone <your-github-link>

2️⃣ Go to project folder

cd assignment3

3️⃣ Install dependencies

npm install

4️⃣ Run server

node server.js

Server runs on:

http://localhost:5000
📚 API Routes
🟢 GET Routes
1️⃣ GET /states

Return complete list of states
Status: 200

2️⃣ GET /states/:id

Return state by ID

Example:

GET /states/3

Status: 200 or 404

If not found:

{
  "message": "State not found"
}
3️⃣ GET /states/highest-gdp

Return state with highest GDP
Status: 200

🟡 POST Route
4️⃣ POST /states

Add new state

Example Body:

{
  "name": "New State",
  "population": 5000000,
  "literacyRate": 75.5,
  "annualBudget": 150000,
  "gdp": 9000000
}

Status: 201 Created

🔵 PUT Routes
5️⃣ PUT /states/:id

Replace entire state (except id)
Status: 200 or 404

6️⃣ PUT /states/:id/budget

Update annualBudget only

Body:

{
  "annualBudget": 260000
}

Status: 200

7️⃣ PUT /states/:id/population

Update population only

Status: 200

🟣 PATCH Routes
8️⃣ PATCH /states/:id/literacy

Update literacyRate only
Status: 200

9️⃣ PATCH /states/:id/gdp

Update gdp only
Status: 200

🔟 PATCH /states/:id

Partially update any provided fields

Example:

{
  "annualBudget": 280000
}

Only provided fields will be updated.
Status: 200

🔴 DELETE Routes
1️⃣1️⃣ DELETE /states/:id

Delete state by ID
Status: 204 or 404

1️⃣2️⃣ DELETE /states/name/:stateName

Delete state by name (case-insensitive)
Status: 204 or 404

1️⃣3️⃣ DELETE /states/low-literacy/:percentage

Delete all states where literacyRate < given value

Example:

DELETE /states/low-literacy/70

Response:

{
  "deletedCount": 2
}

Status: 200

📊 Status Codes Used

200 → Success

201 → Created

204 → No Content (Deleted)

404 → Not Found

🧪 Testing

Use Postman to test all 13 routes.

📤 Submission Links
🔗 GitHub Repository:
https://github.com/kreya228/server-assignment-3-1.git

🔗 Postman Documentation:
https://documenter.getpostman.com/view/50839275/2sBXcHiyj6

🔗 Render Deployment:
https://server-assignment-3-1.onrender.com

👩‍💻 Author
Kreya Panchal
