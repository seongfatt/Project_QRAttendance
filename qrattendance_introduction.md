# 📲 QR Attendance System – Introduction & Visual Walkthrough

Welcome to the QR Attendance System! This mobile app ensures secure, GPS-verified attendance tracking using QR codes. Whether you're managing a conference, classroom, or corporate event, this system makes check-ins effortless and honest.

---

## 🎬 About the System

![About Screen](qr_image/about_qra.JPG)  
Say goodbye to messy sign-in sheets. This system ensures attendance is only recorded when the operator is physically present at the correct location.

---

## 🔐 Login & Authentication

![Login Screen](qr_image/login_qra.JPG)  
Operators log in using secure credentials to access the scanning interface.

---

## 📝 User Registration

![Register Screen](qr_image/register_qra.JPG)  
Users are registered and assigned unique QR codes tied to their User ID.

---

## 👥 Manage Users

![Manage Users](qr_image/manage_user_qra_1.JPG)  
Admins can view and manage user profiles and QR assignments.

---

## 🧭 Location Selection & Geo-fencing

Operators select the current event location from a dropdown menu.  
The app checks if the operator is within the GPS radius of the selected location.

| Step | Screenshot |
|------|------------|
| Location dropdown | ![Step 1](qr_image/Main_qra_scan_1.JPG) |
| GPS check prompt | ![Step 2](qr_image/Main_qra_scan_2.JPG) |
| Geo-fence warning | ![Step 3](qr_image/Main_qra_scan_3.JPG) |
| Valid location confirmation | ![Step 4](qr_image/Main_qra_scan_4.JPG) |

---

## 📷 QR Code Scanning

Once location is validated, the operator scans the user’s QR code.

| Step | Screenshot |
|------|------------|
| QR scan interface | ![Step 5](qr_image/Main_qra_scan_5.JPG) |
| Scan in progress | ![Step 6](qr_image/Main_qra_scan_6.JPG) |
| Scan success | ![Step 7](qr_image/Main_qra_scan_7.JPG) |
| Attendance confirmation | ![Step 8](qr_image/Main_qra_scan_9.jpg) |
| Attendance out of range | ![Step 9](qr_image/Main_qra_scan_8.jpg) |

---

## 🧾 Data Logged to Firebase

Each attendance record includes:

- `scannedUserId` – ID of the attendee  
- `scannerUserId` – ID of the operator  
- `timestamp` – Date and time of scan  
- `latitude` & `longitude` – Operator’s GPS location  
- `eventLocation` – Selected location name

Stored in:

- `attendance_logs/{scannedUserId}/{uniquePushId}`  
- `global_attendance_log/{uniquePushId}`

---

## 📅 View Attendance History

| View Type | Screenshot |
|-----------|------------|
| My Attendance | ![My Attendance](qr_image/ViewMyAttendance_qra_1.jpg) |
| Global Attendance | ![Global Attendance](qr_image/ViewGlobalAttendance_qra_1.jpg) |

Users can view their attendance history filtered by date and location. Admins can access global logs for reporting and audit.

---

## 🎯 Why Clients Love It

- ✅ No fake check-ins  
- ✅ Easy setup and secure scanning  
- ✅ Real-time data for reporting  
- ✅ Works great for events, schools, and teams

---

