# PawAlert – Community Dog Rescue & Safety Network

PawAlert is a full-stack, production-quality web application designed to connect citizens, pet owners, volunteers, NGOs, veterinarians, and admins for rapid dog rescue, reunification, medical aid, and adoption placement.

---

## 🌟 Key Features

1. **Role-Based Authentication**:
   - Roles: `Pet Owner`, `Volunteer Rescuer`, `NGO Representative`, `Veterinarian Doctor`, `Admin`.
   - JWT authentication + 1-Click Quick Demo Login Switcher on all pages.

2. **Report Lost, Found, Injured, or Abandoned Dogs**:
   - Form with image upload preview, landmark details, injury severity, and weather risk factors.
   - Interactive **Leaflet GPS MapPicker** for pinpointing exact rescue coordinates.

3. **AI Rescue Priority Score Engine**:
   - Algorithm calculates urgency score (0-100) based on injury severity, weather hazards, and report freshness.
   - Dynamic badges: `CRITICAL`, `HIGH`, `MEDIUM`, `LOW`.

4. **AI Dog Image Matcher Engine**:
   - Visual side-by-side photo comparison modal matching uploaded dog photos against active reports with confidence % score.

5. **Interactive Live Rescue Map**:
   - Leaflet map with color-coded pin markers (Red = Injured, Orange = Lost, Blue = Found, Purple = Abandoned, Green = Rescued).

6. **Rescue Progress Lifecycle & Community Live Chat**:
   - Visual step timeline (`Pending` -> `Assigned` -> `En Route` -> `Rescued` -> `Reunified`).
   - In-app live chat for incident communications between reporters and rescuers.

7. **Pet Collar QR Code Generator**:
   - Generates downloadable and printable QR codes encoding owner contact info, microchip ID, and vaccination status.

8. **Forever Homes Adoption Portal**:
   - Catalog of rescued dogs ready for adoption with age/breed filters and inline application form.

9. **Veterinary & Emergency Directory**:
   - 24/7 emergency hotline buttons, clinic search, opening hours, and medical services list.

10. **Analytics & Admin Dashboards**:
    - Chart.js visualizations for monthly rescue trends, category doughnut charts, top volunteer leaderboard.
    - Admin panel to approve NGOs/vets, manage users, and moderate reports.

11. **Multi-Language & Dark Mode**:
    - Complete translation bindings for **English (EN)**, **Tamil (TA)**, and **Hindi (HI)**.
    - Modern dark/light theme switcher.

---

## 📁 Project Architecture

```
design project/
├── backend/
│   ├── config/
│   │   └── db.js
│   ├── controllers/
│   │   ├── adminController.js
│   │   ├── adoptionController.js
│   │   ├── analyticsController.js
│   │   ├── authController.js
│   │   ├── chatController.js
│   │   ├── reportController.js
│   │   ├── vetController.js
│   │   └── volunteerController.js
│   ├── middleware/
│   │   ├── authMiddleware.js
│   │   └── errorMiddleware.js
│   ├── models/
│   │   ├── AdoptionDog.js
│   │   ├── ChatMessage.js
│   │   ├── Report.js
│   │   ├── RescueTask.js
│   │   ├── User.js
│   │   └── VetClinic.js
│   ├── routes/
│   │   ├── adminRoutes.js
│   │   ├── adoptionRoutes.js
│   │   ├── analyticsRoutes.js
│   │   ├── authRoutes.js
│   │   ├── chatRoutes.js
│   │   ├── reportRoutes.js
│   │   ├── vetRoutes.js
│   │   └── volunteerRoutes.js
│   ├── utils/
│   │   ├── aiImageMatcher.js
│   │   ├── aiPriorityScore.js
│   │   └── seedData.js
│   ├── server.js
│   ├── .env.example
│   └── package.json
├── frontend/
│   ├── public/
│   │   └── favicon.svg
│   ├── src/
│   │   ├── components/
│   │   │   ├── AIImageMatcherModal.jsx
│   │   │   ├── ChatModal.jsx
│   │   │   ├── Footer.jsx
│   │   │   ├── LiveMap.jsx
│   │   │   ├── MapPicker.jsx
│   │   │   ├── Navbar.jsx
│   │   │   ├── PriorityBadge.jsx
│   │   │   ├── QRCodeModal.jsx
│   │   │   └── RescueTimeline.jsx
│   │   ├── context/
│   │   │   ├── AuthContext.jsx
│   │   │   ├── LanguageContext.jsx
│   │   │   └── ThemeContext.jsx
│   │   ├── pages/
│   │   │   ├── AdminDashboard.jsx
│   │   │   ├── AdoptionPortal.jsx
│   │   │   ├── AnalyticsDashboard.jsx
│   │   │   ├── CreateReport.jsx
│   │   │   ├── Home.jsx
│   │   │   ├── Login.jsx
│   │   │   ├── PetQRGenerator.jsx
│   │   │   ├── Register.jsx
│   │   │   ├── ReportDetails.jsx
│   │   │   ├── ReportsList.jsx
│   │   │   ├── VetDirectory.jsx
│   │   │   └── VolunteerDashboard.jsx
│   │   ├── services/
│   │   │   ├── api.js
│   │   │   └── translations.js
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css
│   ├── index.html
│   ├── vite.config.js
│   ├── tailwind.config.js
│   ├── postcss.config.js
│   └── package.json
└── README.md
```

---

## ⚙️ Local Installation & Running Steps

### Prerequisites
- **Node.js**: v18.0.0 or above
- **npm**: v9.0.0 or above

### 1. Install Backend Dependencies & Start Server
```bash
cd backend
npm install
npm start
```
*Backend server will start at `http://localhost:5000` with built-in dataset fallback.*

### 2. Install Frontend Dependencies & Start App
In a new terminal window:
```bash
cd frontend
npm install
npm run dev
```
*Frontend application will launch at `http://localhost:5173`.*

---

## 🚀 Deployment Instructions

### Deploying Backend (Render / Railway / Vercel Serverless):
1. Push code to GitHub repository.
2. Set Environment Variables:
   - `PORT=5000`
   - `MONGODB_URI=your_mongodb_atlas_connection_string`
   - `JWT_SECRET=your_secret_key`
   - `CLIENT_URL=https://your-frontend-domain.com`

### Deploying Frontend (Vercel / Netlify / Cloudflare Pages):
1. Select `frontend` root directory.
2. Set build command: `npm run build`.
3. Set output directory: `dist`.
