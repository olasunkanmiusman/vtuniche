### **Vtuniche API Documentation**

- **Base URL:** `https://api.vtuniche.com.ng/`
- **Headers:**
  ```json
  {
    'Content-Type': 'application/json',
    "authorization": "Bearer {YourToken}"
  }
  ```

---

### **1. Get User Information**

- **Endpoint:** `GET /userInfo/:id`
- **Request URL:** `https://api.vtuniche.com.ng/userInfo/{id}`
- **Body:** None
- **Functionality:** Retrieves user information.
- **Success Message:** `"user": object`
- **Error Message:** `"error": String`

---

### **2. Purchase Data**

- **Endpoint:** `POST /buy-data/:id`
- **Request URL:** `https://api.vtuniche.com.ng/buy-data/{id}`
- **Body:**
  ```json
  {
    "network": networkId,
    "mobile_number": phoneNumber,
    "plan": planId,
    "Ported_number": false,
    "description": description,
    "type": "mobile data",
    "pin": "your_transaction_pin",
    "networkType": "MTN_PLAN" || "GLO_PLAN" || "AIRTEL_PLAN" || "9MOBILE_PLAN"
  }
  ```
- **Functionality:** Purchase mobile data.
- **Success Message:** `"user": Object`
- **Error Message:** `"error": String`

---

### **3. Purchase Airtime**

- **Endpoint:** `POST /buy-airtime/:id`
- **Request URL:** `https://api.vtuniche.com.ng/buy-airtime/{id}`
- **Body:**
  ```json
  {
    "network": 1 || 2 || 3 || 4,  // Enum: 1=MTN, 2=Glo, 3=9mobile, 4=Airtel
    "pin": pin,
    "description": description,
    "type": "airtime",
    "amount": amount,
    "mobile_number": phoneNumber,
    "Ported_number": true,
    "airtime_type": "VTU"
  }
  ```
- **Functionality:** Purchase airtime.
- **Success Message:** `"user": object`
- **Error Message:** `"error": String`

---

### **4. Purchase Cable Subscription**

- **Endpoint:** `POST /cable-sub/:id`
- **Request URL:** `https://api.vtuniche.com.ng/cable-sub/{id}`
- **Body:**
  ```json
  {
    "pin": pin,
    "description": description,
    "type": "cable subscription",
    "cablename": 1 || 2 || 3,  // Enum: 1=GOTV, 2=DSTV, 3=Startime
    "cableplan": cablePlanId,
    "smart_card_number": smartCardNumber,
    "cableType": "DSTVPLAN" || "GOTVPLAN" || "STARTIMEPLAN"
  }
  ```
- **Functionality:** Purchase cable subscription.
- **Success Message:** `"user": object`
- **Error Message:** `"error": String`

---

### **5. Get Transaction History**

- **Endpoint:** `GET /transactions/:id`
- **Request URL:** `https://api.vtuniche.com.ng/transactions/{id}?pageNumber={pageNumber}&type={queryType}`
- **Params:**
  - `pageNumber`: Should start from `1` and above.
  - `type` (Optional): Could be `"cable subscription"`, `"airtime"`, `"mobile data"`, `"electricity bill"`.
- **Functionality:** Retrieve transaction history.
- **Success Message:** `Object`
- **Error Message:** `"error": string`

---

### **6. Purchase Electricity Bill**

- **Endpoint:** `POST /bill-payment/:id`
- **Request URL:** `https://api.vtuniche.com.ng/bill-payment/{id}`
- **Body:**
  ```json
  {
    "pin": pin,
    "description": description,
    "type": "electricity bill",
    "disco_name": discoName,
    "amount": amount,
    "meter_number": meterNumber,
    "MeterType": meterType
  }
  ```
- **Functionality:** Pay electricity bills.
- **Success Message:** `"user": object`
- **Error Message:** `"error": string`

---

### **Postman Testing Notes**

For each API endpoint:
1. **Set Method (GET/POST)**: Select the appropriate method (GET or POST).
2. **Set Authorization**: Set the authorization type to `Bearer Token` and paste your token.
3. **Add Body for POST Requests**: Ensure the JSON body is correct for POST requests.
4. **Check Response**: Look for success or error messages to validate the requests.
