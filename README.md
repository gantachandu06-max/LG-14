# TeaTime Vending API

## Project Description

TeaTime Vending is a backend application developed using Node.js, Express.js and SQLite. It manages vending machines, operators and their assignments.

The application provides REST API endpoints to perform CRUD operations on machines, retrieve operator information, view machine assignments, search machines by product and maintain an audit trail of machine activities.

## Live API

**Render Deployment:** https://lg-14-teatime-vending.onrender.com

**GitHub Repository:** https://github.com/gantachandu06-max/LG-14

## Technologies Used

- Node.js
- Express.js
- SQLite3
- JavaScript
- VS Code
- REST Client Extension

## Project Structure

```text
LG-14-TeaTime-Vending/
│
├── controllers/
│
├── database/
│   ├── db.js
│   └── teatime.db
│
├── routes/
│   ├── assignmentRoutes.js
│   ├── auditRoutes.js
│   ├── machineRoutes.js
│   └── operatorRoutes.js
│
├── screenshots/
│   ├── postman_add_machine.png
│   ├── postman_get_all_machines.png
│   ├── postman_get_machine_by_id.png
│   ├── postman_search_machines_by_product.png
│   └── postman_update_machine.png
│
├── .gitignore
├── package.json
├── package-lock.json
├── README.md
├── server.js
└── teatime-requests.http
```

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/gantachandu06-max/LG-14.git
```

### 2. Navigate to the Project Folder

```bash
cd LG-14
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Start the Server

```bash
npm start
```

The server runs on port 3000 by default.

**Expected Output:**

```text
TeaTime Vending API running on port 3000
Connected to TeaTime database!
```

## API Endpoints

### Machines

| Method | Endpoint | Description |
|---|---|---|
| GET | `/machines` | Retrieve all machines |
| GET | `/machines/:id` | Retrieve a machine by ID |
| POST | `/machines` | Add a new machine |
| PUT | `/machines/:id` | Update machine details |
| DELETE | `/machines/:id` | Delete a machine |
| GET | `/machines?product=Tea` | Search machines by product |

### Operators

| Method | Endpoint | Description |
|---|---|---|
| GET | `/operators` | Retrieve all operators |
| GET | `/operators/:id` | Retrieve an operator by ID |

### Assignments

| Method | Endpoint | Description |
|---|---|---|
| GET | `/assignments` | Retrieve assignments with operator and machine names |

### Audit Trail

| Method | Endpoint | Description |
|---|---|---|
| GET | `/audit` | Retrieve the latest 10 audit records |

## Database

The application uses SQLite3 to store and manage data.

The database contains three main tables:

1. **Operators** – Stores operator details.
2. **Machines** – Stores vending machine details.
3. **Assignments** – Stores the relationships between operators and machines.

An additional audit table records machine activities.

## Validation and Error Handling

The application includes validation for machine creation and updates.

- Machine name and product are required.
- Invalid requests return HTTP 400.
- Records that do not exist return HTTP 404.
- Successful requests return appropriate HTTP status codes.

## Audit Trail

The application maintains an audit trail for machine operations.

The following activities are recorded:

- ADD – When a new machine is created.
- UPDATE – When machine details are modified.
- DELETE – When a machine is deleted.

Each audit record stores the action, machine ID and timestamp.

The `/audit` endpoint displays the latest 10 records in descending order.

## API Testing

The Postman requests are organized in the `TeaTime-Vending.postman_collection.json` file.

The requests cover:

1. Get All Machines
2. Get Machine By ID
3. Add Machine
4. Update Machine
5. Delete Machine
6. Search Machines By Product
7. Get All Operators
8. Get Operator By ID
9. Get Assignments With Names
10. Get Latest Audit Records

## Screenshots

Screenshots of the API testing results are stored in the `screenshots/` folder.

### Postman — Localhost Results

#### Get All Machines

![Postman: Get All Machines](screenshots/postman_get_all_machines.png)

#### Get Machine By ID

![Postman: Get Machine By ID](screenshots/postman_get_machine_by_id.png)

#### Search Machines By Product

