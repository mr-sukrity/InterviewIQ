# InterviewIQ.AI

InterviewIQ.AI is a full-stack AI-powered interview preparation platform that helps candidates practice realistic **Technical and HR interviews**.

Users can sign in with Google, configure an interview based on their role and experience, optionally upload their resume for AI-powered analysis, receive personalized interview questions, submit answers within time limits, and receive AI-generated performance feedback.

The application also provides interview history, detailed performance reports, and a credit-based system with Razorpay payment integration.

---

## 🚀 Features

### 🔐 User Authentication

- Google authentication using Firebase
- JWT-based authentication
- Secure authentication using HTTP cookies
- User session management
- Logout functionality

### 🤖 AI-Powered Interview Generation

- AI-generated interview questions
- Personalized questions based on:
  - Target role
  - Experience
  - Interview type
  - Resume
  - Projects
  - Skills
- Supports:
  - Technical Interviews
  - HR Interviews
- Generates 5 questions for each interview
- Questions follow an easy → medium → hard difficulty progression

### 📄 Resume Analysis

Users can upload their resume in PDF format.

The application:

1. Uploads the resume.
2. Extracts text from the PDF.
3. Sends the extracted resume information to the AI model.
4. Extracts structured information such as:
   - Role
   - Experience
   - Projects
   - Skills
5. Uses the extracted information to personalize interview questions.

Maximum resume upload size: **5 MB**

### 🎤 Interview Practice

The interview interface provides:

- Real-time interview question flow
- Difficulty-based questions
- Question timers
- Answer submission
- AI-powered answer evaluation
- Performance scoring
- Feedback for each answer

### ⏱️ Question Time Limits

| Question | Difficulty | Time Limit |
|----------|------------|------------|
| 1 | Easy | 60 seconds |
| 2 | Easy | 60 seconds |
| 3 | Medium | 90 seconds |
| 4 | Medium | 90 seconds |
| 5 | Hard | 120 seconds |

### 📊 AI-Powered Answer Evaluation

Candidate answers are evaluated based on:

- Confidence
- Communication
- Correctness

Each category is scored on a scale of **0–10**.

The application also generates feedback for each submitted answer.

### 📈 Interview Reports

After completing an interview, users can view their performance report, including:

- Overall score
- Confidence score
- Communication score
- Correctness score
- Question-wise performance
- AI-generated feedback

### 📚 Interview History

Users can view their previous interviews, including:

- Interview role
- Experience
- Interview mode
- Interview date
- Interview status
- Performance details

### 💳 Credit System

InterviewIQ.AI uses a credit-based system.

- New users receive **100 credits**
- Generating an interview consumes **50 credits**
- Additional credits can be purchased through the pricing section

### 💰 Razorpay Payment Integration

The application integrates Razorpay for purchasing additional interview credits.

Payment flow:

```text
Select Plan
    ↓
Create Razorpay Order
    ↓
Complete Payment
    ↓
Verify Payment Signature
    ↓
Update Payment Status
    ↓
Add Credits to User Account
```

---

# 🛠️ Tech Stack

## Frontend

- React.js
- Vite
- JavaScript
- Tailwind CSS
- React Router
- Redux Toolkit
- Axios
- Firebase
- Motion
- Recharts
- React Icons
- jsPDF
- jsPDF AutoTable
- React Circular Progressbar

## Backend

- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT
- Cookie Parser
- CORS
- Multer
- PDF.js
- Axios
- Razorpay
- OpenRouter API

## Database

- MongoDB

## Authentication

- Firebase Google Authentication
- JSON Web Tokens (JWT)
- HTTP Cookies

## AI

- OpenRouter API
- AI-powered question generation
- AI-powered resume analysis
- AI-powered answer evaluation

## Payment

- Razorpay

---

# 🏗️ System Architecture

InterviewIQ.AI follows a client-server architecture.

```text
                       ┌──────────────────┐
                       │      User        │
                       │    / Browser     │
                       └────────┬─────────┘
                                │
                                ▼
                       ┌──────────────────┐
                       │ React Frontend   │
                       │      Vite        │
                       └────────┬─────────┘
                                │
                              Axios
                                │
                                ▼
                       ┌──────────────────┐
                       │ Express Backend  │
                       │     Node.js      │
                       └────────┬─────────┘
                                │
              ┌─────────────────┼─────────────────┐
              │                 │                 │
              ▼                 ▼                 ▼
       ┌────────────┐    ┌─────────────┐   ┌────────────┐
       │  MongoDB   │    │ OpenRouter  │   │  Razorpay  │
       │  Database  │    │     AI      │   │  Payments  │
       └────────────┘    └─────────────┘   └────────────┘
```

---

# 📁 Project Structure

