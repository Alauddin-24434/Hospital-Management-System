# Hospital-Management-System

### API Endpoints and Data Structures

Auth
1. Register a new user

URL: /auth/register
Method: POST

<pre>
  {
  "username": "user1",
  "email": "user1@example.com",
  "password": "password123",
  "role": "doctor"
}

</pre>
Response:
<pre>
  {
  "message": "User registered successfully",
  "user": {
    "id": "60c72b2f5f1b2c001c8e4af0",
    "username": "user1",
    "email": "user1@example.com",
    "role": "doctor"
  }
}

</pre>

2. Login a user

URL: /auth/login
Method: POST
Request Body:
<pre>
  {
  "email": "user1@example.com",
  "password": "password123"
}

</pre>
Response:
<pre>
  {
  "token": "jwt-token",
  "user": {
    "id": "60c72b2f5f1b2c001c8e4af0",
    "username": "user1",
    "email": "user1@example.com",
    "role": "doctor"
  }
}

</pre>

Users
3. Get user profile
URL: /users/profile
Method: GET
Headers: Authorization: Bearer <token>
Response:
<pre>
  {
  "id": "60c72b2f5f1b2c001c8e4af0",
  "username": "user1",
  "email": "user1@example.com",
  "role": "doctor"
}

</pre>

4. Update user profile

URL: /users/profile
Method: PUT
Headers: Authorization: Bearer <token>
Request Body:
<p>
  <pre>
  {
  "username": "updatedUser1",
  "email": "updatedUser1@example.com"
}

</pre>
</p>
Response:
<pre>
  {
  "message": "Profile updated successfully",
  "user": {
    "id": "60c72b2f5f1b2c001c8e4af0",
    "username": "updatedUser1",
    "email": "updatedUser1@example.com",
    "role": "doctor"
  }
}

</pre>

Patients
5. Create a new patient

URL: /patients
Method: POST
Headers: Authorization: Bearer <token>
Request Body:
<pre>
  {
  "name": "John Doe",
  "age": 30,
  "gender": "male",
  "address": "123 Main St",
  "phone": "1234567890",
  "medicalHistory": "No known allergies."
}

</pre>
Response:
<pre>
  {
  "message": "Patient created successfully",
  "patient": {
    "id": "60c72b2f5f1b2c001c8e4af1",
    "name": "John Doe",
    "age": 30,
    "gender": "male",
    "address": "123 Main St",
    "phone": "1234567890",
    "medicalHistory": "No known allergies."
  }
}

</pre>
6. Get all patients

URL: /patients
Method: GET
Headers: Authorization: Bearer <token>
Response:
<pre>
  [
  {
    "id": "60c72b2f5f1b2c001c8e4af1",
    "name": "John Doe",
    "age": 30,
    "gender": "male",
    "address": "123 Main St",
    "phone": "1234567890",
    "medicalHistory": "No known allergies."
  },
  ...
]

</pre>
7. Get a patient by ID

URL: /patients/:id
Method: GET
Headers: Authorization: Bearer <token>
Response:
<pre>
  {
  "id": "60c72b2f5f1b2c001c8e4af1",
  "name": "John Doe",
  "age": 30,
  "gender": "male",
  "address": "123 Main St",
  "phone": "1234567890",
  "medicalHistory": "No known allergies."
}

</pre>
8. Update a patient by ID

URL: /patients/:id
Method: PUT
Headers: Authorization: Bearer <token>
Request Body:
<pre>
  {
  "name": "John Doe Updated",
  "age": 31,
  "address": "456 Elm St"
}

</pre>
Response:
<pre>
  {
  "message": "Patient updated successfully",
  "patient": {
    "id": "60c72b2f5f1b2c001c8e4af1",
    "name": "John Doe Updated",
    "age": 31,
    "gender": "male",
    "address": "456 Elm St",
    "phone": "1234567890",
    "medicalHistory": "No known allergies."
  }
}

</pre>
9. Delete a patient by ID

URL: /patients/:id
Method: DELETE
Headers: Authorization: Bearer <token>
Response:
<pre>
  {
  "message": "Patient deleted successfully"
}

</pre>

Appointments
10 .Create a new appointment

URL: /appointments
Method: POST
Headers: Authorization: Bearer <token>
Request Body:
<pre>
  {
  "patientId": "60c72b2f5f1b2c001c8e4af1",
  "doctorId": "60c72b2f5f1b2c001c8e4af2",
  "date": "2024-07-01",
  "time": "10:00 AM"
}

