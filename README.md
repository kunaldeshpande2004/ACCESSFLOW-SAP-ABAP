# ACCESSFLOW-SAP-ABAP

A custom SAP ABAP Module Pool application designed to streamline role-based request management in a real-time enterprise scenario. It enables seamless communication between three distinct user roles: **Requester (A)**, **Approver (B)**, and **Issuer (C)**. The system handles request creation, approval, and issuance with robust validations, status tracking, number range-based request ID generation, and ALV-based reporting.

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

### 🔐 Screen 100 – Login Page

- Authenticates user from `ZTEST_AUTH`
- Navigates to the respective screen based on user type (A/B/C)

📷 

---

### 📝 Screen 200 – Requester (Type A)

- User enters:
  - Material
  - Plant
  - Quantity
- Smart Form Print Preview of the current and previous requests
- System generates a **unique Request Number** using number range
- Data saved in `ZTABLE_REQ`

📷 *Insert Screenshot of Request Creation Screen (Screen 200)*

---

### ✅ Screen 300 – Approver (Type B)

- Views pending requests with:
  - Material, Quantity, Time
  - Current Stock Info
- Options to **Approve** or **Reject**
- Includes a **Search Bar** for direct Request Number lookup
- Approved requests become visible to Issuer

📷 *Insert Screenshot of Approver Screen (Screen 300)*

---

### 📦 Screen 400 – Issuer (Type C)

- Sees approved requests
- Can **Issue** or **Reject** the request
- If Issued, invokes `BAPI_GOODSMVT_CREATE` for goods movement
- Issued request stored in `ZISSUED_REQ`

📷 *Insert Screenshot of Issuer Screen (Screen 400)*

---

## 🗃️ Z-Tables Structure

### 🔸 ZTEST_AUTH

- Fields: `USERNAME`, `PASSWORD`, `USER_TYPE`
- Used for login authentication and screen routing

📷 *Insert Screenshot of ZTEST_AUTH Table*

---

### 🔸 ZTABLE_REQ

- Stores all pending and approved requests
- Used by Approver and Issuer roles

📷 *Insert Screenshot of ZTABLE_REQ Table*

---



## 📈 ALV Reports

- Approver and Issuer screens display tabular request data using ALV
- Improves readability and decision-making

---

## 📄 Smart Form

- Generates printable request summary for Requesters
- Preview feature available on Screen 200

---

## 🔌 BAPI Integration

Uses `BAPI_GOODSMVT_CREATE` to simulate real SAP Goods Issue after final approval. This automates inventory adjustments and reflects accurate stock movement.

---

## 🚀 Future Enhancements

- Add email notifications for status changes
- Implement transaction logs with timestamps
- Enhance search and filter functionality in ALV reports

---

## 📁 Screenshots

*(Upload your screenshots and replace the placeholders above with image links using markdown syntax like:)*

```markdown
![Login Screen](screenshots/login.png)