```text
InterviewIQ/
│
├── client/
│   ├── public/
│   │
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   │   ├── AuthModel.jsx
│   │   │   ├── Footer.jsx
│   │   │   ├── Navbar.jsx
│   │   │   ├── Step1SetUp.jsx
│   │   │   ├── Step2Interview.jsx
│   │   │   ├── Step3Report.jsx
│   │   │   └── Timer.jsx
│   │   │
│   │   ├── pages/
│   │   │   ├── Auth.jsx
│   │   │   ├── Home.jsx
│   │   │   ├── InterviewHistory.jsx
│   │   │   ├── InterviewPage.jsx
│   │   │   ├── InterviewReport.jsx
│   │   │   └── Pricing.jsx
│   │   │
│   │   ├── redux/
│   │   │   ├── store.js
│   │   │   └── userSlice.js
│   │   │
│   │   ├── utils/
│   │   │   └── firebase.js
│   │   │
│   │   ├── App.jsx
│   │   ├── App.css
│   │   ├── index.css
│   │   └── main.jsx
│   │
│   ├── package.json
│   └── vite.config.js
│
├── server/
│   ├── config/
│   │   ├── connectDb.js
│   │   └── token.js
│   │
│   ├── controllers/
│   │   ├── auth.controller.js
│   │   ├── interview.controller.js
│   │   ├── payment.controller.js
│   │   └── user.controller.js
│   │
│   ├── middlewares/
│   │   ├── isAuth.js
│   │   └── multer.js
│   │
│   ├── models/
│   │   ├── interview.model.js
│   │   ├── payment.model.js
│   │   └── user.model.js
│   │
│   ├── routes/
│   │   ├── auth.route.js
│   │   ├── interview.route.js
│   │   ├── payment.route.js
│   │   └── user.route.js
│   │
│   ├── services/
│   │   ├── openRouter.service.js
│   │   └── razorpay.service.js
│   │
│   ├── index.js
│   └── package.json
│
└── README.md
```

---

# 🔄 Application Workflow

## 1. Authentication

The user signs in using Google Authentication.

```text
User
 ↓
Google Authentication
 ↓
Firebase
 ↓
Backend
 ↓
User Created / Existing User Found
 ↓
JWT Generated
 ↓
Authentication Cookie
```

The backend uses the authenticated user information for protected operations.

---

## 2. Interview Setup

The user selects/provides:

- Target role
- Experience
- Interview mode
- Optional resume

Interview modes:

- Technical
- HR

---

## 3. Resume Processing

When a resume is uploaded:

```text
PDF Resume
     ↓
Multer
     ↓
PDF.js
     ↓
Text Extraction
     ↓
OpenRouter AI
     ↓
Structured Resume Information
     ↓
Role / Experience / Projects / Skills
```

The extracted information is used to generate personalized interview questions.

---

## 4. AI Question Generation

The backend sends candidate information to the AI model.

The AI generates **5 interview questions**.

Difficulty progression:

```text
Question 1 → Easy
Question 2 → Easy
Question 3 → Medium
Question 4 → Medium
Question 5 → Hard
```

The generated questions are stored in MongoDB.

Generating an interview consumes **50 credits**.

---

## 5. Answer Submission

For each question, the candidate submits an answer.

The application checks:

- Whether an answer was submitted
- Whether the time limit was exceeded

If the answer is valid, it is sent to the AI evaluator.

---

## 6. Answer Evaluation

The AI evaluates the answer using:

```text
Confidence
Communication
Correctness
```

Each metric is scored from **0 to 10**.

The interview stores the evaluation result along with the candidate's answer and feedback.

---

## 7. Interview Completion

After all five questions are completed, the interview is marked as completed.

The final report contains the candidate's overall performance and question-wise evaluation.

---

# 🔌 API Endpoints

All backend APIs are prefixed with:

```text
/api
```

## Authentication

### Google Authentication

```http
POST /api/auth/google
```

Authenticates a user using Google authentication information.

### Logout

```http
GET /api/auth/logout
```

Logs out the authenticated user.

---

# User

### Get Current User

```http
GET /api/user/current-user
```

Returns the currently authenticated user's information.

**Authentication:** Required

---

# Interview

### Analyze Resume

```http
POST /api/interview/resume
```

Uploads and analyzes a PDF resume.

**Authentication:** Required

**Maximum file size:** 5 MB

---

### Generate Interview Questions

```http
POST /api/interview/generate-questions
```

Generates personalized interview questions using AI.

**Authentication:** Required

Example request:

```json
{
  "role": "Software Developer",
  "experience": "Fresher",
  "mode": "Technical",
  "resumeText": "Resume content",
  "projects": [
    "AI Interview Platform"
  ],
  "skills": [
    "React",
    "Node.js",
    "MongoDB"
  ]
}
```

---

### Submit Answer

```http
POST /api/interview/submit-answer
```

Submits an answer for AI evaluation.

**Authentication:** Required

---

### Finish Interview

```http
POST /api/interview/finish
```

Finishes the interview and calculates the final result.

**Authentication:** Required

---

### Get Interview History

```http
GET /api/interview/get-interview
```

Returns the authenticated user's interview history.

**Authentication:** Required

---