</pre>
Response:
<pre>
  {
  "message": "Appointment created successfully",
  "appointment": {
    "id": "60c72b2f5f1b2c001c8e4af3",
    "patientId": "60c72b2f5f1b2c001c8e4af1",
    "doctorId": "60c72b2f5f1b2c001c8e4af2",
    "date": "2024-07-01",
    "time": "10:00 AM",
    "status": "scheduled"
  }
}

</pre>
11. Get all appointments

URL: /appointments
Method: GET
Headers: Authorization: Bearer <token>
Response:
<pre>
  [
  {
    "id": "60c72b2f5f1b2c001c8e4af3",
    "patientId": "60c72b2f5f1b2c001c8e4af1",
    "doctorId": "60c72b2f5f1b2c001c8e4af2",
    "date": "2024-07-01",
    "time": "10:00 AM",
    "status": "scheduled"
  },
  ...
]

</pre>
12. Get an appointment by ID

URL: /appointments/:id
Method: GET
Headers: Authorization: Bearer <token>
Response:
<pre>
  {
  "id": "60c72b2f5f1b2c001c8e4af3",
  "patientId": "60c72b2f5f1b2c001c8e4af1",
  "doctorId": "60c72b2f5f1b2c001c8e4af2",
  "date": "2024-07-01",
  "time": "10:00 AM",
  "status": "scheduled"
}

</pre>
13. Update an appointment by ID

URL: /appointments/:id
Method: PUT
Headers: Authorization: Bearer <token>
Request Body:
<pre>
  {
  "status": "completed"
}

</pre>
Response:
<pre>
  {
  "message": "Appointment updated successfully",
  "appointment": {
    "id": "60c72b2f5f1b2c001c8e4af3",
    "patientId": "60c72b2f5f1b2c001c8e4af1",
    "doctorId": "60c72b2f5f1b2c001c8e4af2",
    "date": "2024-07-01",
    "time": "10:00 AM",
    "status": "completed"
  }
}

</pre>
14. Delete an appointment by ID

URL: /appointments/:id
Method: DELETE
Headers: Authorization: Bearer <token>
Response:
<pre>
  {
  "message": "Appointment deleted successfully"
}

</pre>

Billing
15. Create a new billing record

URL: /billings
Method: POST
Headers: Authorization: Bearer <token>
Request Body:
<pre>
  {
  "patientId": "60c72b2f5f1b2c001c8e4af1",
  "appointmentId": "60c72b2f5f1b2c001c8e4af3",
  "amount": 200,
  "date": "2024-07-01"
}

</pre>
Response:
<pre>
  {
  "message": "Billing record created successfully",
  "billing": {
    "id": "60c72b2f5f1b2c001c8e4af4",
    "patientId": "60c72b2f5f1b2c001c8e4af1",
    "appointmentId": "60c72b2f5f1b2c001c8e4af3",
    "amount": 200,
    "date": "2024-07-01",
    "status": "pending"
  }
}

</pre>

16. Get all billing records

URL: /billings
Method: GET
Headers: Authorization: Bearer <token>
Response:
<pre>
  [
  {
    "id": "60c72b2f5f1b2c001c8e4af4",
    "patientId": "60c72b2f5f1b2c001c8e4af1",
    "appointmentId": "60c72b2f5f1b2c001c8e4af3",
    "amount": 200,
    "date": "2024-07-01",
    "status": "pending"
  },
  ...
]

</pre>
17. Get a billing record by ID

URL: /billings/:id
Method: GET
Headers: Authorization: Bearer <token>
Response:
<pre>
  {
  "id": "60c72b2f5f1b2c001c8e4af4",
  "patientId": "60c72b2f5f1b2c001c8e4af1",
  "appointmentId": "60c72b2f5f1b2c001c8e4af3",
  "amount": 200,
  "date": "2024-07-01",
  "status": "pending"
}

</pre>
18. Update a billing record by ID

URL: /billings/:id
Method: PUT
Headers: Authorization: Bearer <token>
Request Body:
<pre>
  {
  "status": "paid"
}

</pre>
Response:
<pre>
  {
  "message": "Billing record updated successfully",
  "billing": {
    "id": "60c72b2f5f1b2c001c8e4af4",
    "patientId": "60c72b2f5f1b2c001c8e4af1",
    "appointmentId": "60c72b2f5f1b2c001c8e4af3",
    "amount": 200,
    "date": "2024-07-01",
    "status": "paid"
  }
}

</pre>
19. Delete a billing record by ID

URL: /billings/:id
Method: DELETE
Headers: Authorization: Bearer <token>
Response:
<pre>
  {
  "message": "Billing record deleted successfully"
}

</pre>
