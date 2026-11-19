<div align="center">
  <img src="resume-lens-logo.png" alt="Resume Lens Logo" width="200"/>
  
  ## Resume Lens — AI-powered Resume Analyzer
  
  **Elevate your resume with AI-powered analysis and feedback**
  
  A comprehensive resume analysis platform powered by Google Gemini AI that provides ATS scores, detailed feedback, and actionable recommendations to improve your resume.
  
  [![Made with React](https://img.shields.io/badge/Made%20with-React-61DAFB?logo=react)](https://reactjs.org/)
  [![Node.js](https://img.shields.io/badge/Node.js-339933?logo=node.js&logoColor=white)](https://nodejs.org/)
  [![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?logo=postgresql&logoColor=white)](https://www.postgresql.org/)
  [![Prisma](https://img.shields.io/badge/Prisma-2D3748?logo=prisma&logoColor=white)](https://www.prisma.io/)
  
</div>

---

## ✨ Features

- 🔐 **Secure Authentication** - User signup/login with JWT-based authentication
- 📄 **Resume Upload** - Support for PDF resume uploads
- 🤖 **AI-Powered Analysis** - Comprehensive resume analysis using Google Gemini AI
- 📊 **ATS Score** - Get your Applicant Tracking System compatibility score
- 💡 **Detailed Feedback** - Section-wise analysis and improvement suggestions
- 🎨 **Modern UI** - Beautiful, responsive interface built with React and TailwindCSS
- 🔍 **OCR Support** - Extract text from image-based PDFs using Tesseract OCR

---

## 🏗️ Tech Stack

### Frontend

- React 19.2.0
- Vite
- TailwindCSS
- React Router DOM
- Axios
- Lucide React Icons

### Backend

- Node.js + Express
- Prisma ORM
- PostgreSQL
- JWT Authentication
- Google Gemini AI API
- Multer (File uploads)

### OCR Service (Optional)

- Python Flask
- Tesseract OCR
- pdf2image

---

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v18 or higher) - [Download](https://nodejs.org/)
- **PostgreSQL** (v14 or higher) - [Download](https://www.postgresql.org/download/)
- **Python** (v3.10 or higher) - Required for OCR service - [Download](https://python.org/)
- **Git** - [Download](https://git-scm.com/)

---

## 📥 Installation

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/yourusername/ai-resume-analyzer.git
cd ai-resume-analyzer
```

---

### 2️⃣ Database Setup

1. **Install PostgreSQL** and ensure it's running
2. **Create a new database**:

```sql
CREATE DATABASE resume_analyzer;
```

3. **Note your database credentials** for the `.env` file

---

### 3️⃣ Backend Setup

Navigate to the backend directory:

```bash
cd backend
```

#### Create `.env` file

Create a `.env` file in the `backend` directory with the following configuration:

```env
# Database Configuration
DATABASE_URL="postgresql://YOUR_USERNAME:YOUR_PASSWORD@localhost:5432/resume_analyzer?schema=public"

# Example: DATABASE_URL="postgresql://postgres:admin123@localhost:5432/resume_analyzer?schema=public"

# JWT Secret (Generate a random string for production)
JWT_SECRET="your_super_secret_jwt_key_change_this_in_production"

# Google Gemini AI API Key
# Get your API key from: https://makersuite.google.com/app/apikey
GEMINI_API_KEY="your_gemini_api_key_here"

# OCR Service URL (Python Flask service)
OCR_API_URL="http://localhost:5000/ocr"

# Server Port
PORT=3000
```

#### Install Dependencies

```bash
npm install
```

#### Run Database Migrations

```bash
npx prisma migrate dev
```

#### Generate Prisma Client

```bash
npx prisma generate
```

#### Start the Backend Server

```bash
npm start
```

The backend server will start on `http://localhost:3000`

---

### 4️⃣ Frontend Setup

Open a **new terminal** and navigate to the frontend directory:

```bash
cd frontend
```

#### Create `.env` file (Optional)

Create a `.env` file in the `frontend` directory if you need custom configuration:

```env
# Backend API URL
VITE_API_URL=http://localhost:3000

# OCR Service URL
VITE_OCR_URL=http://localhost:5000
```

> **Note:** These are the default values. You only need this file if you're using different ports.

#### Install Dependencies

```bash
npm install
```

#### Start the Frontend Development Server

```bash
npm run dev
```

The frontend will start on `http://localhost:5173` (or another port if 5173 is busy)

---

### 5️⃣ OCR Service Setup (Optional but Recommended)

The OCR service is used to extract text from image-based PDFs.

Open a **new terminal** and navigate to the OCR service directory:

```bash
cd python-tesseract-ocr
```

#### Install Python Dependencies

```bash
pip install -r requirements.txt
```

#### Install Tesseract OCR

**Windows:**

- Download installer from: https://github.com/UB-Mannheim/tesseract/wiki
- Install and add to PATH

**macOS:**

```bash
brew install tesseract
```

**Linux (Ubuntu/Debian):**

```bash
sudo apt-get install tesseract-ocr
```

#### Start the OCR Service

```bash
python main.py
```

The OCR service will start on `http://localhost:5000`

---

## 🎯 Running the Complete Application

You need to run all three services simultaneously:

### Option 1: Manual (3 separate terminals)

**Terminal 1 - Backend:**

```bash
cd backend
npm start
```

**Terminal 2 - Frontend:**

```bash
cd frontend
npm run dev
```

**Terminal 3 - OCR Service:**

```bash
cd python-tesseract-ocr
python main.py
```

### Option 2: Using the Batch Script (Windows)

```bash
run-all.bat
```

---

## 📁 Project Structure

```
ai-resume-analyzer/
├── backend/                 # Node.js Express Backend
│   ├── lib/                # Database client
│   ├── middleware/         # Authentication middleware
│   ├── prisma/            # Database schema & migrations
│   ├── routes/            # API routes
│   ├── uploads/           # Uploaded resume files
│   ├── utils/             # Utility functions
│   ├── server.js          # Main server file
│   └── .env               # Backend environment variables
│
├── frontend/              # React Frontend
│   ├── src/
│   │   ├── components/   # Reusable components
│   │   ├── pages/        # Page components
│   │   ├── hooks/        # Custom React hooks
│   │   ├── assets/       # Static assets
│   │   ├── App.jsx       # Main App component
│   │   └── config.js     # Frontend configuration
│   └── .env              # Frontend environment variables
│
├── python-tesseract-ocr/ # OCR Service
│   ├── main.py           # Flask application
│   └── requirements.txt  # Python dependencies
│
├── resume-lens-logo.png      # Application logo
└── README.md             # This file
```

---

## 🔑 Getting API Keys

### Google Gemini AI API Key

1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Click "Create API Key"
4. Copy the API key and add it to your `backend/.env` file

---

## 🧪 Testing the Application

1. Open your browser and navigate to `http://localhost:5173`
2. **Register** a new account
3. **Login** with your credentials
4. **Upload** a PDF resume
5. **View** the AI-generated analysis with ATS score and feedback

---

## 📝 Environment Variables Reference

### Backend (.env)

| Variable         | Description                  | Example                                                                       |
| ---------------- | ---------------------------- | ----------------------------------------------------------------------------- |
| `DATABASE_URL`   | PostgreSQL connection string | `postgresql://postgres:password@localhost:5432/resume_analyzer?schema=public` |
| `JWT_SECRET`     | Secret key for JWT tokens    | `your_super_secret_key`                                                       |
| `GEMINI_API_KEY` | Google Gemini AI API key     | `AIzaSy...`                                                                   |
| `OCR_API_URL`    | URL of the OCR service       | `http://localhost:5000/ocr`                                                   |
| `PORT`           | Backend server port          | `3000`                                                                        |

### Frontend (.env) - Optional

| Variable       | Description     | Default                 |
| -------------- | --------------- | ----------------------- |
| `VITE_API_URL` | Backend API URL | `http://localhost:3000` |
| `VITE_OCR_URL` | OCR service URL | `http://localhost:5000` |

---

## 🛠️ Troubleshooting

### Database Connection Issues

- Ensure PostgreSQL is running
- Verify database credentials in `.env`
- Check if the database `resume_analyzer` exists

### Port Already in Use

- Backend (3000): Change `PORT` in `backend/.env`
- Frontend (5173): Vite will automatically use the next available port
- OCR (5000): Modify port in `python-tesseract-ocr/main.py`

### OCR Not Working

- Ensure Tesseract is installed and in PATH
- Verify Python dependencies are installed
- Check OCR service is running on port 5000

### Prisma Errors

```bash
npx prisma generate
npx prisma migrate reset
```

---

## 👨‍💻 Author

Created by Ekank

---

## 🌟 Show Your Support

Give a ⭐️ if this project helped you!
