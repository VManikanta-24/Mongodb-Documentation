## 📘 `List of APIS`



### Base Url Endpoint


**URL:**  

```
https://www.bluebex.xyz

```


### 1. ✅ Register User

**URL:** 
```
https://www.bluebex.xyz/api/users/register
```

**Method:** `POST`

**Description:** Registers a new user using phone number and name.

#### 🔸 Request Body:

```json
{
    "phoneNumber": "9108105199",
    "name": "Balaji S",
    "companyName":"Bluebex private Limited"
}
```

#### 🔸 Response:

```json
{
    "message": "OTP sent successfully for registration",
    "phoneNumber": "9108105199",
    "status": "success",
    "details": "943342c8b66e6ee9-BOM"
}
```

---

### 2. 🔐 Verify OTP

**URL:** `https://www.bluebex.xyz/api/otp/verify`

**Method:** `POST`

**Description:** Verifies the OTP sent to the user and completes registration.

***Use this endpoint to verify the OTP sent during registration. The mode should be "register" to confirm the user is registering, not logging in.***


#### 🔸 Request Body:

```json
{
    "phoneNumber": "9108105199",
    "otp": "40891",
    "mode": "register"
}
```

#### 🔸 Response:

```json
{
    "message": "Admin registered successfully",
    "name": "Balaji S",
    "phoneNumber": "9108105199",
    "companyName": "Bluebex private Limited"
}

```
> 🔍 *Note:*  
> - The mode value determines the context of the OTP verification:  
> - "register": Registers a new user upon successful OTP verification.  
> - "login": Logs in an existing user after OTP verification.

---
### 3. 📩 Login User (Send OTP)


***Method: POST***
```
https://www.bluebex.xyz/api/users/login
```

This endpoint sends an OTP to an existing user’s phone number to start the login process.

***Request Body:***

```json

{
    "phoneNumber":"9108105199"
}

```
***Response:***

```json
{
    "message": "OTP sent successfully for login",
    "phoneNumber": "9108105199",
    "name": "Balaji S",
    "status": "success",
    "details": "943349c267b63a2c-BOM"
} 

```

*Status:* 200 OK

---

### 4. 🔑 Verify OTP (Login)

***Method: POST***

``` bash
https://www.bluebex.xyz/api/otp/verify
```
After receiving the OTP via the login endpoint, verify it here. The mode must be "login" to trigger the login flow and return a JWT token.

***Request Body:***
```json
{
    "phoneNumber": "9108105199",
    "otp": "82446",
    "mode": "login"
}

```

***Response:***
```
{
    "message": "Login successful",
    "user": {
        "_id": "682da64777ee6298f3f03b80",
        "phoneNumber": "9108105199",
        "name": "Balaji S",
        "isVerified": true,
        "companyName": "Bluebex private Limited",
        "firebaseToken": "",
        "appVersion": "",
        "role": "admin",
        "createdAt": "2025-05-21T10:09:11.897Z",
        "updatedAt": "2025-05-21T10:12:30.576Z",
        "__v": 0
    },
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY4MmRhNjQ3NzdlZTYyOThmM2YwM2I4MCIsInJvbGUiOiJhZG1pbiIsImlhdCI6MTc0NzgyMjM1MCwiZXhwIjoxNzc5Mzc5OTUwfQ.yOUhJYLF8d_xHUBzBlgSXZ4QimcbgJwpvWrTSUCS2jc"
}

```
*Status:* 200 OK

> 🔐 *JWT Token:*  
> A secure JSON Web Token is issued upon successful login. This token can be used for authenticated API requests in future sessions.

---

### 5. 👤 Get All Users

**URL:** `https://www.bluebex.xyz/api/users/get-all-users`

**Method:** `GET`

#### 🔸 Response:

