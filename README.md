# Optics Shop CRM System 👓

![.NET Core](https://img.shields.io/badge/.NET%20Core-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white)

A comprehensive, production-ready Customer Relationship Management (CRM) system developed specifically for optical shops. This web application streamlines daily operations, manages customer profiles and optical details, and automates patient follow-ups to enhance customer engagement.

---

## 📸 Screenshots

| Login Page | 
 <img width="1915" height="928" alt="Screenshot 2026-09-16 170013" src="https://github.com/user-attachments/assets/bb4afae1-94c3-461e-84bd-91f4e3f3721d" />
 Dashboard |
 <img width="1884" height="959" alt="Screenshot 2026-09-16 170140" src="https://github.com/user-attachments/assets/d3a25151-6351-4a7c-a94e-a3e127987c3f" />

|

| Patients & Products/Examinations Management |
|:---:|
| <img width="1902" height="928" alt="Screenshot 2026-09-16 170518" src="https://github.com/user-attachments/assets/57a70781-cf50-4885-a62b-4a0dcd60f290" /> |
| <img width="1896" height="943" alt="Screenshot 2026-09-16 171014" src="https://github.com/user-attachments/assets/b5d240d0-3644-40a6-83e1-5db8b7649844" /> |
|<img width="889" height="969" alt="Screenshot 2026-09-16 171145" src="https://github.com/user-attachments/assets/8c73f601-6e1f-42ab-a24f-086fa8bf29e2" />   |

---

## ✨ Key Features

* **Comprehensive Patient Management:** Easily store and retrieve patient profiles, including primary and secondary contact details[cite: 1].
* **Optical Records & Prescriptions:** Track detailed optical measurements (SPH, CYL, AXIS, ADD, V.A, IPD) for both eyes, along with attached images of glasses or medical documents.
* **Smart WhatsApp Integration:** One-click automated WhatsApp messaging for sending welcome messages and smart follow-up alerts[cite: 1].
* **Automated Looping Reminders:** The system intelligently tracks patient appointments and automatically schedules looping 6-month reminders for periodic eye check-ups.
* **Prescription Printing & Excel Export:** Generate and print customized medical prescriptions directly from the browser, and export weekly reminder schedules to Excel (CSV) with full Arabic language support.
* **Secure Authentication:** Implemented secure authentication and role-based authorization using ASP.NET Identity[cite: 1].
* **Interactive UI/UX:** Utilizes AJAX, DataTables, and SweetAlert2 for a seamless, page-reload-free user experience (e.g., Quick Add Patient models and History Timelines).

---

## 🛠️ Tech Stack

**Backend:**
* ASP.NET Core MVC (C#)[cite: 1]
* Entity Framework Core (Code-First Approach)[cite: 1]
* ASP.NET Identity for Security[cite: 1]
* LINQ[cite: 1]

**Frontend:**
* Razor Pages
* HTML5, CSS3, JavaScript
* Bootstrap 5 & FontAwesome
*  AJAX, DataTables, SweetAlert2, Select2



---

## 🧠 What I Learned & Challenges Overcome

Building and deploying this production system presented several real-world challenges that significantly improved my skills as a .NET Developer:

1. **Securing Production Credentials:** 
   * *Challenge:* Hardcoding database connection strings in `appsettings.json` is a major security risk, especially when pushing to GitHub.
   * *Solution:* I implemented a secure architecture where the local environment reads the connection string securely from `launchSettings.json`, while the production server reads it from **Environment Variables** injected via the IIS Application Pool / `web.config`. This completely isolated sensitive data from the source code.

2. **Managing Server-Side File Uploads & Migrations:** 
   * *Challenge:* Encountered partial data loss of uploaded images due to shared hosting storage node migrations.
   * *Solution:* Standardized the image upload service to correctly map physical paths using `IWebHostEnvironment`, implemented robust file validation, and established a direct communication protocol with the hosting provider to restore backups and monitor the `wwwroot` directory structure.

3. **Complex Asynchronous UI Workflows:** 
   * *Challenge:* The client requested a continuous "looping" reminder system where confirming a patient contact would instantly prompt to reschedule the next appointment without refreshing the page.
   * *Solution:* Engineered a dynamic nested modal system using SweetAlert2 and jQuery AJAX. Handled the asynchronous HTTP POST requests to update the `NextExamDate` in the database, while simultaneously updating the frontend DataTables and notification badges in real-time.

4. **Database Optimization:** 
   * *Challenge:* As the patient records grew, querying full histories became slower.
   * *Solution:* Utilized `.AsNoTracking()` in Entity Framework Core for read-only operations (like filling DataTables and Excel exports) and optimized LINQ queries to minimize database roundtrips.

---
## 📬 Contact & Links
* **Developer:** Zaid Yasser Mallah
* **LinkedIn:** [Zaid Mallah](https://www.linkedin.com/in/zaidyasser)
* **Email:** zaidalmallah444@gmail.com
