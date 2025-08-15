 Smart Visitor & Threat Detection System using AWS

📌 Project Overview
The **Smart Visitor & Threat Detection System** is a face-recognition-based security solution that uses **AWS services** to allow or deny access to visitors.

- **Authorized Visitors**: Recognized automatically and granted access.
- **Unauthorized Visitors**: Must enter their name and email, and a request is sent to the admin for approval.
- If approved, the visitor receives an **email with a QR code** for entry.
- Voice feedback is provided for status ("Access Granted" or "Access Denied").

---

 🎯 Objectives
- Automate visitor identification and access control.
- Notify admin instantly when unauthorized visitors arrive.
- Use QR codes for secure, one-time access.
- Maintain a **visitor log** with details in **DynamoDB**.

---

 💡 Use Case
This system can be used in:
- Office entrances
- Residential apartments
- Private events
- Secure facilities

---

 🛠️ Prerequisites
Before starting this project, ensure you have:

Basic Requirements
- AWS account
- Basic knowledge of Python & Flask
- Laptop/PC with internet access

AWS Services Used
- S3 → Store authorized visitor images and new visitor uploads.
- Rekognition → Face detection and matching.
- Polly → Voice output for access status.
- SNS → Send alerts to the admin.
- SES → Send QR codes to approved visitors.
- DynamoDB → Store visitor logs.
- Lambda → Trigger specific actions.
- EC2 → Host Flask web app.

---

⚙️ Project Workflow

Step 1: Face Capture & Upload (OpenCV + AWS S3)
- Capture visitor's face using OpenCV.
- Upload image to **S3 bucket** for processing.

Step 2: Voice Feedback (AWS Polly)
- System announces "Authorized" or "Unauthorized" based on face recognition result.

Step 3: Unauthorized Visitor Alert (AWS SNS + Flask)
- If unauthorized, send visitor details to admin via SNS.
- Admin can **Approve** or **Deny** via a dashboard.

Step 4: Admin Dashboard
- Displays visitor photo, name, email, and decision buttons.

Step 5: Send Email with QR Code (AWS SES)
- Upon approval, visitor receives an email with:
  - QR code
  - Verification link

Step 6: QR Code Verification
- Visitor scans QR code on entry.
- If valid, access is granted.

Step 7: Store Visitor Data (DynamoDB)
- Fields stored:
  - Visitor ID → Unique ID for each visitor
  - Name → Visitor’s name
  - Email → Visitor’s email
  - Photo URL → Link to stored photo in S3
  - Timestamp → Date & time of visit
  - Status → Approved / Rejected


