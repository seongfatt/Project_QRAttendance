# 🎉 Welcome to the QR Attendance System!

Say goodbye to messy sign-in sheets and hello to smart, secure, location-aware attendance tracking.  
Whether you're running a conference, a classroom, or a corporate event—this system makes attendance effortless and foolproof.

---

## 🚀 What Is It?

The **QR Attendance System** is a mobile app that lets authorized staff scan user QR codes to record attendance—  
**but only** when they’re physically at the right location. Thanks to GPS geo-fencing, it’s not just smart—it’s honest.

---

## 🧠 How It Works (In Plain English)

1. Staff logs in to the app  
2. Selects the event location from a dropdown (e.g., “Main Hall”)  
3. App checks: “Are you really there?” using GPS  
4. If yes → ✅ Scan away!  
5. If no → ❌ “Too far from [Location Name]” 😬  
6. Attendance is recorded with timestamp, location, and user ID

---

## 🔍 Behind the Scenes

### 🛠️ Core Components

| Role      | Description                          |
|-----------|--------------------------------------|
| Operator  | Authorized staff scanning QR codes   |
| User      | Attendee with a unique QR code       |

---

### 📍 Location Logic

Each event location has:

- A name (e.g., “Event Hall 1”)  
- GPS coordinates  
- A radius (in meters)  

The app checks if the operator is within that zone before allowing scans.

---

### 📸 QRScannerActivity Highlights

- Dropdown for location selection  
- GPS geo-fencing validation  
- Location permission checks  
- QR code scanning with user ID extraction  
- Real-time attendance logging

---

## 🧰 Setup Checklist

Before you start scanning:

- ✅ Users registered (e.g., via Firebase Auth)  
- ✅ Each user has a QR code with their unique ID  
- ✅ Locations defined with GPS zones  
- ✅ Operators have login credentials

---

## 📊 Data That Gets Logged

Every attendance record includes:

- `scannedUserId` – Who showed up  
- `scannerUserId` – Who scanned them  
- `timestamp` – When it happened  
- `latitude` & `longitude` – Where it happened  
- `eventLocation` – Which location was selected

Stored in Firebase:

- `attendance_logs/{scannedUserId}/{uniquePushId}`  
- `global_attendance_log/{uniquePushId}`

---

## 📅 View Your History

Users can check their attendance anytime:

- Filter by date or location  
- See who scanned them  
- All pulled from Firebase with friendly names

---

## 🎯 Why Clients Love It

- ✅ No fake check-ins  
- ✅ Easy setup and secure scanning  
- ✅ Real-time data for reporting  
- ✅ Works great for events, schools, and teams

---
