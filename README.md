# About QR Attendance System

This document outlines the **QR Attendance System**, a mobile application designed to efficiently record user attendance at specific physical locations. The system uses operator-controlled QR code scanning and leverages GPS geo-fencing to ensure that attendance is recorded only when the operator is physically present at the designated location.

## Core Functionality: Admin-Operated QR Scanning

The primary method for recording attendance is an operator using the `QRScannerActivity` in the Android application.

-   **Operator (Admin/Staff):** An individual with authorized access to the application.
-   **User (Attendee):** An individual with a unique QR code whose attendance needs to be recorded.

### Key Features of the QRScannerActivity:

-   **Location Selection:** The operator must choose their current physical event location from a dropdown menu (e.g., "Main Event Hall," "Event Hall 1").
-   **GPS Geo-fencing:** The system uses GPS to verify the operator's proximity to the selected location before allowing attendance to be recorded. Each defined location is associated with specific GPS coordinates and a radius.
-   **Permission Handling:** The app requests and checks for necessary location permissions.
-   **User Identification:** The operator scans a QR code presented by the user, which contains their unique identifier.

---

## Setup Prerequisites

Before using the attendance system, you need to complete the following setup steps:

1.  **User Registration:** All users must be registered in the system (e.g., Firebase Authentication) and have a unique User ID.
2.  **User QR Codes:** Each user must be given a QR code that encodes their unique User ID.
3.  **Location Configuration:**
    -   Define the names of the scannable event locations (e.g., "Main Event Hall") within the `QRScannerActivity` code.
    -   Each location must be configured with precise GPS latitude, longitude, and an acceptable radius (in meters) within the `setupLocationZones()` method of the `QRScannerActivity.java` file.
4.  **Operator Access:** Operators must have valid credentials to log into the Android application.

---

## Attendance Recording Workflow

Here's the step-by-step process for an operator recording attendance using the `QRScannerActivity`:

1.  **Login:** The operator logs into the Android application.
2.  **Navigate to QR Scanner:** The operator opens the "QR Scanner" screen.
3.  **Select Event Location:** The operator chooses the current physical location from the dropdown menu.
4.  **Permissions:** If location permissions have not been granted, the app will prompt for them.
5.  **Enable Scan Button:** The "Scan QR at Selected Location" button becomes active only after a valid location is chosen and location permissions are granted.
6.  **Initiate Scan:** The operator clicks the "Scan QR at Selected Location" button.
7.  **Geo-fence Validation:**
    -   The app retrieves the operator's current GPS coordinates.
    -   It compares these coordinates to the pre-defined GPS zone for the selected location.
    -   If the operator is **outside the zone**, a "Too far from [Location Name]" message is displayed.
8.  **Scan User's QR Code:** The device camera activates, and the operator scans the user's QR code.
9.  **Record Data:** Upon a successful scan and geo-fence validation, the user's ID is extracted from the QR code, and an attendance record is created.
10. **Confirmation:** A "Attendance Recorded" message is displayed on the screen.

---

## Data Storage

### Attendance Record Data

Each attendance event captures the following information:

-   `scannedUserId`: The unique ID of the user whose attendance was recorded.
-   `scannerUserId`: The unique ID of the operator who performed the scan.
-   `timestamp`: The date and time of the scan.
-   `latitude`: The operator's device latitude at the time of the scan.
-   `longitude`: The operator's device longitude at the time of the scan.
-   `eventLocation`: The descriptive name of the location selected by the operator.

### Firebase Realtime Database

Attendance records are saved to the following paths in Firebase:

-   `attendance_logs/{scannedUserId}/{uniquePushId}`: Stores records specific to each user.
-   `global_attendance_log/{uniquePushId}`: A comprehensive log of all attendance events.

---

## Viewing Attendance History

The application also includes an `AttendanceActivity` where authenticated users can view their own attendance history. This history can be filtered by date and location. User and scanner names are displayed by fetching them from the database based on their IDs.
