# ACCESSFLOW-SAP-ABAP

A custom SAP ABAP Module Pool application designed to streamline role-based request management in a real-time enterprise scenario. It enables seamless communication between three distinct user roles: **Requester (A)**, **Approver (B)**, and **Issuer (C)**. The system handles request creation, approval, and issuance with robust validations, status tracking, number range-based request ID generation, and ALV-based reporting.

---


📂 Tech Stack
SAP ABAP Module Pool

Screen Painter

ALV Grid Display

Smart Forms

Z-tables

Number Ranges

BAPI_GOODSMVT_CREATE

---

## 🔧 Features

- **Multi-screen Navigation** via Module Pool (Screens: 100, 200, 300, 400)
- **Role-Based Access Control** using Z-table authentication (`ZTEST_AUTH`)
- **Request Creation** with auto-generated Request Numbers via number ranges
- **Request Approval & Issuance Flow**
- **Smart Forms** print preview for Requesters
- **BAPI Integration (`BAPI_GOODSMVT_CREATE`)** for Goods Issue
- **ALV Reporting** for Approver and Issuer
- **Custom Z-Tables**:
  - `ZTEST_AUTH`: Stores user credentials and user type (A/B/C)
  - `ZTABLE_REQ`: Stores request data


---

## 🧑‍💼 User Role-Based Navigation
<img width="1117" height="627" alt="image" src="https://github.com/user-attachments/assets/46846d2b-1a29-47fb-a7c9-7ede7416af67" />




### 🔐 Screen 100 – Login Page

- Authenticates user from `ZTEST_AUTH`
- Navigates to the respective screen based on user type (A/B/C)

📷 <img width="1600" height="854" alt="image" src="https://github.com/user-attachments/assets/dbc086a5-c156-450c-bacb-cc2236b13643" />


---

### 📝 Screen 200 – Requester (Type A)

- User enters:
  - Material
  - Plant
  - Quantity
- Smart Form Print Preview of the current and previous requests
- System generates a **unique Request Number** using number range
- Data saved in `ZTABLE_REQ`

📷 <img width="1365" height="716" alt="image" src="https://github.com/user-attachments/assets/bcc88138-635e-4005-8a73-03df1c017925" />


---

### ✅ Screen 300 – Approver (Type B)

- Views pending requests with:
  - Material, Quantity, Time
  - Current Stock Info
- Options to **Approve** or **Reject**
- Includes a **Search Bar** for direct Request Number lookup
- Approved requests become visible to Issuer

📷 <img width="1365" height="667" alt="image" src="https://github.com/user-attachments/assets/a0b27b1c-bd3b-467e-9601-053a1fe10666" />


---

### 📦 Screen 400 – Issuer (Type C)

- Sees approved requests
- Can **Issue** or **Reject** the request
- If Issued, invokes `BAPI_GOODSMVT_CREATE` for goods movement
- Issued request stored in `ZISSUED_REQ`

📷 <img width="1365" height="672" alt="image" src="https://github.com/user-attachments/assets/b812a9fd-0adb-4e45-92e2-e9e1fadb8569" />


---

## 🗃️ Z-Tables Structure

### 🔸 ZTEST_AUTH

- Fields: `USERNAME`, `PASSWORD`, `USER_TYPE`
- Used for login authentication and screen routing

📷 <img width="975" height="559" alt="image" src="https://github.com/user-attachments/assets/3c2db213-4644-4ab6-9e0b-434cb6aa1abb" />


---

### 🔸 ZTABLE_REQ

- Stores all pending and approved requests
- Used by Approver and Issuer roles

📷 <img width="975" height="481" alt="image" src="https://github.com/user-attachments/assets/b3f165df-6567-4017-9850-731cabc91d52" />


---

## 📄 Smart Form

- Generates printable request summary for Requesters
- Preview feature available on Screen 200

  <img width="1355" height="717" alt="image" src="https://github.com/user-attachments/assets/6047a80d-12e3-4744-b313-1d1642f91282" />

---  

## 🔌 BAPI Integration

Uses `BAPI_GOODSMVT_CREATE` to simulate real SAP Goods Issue after final approval. This automates inventory adjustments and reflects accurate stock movement.

---

👨‍💻 Developed By
Kunal Deshpande
B.Tech CSE @ Medi-Caps University
SAP ABAP Intern at VECV