### Get Interview Report

```http
GET /api/interview/report/:id
```

Returns the detailed report for a specific interview.

**Authentication:** Required

---

# Payment

### Create Razorpay Order

```http
POST /api/payment/order
```

Creates a Razorpay order for purchasing credits.

**Authentication:** Required

---

### Verify Payment

```http
POST /api/payment/verify
```

Verifies the Razorpay payment signature and updates the user's credits.

**Authentication:** Required

---

# 🗄️ Database Models

## User

The User collection stores:

- Name
- Email
- Credits
- Created timestamp
- Updated timestamp

Default credits:

```text
100
```

---

## Interview

The Interview collection stores:

- User ID
- Role
- Experience
- Interview mode
- Resume text
- Questions
- Difficulty
- Time limit
- Answers
- Feedback
- Score
- Confidence
- Communication
- Correctness
- Final score
- Interview status
- Created timestamp
- Updated timestamp

---

## Payment

The Payment collection stores:

- User ID
- Plan ID
- Amount
- Credits
- Razorpay order ID
- Razorpay payment ID
- Payment status
- Created timestamp
- Updated timestamp

---

# ⚙️ Installation

## Prerequisites

Before running the project, make sure you have:

- Node.js installed
- npm installed
- MongoDB database
- Firebase project
- OpenRouter API key
- Razorpay account

---

# 📥 Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

Navigate into the project:

```bash
cd InterviewIQ
```

---

# 🎨 Frontend Setup

Navigate to the client directory:

```bash
cd client
```

Install dependencies:

```bash
npm install
```

Create a `.env` file inside the `client` directory.

Example:

```env
VITE_FIREBASE_APIKEY=your_firebase_api_key
VITE_RAZORPAY_KEY_ID=your_razorpay_key_id
```

Start the frontend:

```bash
npm run dev
```

The frontend will normally run at:

```text
http://localhost:5173
```

---

# 🖥️ Backend Setup

Open another terminal.

Navigate to the server directory:

```bash
cd server
```

Install dependencies:

```bash
npm install
```

Create a `.env` file inside the `server` directory.

Example:

```env
PORT=6000

MONGODB_URL=your_mongodb_connection_string

JWT_SECRET=your_jwt_secret

OPENROUTER_API_KEY=your_openrouter_api_key

RAZORPAY_KEY_ID=your_razorpay_key_id

RAZORPAY_KEY_SECRET=your_razorpay_key_secret
```

Start the backend:

```bash
npm run dev
```

The backend will normally run on:

```text
http://localhost:6000
```

---

# 🔑 Environment Variables

## Client

| Variable | Description |
|----------|-------------|
| `VITE_FIREBASE_APIKEY` | Firebase API key |
| `VITE_RAZORPAY_KEY_ID` | Razorpay public key |

## Server

| Variable | Description |
|----------|-------------|
| `PORT` | Backend server port |
| `MONGODB_URL` | MongoDB connection string |
| `JWT_SECRET` | Secret used to generate JWT tokens |
| `OPENROUTER_API_KEY` | OpenRouter API key |
| `RAZORPAY_KEY_ID` | Razorpay key ID |
| `RAZORPAY_KEY_SECRET` | Razorpay secret key |

---

# 🔒 Security

Do not commit sensitive credentials to GitHub.

Keep the following information private:

- MongoDB connection string
- JWT secret
- OpenRouter API key
- Razorpay secret key
- Firebase private credentials

Make sure `.env` files are included in `.gitignore`.

Example:

```gitignore
.env
.env.*
node_modules/
```

---

# 🧪 Running the Project Locally

You need to run both the frontend and backend.

### Terminal 1 — Frontend

```bash
cd client
npm install
npm run dev
```

### Terminal 2 — Backend

```bash
cd server
npm install
npm run dev
```

Then open the frontend URL in your browser.

---

# 📦 Production Build

To create a production build of the frontend:

```bash
cd client
npm run build
```

To preview the production build:

```bash
npm run preview
```

---

# 📌 Important Notes

- Each new user starts with 100 credits.
- Generating an interview consumes 50 credits.
- Resume uploads are limited to 5 MB.
- AI features require a valid OpenRouter API key.
- Google authentication requires Firebase configuration.
- Payment functionality requires Razorpay credentials.
- MongoDB is required for storing users, interviews, and payment records.
- Protected API routes require authentication.
- Never commit `.env` files or secret API keys to GitHub.

---

# 🚀 Future Improvements

Some possible future improvements include:

- AI voice-based interviews
- Speech-to-text answers
- Real-time AI conversation
- Coding interview practice
- Company-specific interview preparation
- More detailed skill-wise analytics
- Personalized learning recommendations
- Advanced resume analysis
- Interview performance comparison
- Additional interview categories
- Email notifications
- Improved security and rate limiting

---

# 👨‍💻 Author

**Sukrity Roy**

Full Stack Developer

---

# 📄 License

This project is developed for educational, learning, and portfolio purposes.