```json
{
    "users": [
        {
            "_id": "681c3f2a28183a62ac4f1b09",
            "phoneNumber": "8296823955",
            "name": "Mallikarjuna (test)",
            "isVerified": false,
            "companyName": "CompanyName not required for users",
            "firebaseToken": null,
            "appVersion": null,
            "role": "user",
            "createdAt": "2025-05-08T05:20:42.242Z",
            "updatedAt": "2025-05-08T05:20:42.242Z"
        },
        {
            "_id": "681c3f7228183a62ac4f1b0c",
            "phoneNumber": "8156815924",
            "name": "Albin (test)",
            "isVerified": false,
            "companyName": "CompanyName not required for users",
            "firebaseToken": null,
            "appVersion": null,
            "role": "user",
            "createdAt": "2025-05-08T05:21:54.012Z",
            "updatedAt": "2025-05-08T05:21:54.012Z"
        },
        {
            "_id": "681c3f8d28183a62ac4f1b0f",
            "phoneNumber": "8884983171",
            "name": "Balaji 2",
            "isVerified": true,
            "companyName": "CompanyName not required for users",
            "firebaseToken": null,
            "appVersion": null,
            "role": "user",
            "createdAt": "2025-05-08T05:22:21.533Z",
            "updatedAt": "2025-05-08T05:23:16.882Z"
        },
        {
            "_id": "681d91a677ee6298f3f03339",
            "phoneNumber": "8887564651",
            "name": "Vidhushi",
            "isVerified": false,
            "companyName": "CompanyName not required for users",
            "firebaseToken": null,
            "appVersion": null,
            "role": "user",
            "createdAt": "2025-05-09T05:24:54.707Z",
            "updatedAt": "2025-05-09T05:24:54.707Z"
        },
        {
            "_id": "681da08f77ee6298f3f03459",
            "phoneNumber": "9059763286",
            "name": "Test Number",
            "isVerified": false,
            "companyName": "CompanyName not required for users",
            "firebaseToken": null,
            "appVersion": null,
            "role": "user",
            "createdAt": "2025-05-09T06:28:31.442Z",
            "updatedAt": "2025-05-09T06:28:31.442Z"
        },
        {
            "_id": "681de26077ee6298f3f034ab",
            "phoneNumber": "1234567890",
            "name": "Meeting",
            "isVerified": false,
            "companyName": "CompanyName not required for users",
            "firebaseToken": null,
            "appVersion": null,
            "role": "user",
            "createdAt": "2025-05-09T11:09:20.013Z",
            "updatedAt": "2025-05-09T11:09:20.013Z"
        },
        {
            "_id": "682326d177ee6298f3f036c5",
            "phoneNumber": "9009009001",
            "name": "Working or not",
            "isVerified": false,
            "companyName": "CompanyName not required for users",
            "firebaseToken": null,
            "appVersion": null,
            "role": "user",
            "createdAt": "2025-05-13T11:02:41.039Z",
            "updatedAt": "2025-05-13T11:02:41.039Z"
        },
        {
            "_id": "682361f777ee6298f3f0370c",
            "phoneNumber": "919380386090",
            "name": "M4NOJBE",
            "isVerified": false,
            "companyName": "CompanyName not required for users",
            "firebaseToken": null,
            "appVersion": null,
            "role": "user",
            "createdAt": "2025-05-13T15:15:03.033Z",
            "updatedAt": "2025-05-13T15:15:03.033Z"
        }
    ]
}
```

---

### 6.  Add New User (Admin Only)

**URL:** `https://www.bluebex.xyz/api/users/admin/add-user`

**Method:** `POST`

**Description:** Allows an admin to add a new user.

#### 🔸 Headers:

```
Authorization: Bearer <JWT Token> : eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY4MmRhNjQ3NzdlZTYyOThmM2YwM2I4MCIsInJvbGUiOiJhZG1pbiIsImlhdCI6MTc0NzgyMzI4NywiZXhwIjoxNzc5MzgwODg3fQ.2XXiJuMJ3aaVp97s9xu5TxsTTYkcCoLrErgRPhY3q_
```

#### 🔸 Request Body:

```json
{
  "name": "Balaji",
  "phoneNumber": "9108105199"
}
```

