QuizPlatform
A modern, interactive quiz platform built with Next.js (frontend) and Node.js (backend), designed for creating, sharing, and analyzing quizzes. Perfect for educators, trainers, and marketers looking to engage their audience with powerful analytics and a seamless user experience.
Features

User Authentication: Secure signup with email verification using OTP (One-Time Password).
Quiz Creation: Intuitive interface to create quizzes with customizable questions and answers.
Real-time Analytics: Track participant responses and performance with detailed insights.
Shareable Quizzes: Generate links to share quizzes anywhere or embed them on websites.
Responsive Design: Fully responsive UI that works on desktops, tablets, and mobile devices.
Secure & Reliable: Enterprise-grade security with Clerk integration for authentication and Supabase for database management.

Project Structure
The project is split into two main directories:

frontend/ (Next.js app)
backend/ (Node.js server)

Getting Started
Prerequisites

Node.js (v18 or higher)
npm, Yarn, or pnpm (package manager of your choice)
Clerk account for authentication (for frontend)
Supabase account for database (for backend)
SendGrid account for email sending (for backend)

Frontend Setup

Navigate to the frontend directory:
cd frontend


Install dependencies:
npm install

Or:
yarn install

Or:
pnpm install


Set up environment variables:Create a .env.local file in the frontend/ directory:
NEXT_PUBLIC_Backend_URL=http://localhost:5000


NEXT_PUBLIC_Backend_URL should point to your backend (update to production URL when deploying).


Run the frontend development server:
npm run dev

Or:
yarn dev

Or:
pnpm dev

Open http://localhost:3000 in your browser to see the frontend.


Backend Setup

Navigate to the backend directory:
cd backend


Install dependencies:
npm install

Or:
yarn install

Or:
pnpm install


Set up environment variables:Create a .env file in the backend/ directory:
SUPABASE_URL=https://your-supabase-project-url.supabase.co
SUPABASE_ANON_KEY=your-supabase-anon-key
SUPABASE_SERVICE_KEY=your-supabase-service-key
SENDGRID_USER=your-sendgrid-username
SENDGRID_PASS=your-sendgrid-password
EMAIL_FROM=noreply@yourdomain.com
PORT=5000
JWT_SECRET=your-secure-jwt-secret
APP_URL=http://localhost:3000


Replace Supabase, SendGrid, and JWT values with your actual credentials.
APP_URL should point to your frontend URL (update to production URL when deploying).


Set up Supabase database:

Create a users table in your Supabase project with the following schema:CREATE TABLE users (
  id UUID DEFAULT uuid_generate_v4() PRIMARY KEY,
  first_name TEXT NOT NULL,
  last_name TEXT NOT NULL,
  email TEXT NOT NULL UNIQUE,
  phone TEXT NOT NULL,
  password TEXT NOT NULL,
  role TEXT NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);


Enable Row Level Security (RLS) if needed and set appropriate policies.


Run the backend server:
npm run dev

Or:
yarn dev

Or:
pnpm dev

The backend will run on http://localhost:5000.


Building for Production
Frontend
cd frontend
npm run build
npm run start

Backend
cd backend
npm run build
npm run start

Folder Structure
Frontend
frontend/
├── app/                    # Next.js app directory (App Router)
│   ├── page.js             # Homepage component
│   └── ...                 # Other pages/routes
├── components/             # Reusable React components
│   ├── signup/             # Signup-related components
│   │   ├── SignupForm.jsx  # Main signup form component
│   │   └── ...             # Other signup components
│   ├── ui/                 # UI components (Button, Card, etc.)
│   ├── Footer.jsx          # Footer component
│   └── ...                 # Other components
├── public/                 # Static assets
├── .env.local              # Environment variables (ignored in git)
├── .gitignore              # Git ignore file
├── next.config.js          # Next.js configuration
├── package.json            # Dependencies and scripts
└── README.md               # Project documentation

Backend
backend/
├── src/
│   ├── routes/
│   │   └── auth.js        # Authentication routes
│   ├── utils/
│   │   ├── email.js       # SendGrid email utility
│   │   └── jwt.js         # JWT utility
│   ├── index.js           # Main server file
│   └── .env               # Environment variables (ignored in git)
├── package.json           # Dependencies and scripts
└── README.md              # Backend documentation

Technologies Used
Frontend

Framework: Next.js (App Router), React
Styling: Tailwind CSS
Authentication: Clerk
State Management: React hooks (useState, useRouter)
Icons: Lucide React
Notifications: React Hot Toast
Build Tools: TypeScript, ESLint

Backend

Framework: Node.js, Express
Database: Supabase (PostgreSQL)
Email Service: SendGrid
Authentication: JWT (JSON Web Tokens)
Password Hashing: bcryptjs
Environment Management: dotenv
Development Tools: Nodemon

Usage

Sign Up:

Navigate to the signup page (e.g., /signup).
Enter your first name, last name, email, password, and agree to the terms.
Verify your email using the OTP sent to your inbox.



Create a Quiz:

After signing up, navigate to the dashboard (/dashboard).
Use the quiz builder to create questions, set correct answers, and customize settings.


Share and Analyze:

Share the quiz link with participants.
View real-time analytics on the dashboard, including participant responses and performance metrics.



Contributing
We welcome contributions! To contribute:

Fork the repository.
Create a new branch (git checkout -b feature/your-feature).
Make your changes and commit them (git commit -m "Add your feature").
Push to the branch (git push origin feature/your-feature).
Open a Pull Request with a detailed description of your changes.

Please ensure your code follows the project's ESLint rules and passes all tests before submitting a PR.
License
This project is licensed under the MIT License. See the LICENSE file for details.
Contact
For questions or support, please reach out to your-vishnuwitty@gmail.com.

Built with ❤️ by vishnu