![Postman: Search Machines By Product](screenshots/postman_search_machines_by_product.png)

#### Add Machine

![Postman: Add Machine](screenshots/postman_add_machine.png)

#### Update Machine

![Postman: Update Machine](screenshots/postman_update_machine.png)

### Additional Postman Screenshots

These captures show the requests and responses shared by Vinay. Error responses are labeled as captured; they are included as testing evidence, not successful CRUD results.

#### Get All Machines

![Vinay Postman: Get All Machines](screenshots/vinay_postman_get_all_machines.png)

#### Get Machine By ID

![Vinay Postman: Get Machine By ID](screenshots/vinay_postman_get_machine_by_id.png)

#### Add Machine Request

![Vinay Postman: Add Machine request response](screenshots/vinay_postman_add_machine_validation.png)

#### Update Machine Request

![Vinay Postman: Update Machine request response](screenshots/vinay_postman_update_machine_validation.png)

#### Delete Machine Request

![Vinay Postman: Delete Machine request response](screenshots/vinay_postman_delete_machine_constraint.png)

#### Search Machines By Product

![Vinay Postman: Search Machines By Product](screenshots/vinay_postman_search_machines_by_product.png)

### Madhukar's Postman Screenshots

#### Machine Requests

![Madhukar Postman: Get All Machines](screenshots/postman-get-all-machines.png)

![Madhukar Postman: Get Machine By ID](screenshots/postman-get-machine-by-id.png)

![Madhukar Postman: Search Machines By Product](screenshots/postman-search-machines-by-product.png)

![Madhukar Postman: Add Machine error response](screenshots/postman-add-machine-error.png)

![Madhukar Postman: Invalid machine route response](screenshots/postman-invalid-machine-route.png)

#### Operator Requests

![Madhukar Postman: Get All Operators](screenshots/postman-get-all-operators.png)

![Madhukar Postman: Get Operator By ID](screenshots/postman-get-operator-by-id.png)

![Additional capture: Get All Operators](screenshots/get_all_operators.png)

![Additional capture: Get Operator By ID](screenshots/get_operator_by_id.png)

#### Assignments

![Madhukar Postman: Get Assignments](screenshots/postman-get-assignments.png)

![Madhukar Postman: Additional Assignments capture](screenshots/postman-assignments-additional-capture.png)

![Additional capture: Get Assignments](screenshots/get_assignments.png)

#### Audit Records

![Madhukar Postman: Get Latest Audit Records](screenshots/postman-get-audit-records.png)

![Additional capture: Latest Audit Records](screenshots/latest_audit_records.png)

### Hasya's Postman Screenshots

#### Machine Requests

![Hasya Postman: Get All Machines](screenshots/hasya_postman_get_all_machines.png)

![Hasya Postman: Get Machine By ID](screenshots/hasya_postman_get_machine_by_id.png)

![Hasya Postman: Search Machines By Product](screenshots/hasya_postman_search_machines_by_product.png)

![Hasya Postman: Add Machine](screenshots/hasya_postman_add_machine.png)

![Hasya Postman: Update Machine](screenshots/hasya_postman_update_machine.png)

![Hasya Postman: Delete Machine](screenshots/hasya_postman_delete_machine.png)

#### Operator and Assignment Requests

![Hasya Postman: Get All Operators](screenshots/hasya_postman_get_all_operators.png)

![Hasya Postman: Get Assignments](screenshots/hasya_postman_get_assignments.png)

## Expected HTTP Status Codes

| Status Code | Description |
|---|---|
| 200 | Request successful |
| 201 | Resource created successfully |
| 400 | Invalid request or missing required fields |
| 404 | Requested resource not found |
| 500 | Internal server error |

## Team Members

**Group 14 – TeaTime Vending**

- B. Hasya
- G. Chandu
- K. Vinay Vardhan
- K. Susvitha
- K. Madhukar

## Conclusion

The TeaTime Vending API demonstrates the implementation of REST API operations using Node.js, Express.js and SQLite. It supports machine management, operator retrieval, assignments, product-based searching, input validation and audit logging.