#### 🔸 Response:

```json
{
    "message": "User added successfully",
    "newUser": {
        "phoneNumber": "8296823955",
        "name": "Mallikarujna",
        "isVerified": false,
        "companyName": "CompanyName not required for users",
        "firebaseToken": null,
        "appVersion": null,
        "role": "user",
        "_id": "682dab3077ee6298f3f03b94",
        "createdAt": "2025-05-21T10:30:08.202Z",
        "updatedAt": "2025-05-21T10:30:08.202Z",
        "__v": 0
    }
}
```
### Flow Explanation for Add User API
This API is designed to allow only **admin users** to add new users. The process includes three steps:

1. **Verify JWT Token**: The incoming request must contain a valid JWT token in the Authorization header. This token is decoded and attached to the request object.
2. **Verify Admin Role**: The decoded user data is checked to confirm that the user role is 'admin'. If not, the request is denied.
3. **Add User Logic**: If validation passes, a new user is created with the role set to 'user'. Company name is optional and defaults to a placeholder if not provided.

This ensures secure addition of users only by authenticated admin users. 
### The user added through this method does not need to register again — their data is already pre-filled by the admin.

### code Snippets: 

`router.post("/admin/add-user", verifyToken, verifyAdmin, addUser);`

***Verify Token***

```
const verifyToken = (req, res, next) => {
  const token = req.header("Authorization")?.split(" ")[1];    // Extract token from Authorization header
  
  if (!token) {
    return res.status(401).json({ message: "No token, authorization denied" });
  }

  try {
    const decoded = jwt.verify(token, process.env.JWT_SECRET);      // Verify the token
    req.user = decoded;                                             // Attach decoded user data (id, role) to the request object
    next();                                                        // Proceed to the next middleware or route handler
  } catch (err) {
    return res.status(400).json({ message: "Invalid token" , error: err.message });
  }
};
```

***Verify Admin***
```
const verifyAdmin = (req, res, next) => {
    
    // Check if the user is an admin
    if (req.user.role !== 'admin') {
      console.error(Access denied: User ${req.user.id} is not an admin.);
      
      return res.status(403).json({
        message: "Access denied",
        error: "Admin role is required to access this resource."
      });
    }
  
    // Proceed to the next middleware if the user is an admin
    next();
  };
```

***Adding user by admin***

```
//Adding the user by admin
const addUser = async (req, res) => {
  const { name, phoneNumber,companyName} = req.body;

  // Ensure name and phoneNumber are provided
  if (!name || !phoneNumber) {
    return res.status(400).json({ message: "Name and phone number are required" });
  }

  try {
    // Check if the user already exists
    const existingUser = await User.findOne({ phoneNumber });
    if (existingUser) {
      return res.status(400).json({ message: "User already exists" });
    }

    // Create new user with default role as 'user'
    const newUser = new User({
      name,
      phoneNumber,
      role: 'user',  // Default role for new users
      companyName: companyName || "CompanyName not required for users",
    });

    // Save new user to the database
    await newUser.save();

    // Respond with success
    res.status(201).json({ message: "User added successfully", newUser });
  } catch (error) {
    console.error("Error adding user:", error.message);
    res.status(500).json({ message: "Server error" , error : error.message });
  }
};
```

***images for reference***

