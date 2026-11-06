# CLOUDMEDIX
### Secure Cloud-Based Healthcare Record Management System

[![Build Status](https://img.shields.io/badge/Build-Passing-emerald)](https://github.com/)
[![License](https://img.shields.io/badge/License-MIT-blue)](https://github.com/)
[![Cloud Engine](https://img.shields.io/badge/Cloud-Google%20Firebase-orange)](https://firebase.google.com/)
[![React](https://img.shields.io/badge/Frontend-React%2018%20%7C%20TypeScript-sky)](https://react.dev/)

**CloudMedix** is a cloud-native, production-grade Electronic Health Record (EHR) & Healthcare SaaS Management System. Built with **React 18**, **TypeScript**, **Vite**, **Tailwind CSS**, and **Firebase Services** (Authentication, Firestore Database, Cloud Storage, Hosting), it provides multi-role management for **Patients**, **Doctors**, **Hospital Staff**, and **Administrators**.

---

## 🌟 Key Features & Role Portals

### 1. 🏥 Patient Portal (`/patient/*`)
- **EHR Encounter History**: View longitudinal clinical records, diagnoses, symptoms, and treatment plans.
- **Digital Prescriptions**: Access active prescriptions with a printable medical prescription view (Rx format).
- **Laboratory Reports**: Download encrypted PDF diagnostic test results stored in Firebase Storage.
- **Appointments Manager**: Book, view, or cancel medical consultations with specialists.
- **Security Center**: View session status, login activity, active role, and trigger password resets.

### 2. 🩺 Doctor Portal (`/doctor/*`)
- **Authorized Patient Roster**: Access assigned patient charts guarded by zero-trust security rules.
- **EHR Encounters Generator**: Document clinical visit details, diagnoses, symptoms, and treatment plans.
- **Prescription Center**: Issue prescriptions with automated dosage and frequency validation.
- **Lab Upload Manager**: Upload PDF/image lab reports directly to Firebase Storage with size/type checks.
- **Consultation Schedule**: Manage daily outpatient queues and update appointment statuses.

### 3. 📋 Hospital Staff Portal (`/staff/*`)
- **Outpatient Registration**: Register new patients and create master demographic profiles.
- **Appointment Desk**: Schedule consultations with hospital specialists across departments.
- **Administrative Documents**: Upload consent forms, admission notices, and policy records.

### 4. 🛡️ System Administrator Portal (`/admin/*`)
- **User Role Management**: Elevate user roles (`PATIENT`, `DOCTOR`, `STAFF`, `ADMIN`) and suspend/reactivate accounts.
- **Immutable System Audit Stream**: Real-time log table capturing all system events (`LOGIN`, `VIEW_RECORD`, `CREATE_RECORD`, `DOWNLOAD_DOCUMENT`, `ACCESS_DENIED`).
- **Security Center**: Threat monitoring, failed login tracking, and Firestore Security Rules health checks.
- **1-Click Cloud Seeder**: Automated seed button to populate Cloud Firestore with realistic demo records.

---

## ☁️ Free Cloud Platform & Stack

| Layer | Technology / Cloud Service | Free Tier / No-Cost Implementation |
| :--- | :--- | :--- |
| **Frontend UI** | React 18, TypeScript, Tailwind CSS, Lucide Icons | Open Source / Client-Side SPA |
| **Authentication** | Firebase Authentication | Free Tier (Unlimited Email/Password Auth) |
| **Database** | Cloud Firestore | Free Tier (50,000 Reads, 20,000 Writes / day) |
| **File Storage** | Firebase Storage | Free Tier (5 GB Encrypted Document Storage) |
| **Global Hosting** | Firebase Hosting | Free Tier (10 GB Storage, Free SSL/TLS) |

---

## 🔑 Demo Account Credentials

CloudMedix includes built-in demo personas for instant 1-click evaluation from the Login page or Landing page:

| Persona Role | Email Credential | Account Name | Default Capabilities |
| :--- | :--- | :--- | :--- |
| **DOCTOR** | `doctor@cloudmedix.demo` | Dr. Arun Kumar | Cardiology Specialist, Create EHR & Rx |
| **PATIENT** | `patient@cloudmedix.demo` | Rahul Sharma | View EHR, Print Rx, Download Reports |
| **STAFF** | `staff@cloudmedix.demo` | Priya Menon | Patient Registration & Appointment Desk |
| **ADMIN** | `admin@cloudmedix.demo` | System Administrator | Role Management & System Audit Logs |

---

## 📁 Project Structure

```
c:/cloud computing/
├── docs/                      # Comprehensive Documentation Suite
│   ├── architecture.md        # System Architecture & Topology
│   ├── database.md            # Firestore Data Schema & Collections
│   ├── security.md            # Security Architecture & Rules
│   ├── deployment.md          # Firebase Hosting & Deployment Guide
│   └── testing.md             # Quality Assurance Test Plan
├── firestore.rules            # Strict Firestore Security Rules
├── storage.rules              # Firebase Storage Access & File Rules
├── firestore.indexes.json     # Firestore Query Indexes
├── firebase.json              # Firebase Hosting Configuration
├── .env.example               # Firebase Credentials Template
├── src/
│   ├── components/            # Reusable UI, Medical & Security Components
│   ├── contexts/              # AuthContext, ToastContext, NotificationContext
│   ├── firebase/              # Firebase Initialization & Demo Seed Dataset
│   ├── hooks/                 # Custom React Hooks (useAuth, useFirestore, useAuditLog)
│   ├── layouts/               # AppLayout & PublicLayout
│   ├── pages/                 # Public, Patient, Doctor, Staff & Admin Pages
│   ├── routes/                # Protected Routes & Role Guards
│   ├── services/              # Auth, Firestore, Storage & Audit Services
│   ├── types/                 # TypeScript Domain Interfaces
│   ├── App.tsx
│   └── main.tsx
├── package.json
└── README.md
```

---

## 🚀 Local Development & Execution

### 1. Install Dependencies
```bash
npm install
```

### 2. Configure Environment Variables (Optional for Live Firebase)
Create a `.env` file from `.env.example` with your Firebase web configuration:
```env
VITE_FIREBASE_API_KEY=AIzaSy...
VITE_FIREBASE_AUTH_DOMAIN=cloudmedix-demo.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=cloudmedix-demo
VITE_FIREBASE_STORAGE_BUCKET=cloudmedix-demo.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=123456789012
VITE_FIREBASE_APP_ID=1:123456789012:web:abcdef
```
*Note: If `.env` is omitted, CloudMedix runs in standalone local memory demo mode.*

### 3. Run Development Server
```bash
npm run dev
```
Open `http://localhost:3000` in your browser.

### 4. Build Production App
```bash
npm run build
```

---

## 🔒 Firebase Security Rules Deployment

Deploy security rules using Firebase CLI:
```bash
npx firebase-tools deploy --only firestore,storage
```

---

## 📄 Licensing & Academic Usage
Built as a demonstration project for Cloud Computing, Software Engineering, and Cybersecurity technical reviews. All demo patient records are fictional.
