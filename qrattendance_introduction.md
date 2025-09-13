# 📲 QR Attendance System – Visual Flow Guide

Welcome to the QR Attendance System! This guide walks you through the full attendance workflow using real screenshots from the app. Each step is GPS-verified, secure, and designed for smooth operator experience.

---

## 🎬 1. About the System

![About Screen](qr_image/about_qra.JPG)  
Say goodbye to messy sign-in sheets. This system ensures attendance is recorded only when the operator is physically present at the correct location.

---

## 🔐 2. Login & Authentication

![Login Screen](qr_image/login_qra.JPG)  
Operators log in using secure credentials to access the QR scanning interface.

---

## 📝 3. User Registration

![Register Screen](qr_image/register_qra.JPG)  
Users are registered and assigned unique QR codes tied to their User ID.

---

## 🧭 4. Location Selection

![Dropdown UI](qr_image/demo_qra_1.JPG)  
Operators select the current event location from a dropdown menu (e.g., “Main Hall”).

---

## 📍 5. GPS Geo-fencing Validation

![Geo-fence Warning](qr_image/demo_qra_2.JPG)  
The app checks if the operator is within the GPS radius of the selected location.  
If not: `"Too far from [Location Name]"` is displayed.

---

## 📷 6. QR Code Scanning

![Scan UI](qr_image/demo_qra_4.JPG)  
Once validated, the operator scans the user’s QR code using the device camera.

---

## ✅ 7. Attendance Confirmation

![Success Message](qr_image/demo_qra_6.JPG)  
If the scan is successful and location is valid, attendance is recorded with a confirmation message.

---

## 🧾 8. Data Logged to Firebase

| Field             | Description                          |
|------------------|--------------------------------------|
| `scannedUserId`  | ID of the attendee                   |
| `scannerUserId`  | ID of the operator                   |
| `timestamp`      | Date and time of scan                |
| `latitude`       | Operator’s GPS latitude              |
| `longitude`      | Operator’s GPS longitude             |
| `eventLocation`  | Selected location name               |

Stored in:

- `attendance_logs/{scannedUserId}/{uniquePushId}`  
- `global_attendance_log/{uniquePushId}`

---

## 📅 9. View Attendance History

![History Screen](qr_image/demo_qra_8.JPG)  
Users can view their attendance history filtered by date and location.

---

## 🧩 10. Extra Modules (Optional)

- **VGA Module** – Custom visual analytics  
  ![VGA Module](qr_image/VGA_qra_1.jpg)

- **VMA Module** – Attendance metrics dashboard  
  ![VMA Module](qr_image/VMA_qra_1.jpg)

- **MU Module** – Multi-user scan interface  
  ![MU Module](qr_image/mu_qra_1.JPG)

---

## 🎯 Why Clients Love It

- ✅ No fake check-ins  
- ✅ Easy setup and secure scanning  
- ✅ Real-time data for reporting  
- ✅ Works great for events, schools, and teams

---