![image](https://github.com/user-attachments/assets/026ef48a-e79a-41eb-b7d0-1b740cbbe09a)



![image](https://github.com/user-attachments/assets/e1afe1f8-16d6-449e-b4b3-163e37864bbe)



![image](https://github.com/user-attachments/assets/5546c446-c333-40af-834b-1f8d33a1537f)

---
### 7. Profile API(Get User Profile by Phone Number)


Retrieves a specific user's profile using their phone number.

*Endpoint:* /users/profile/:phoneNumber  

*Method:* GET 

```
https://www.bluebex.xyz/api/users/profile/:phoneNumber
``` 



### we don't require request body but we need a phonenumber for which we are able to get the profile details !!

#### Example Requests

GET https://www.bluebex.xyz/api/users/profile/9618863286

GET https://www.bluebex.xyz/api/users/profile/9515458476

GET https://www.bluebex.xyz/api/users/profile/9164949099


#### Example Response
```json
{
  "user": {
    "_id": "6808839a468826f796da3d94",
    "phoneNumber": "9618863286",
    "name": "Manikanta Vaddi",
    "isVerified": true,
    "companyName": "Spiway private Limited",
    "firebaseToken": "",
    "appVersion": "",
    "role": "admin",
    "createdAt": "2025-04-23T06:07:22.401Z",
    "updatedAt": "2025-05-02T06:32:34.289Z"
  }
}
```


#### Key Response Fields
| Field | Description |
|-------|-------------|
| *_id* | Unique identifier for the user |
| *name* | User's full name |
| *companyName* | Name of the user's company |
| *firebaseToken* | Token for push notifications |


---

### 8. 🧑‍💼 Get All Admins (Optional)

**URL:** `https://www.bluebex.xyz/api/users/get-all-admins`

**Method:** `GET`

**Description:** Fetches a list of users with the role of `admin`.

#### 🔸 Response:

```json
{
    "admins": [
        {
            "_id": "681dda3f77ee6298f3f03492",
            "phoneNumber": "9380386090",
            "name": "Manoj",
            "isVerified": true,
            "companyName": "BlueBex",
            "firebaseToken": "",
            "appVersion": "",
            "role": "admin",
            "createdAt": "2025-05-09T10:34:39.484Z",
            "updatedAt": "2025-05-21T09:36:57.176Z"
        },
        {
            "_id": "682d8ba277ee6298f3f03b4a",
            "phoneNumber": "9618863286",
            "name": "Manikanta Vaddi",
            "isVerified": true,
            "companyName": "Bluebex.in",
            "firebaseToken": "",
            "appVersion": "",
            "role": "admin",
            "createdAt": "2025-05-21T08:15:30.021Z",
            "updatedAt": "2025-05-21T08:15:41.697Z"
        },
        {
            "_id": "682da64777ee6298f3f03b80",
            "phoneNumber": "9108105199",
            "name": "Balaji S",
            "isVerified": true,
            "companyName": "Bluebex private Limited",
            "firebaseToken": "",
            "appVersion": "",
            "role": "admin",
            "createdAt": "2025-05-21T10:09:11.897Z",
            "updatedAt": "2025-05-21T10:12:30.576Z"
        }
    ]
}
```

---

### 🔒 1. MongoDB Atlas Setup

> -  Created a MongoDB Atlas account using your Bluebex mail.

> -  Created a Cluster (e.g., Cluster0).

> -  Created a Database User with username & password.

> -  Added IP Whitelist to allow access (e.g., 0.0.0.0/0 for all IPs).

> -  Copied the Connection URI from the Atlas dashboard.

***  Stored your connection string in .env:***

```
MONGODB_URI=mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/<dbname>?retryWrites=true&w=majority

```
* Used process.env.MONGODB_URI in your connect() function for security.

### code snippet

```
const connect = async () => {
    try {
      await mongoose.connect(process.env.MONGODB_URI); // Use environment variable for security
      console.log(" Connected to MongoDB");
    } catch (err) {
      console.error(" MongoDB connection error:", err.message);
    }
  };
```
---
### Work Contributions


***1.Balaji***

Created
> - Register API
> - Otp Verify for Register API
> - Login API
> - Otp verify For Login API
> - Profile API
> - Mongodb Atlas Connection        


***2. Manikanta***

Created
> - Get-all-users API

> - Add User by Admin API

> - Get-all-Admins API

> - Converted otp validation from PHP to Node.js using Two factor service 

#### Code contributions collaboratively written by @Balaji S and @Manikanta V 

*Note:*

*For more detailed documentation, please refer to the individual daily reports and the monthly report.*

Thank you 

Balaji S

Manikanta v


---


