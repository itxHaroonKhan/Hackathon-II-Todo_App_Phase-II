# Hackathon-II-Todo_App_Phase-II

A full-stack Todo application built with Next.js (frontend) and FastAPI (backend) with authentication and task management features.

## 🚀 Live Demo
Frontend Preview: https://frontend-gcohfcq16-haroon-khans-projects-5c7a0028.vercel.app

## 🛠️ Tech Stack

- **Frontend**: Next.js 14 (App Router), React, TypeScript, Tailwind CSS
- **Backend**: FastAPI, Python 3.8+
- **Database**: PostgreSQL with SQLModel ORM
- **Authentication**: JWT-based authentication
- **Deployment**: Vercel (Frontend), Self-hosted (Backend)

## 📋 Features

- User authentication (signup/login)
- Secure JWT-based authentication system
- Task management (create, read, update, delete)
- Responsive UI design
- Modern, clean interface
- API endpoints for all operations

## 🚀 Quick Start

### Prerequisites

- Node.js (v18 or higher)
- Python 3.8 or higher
- PostgreSQL database
- Git

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables:
   ```bash
   cp .env.local .env
   ```

   Update the `.env` file with your backend API URL:
   ```env
   NEXT_PUBLIC_API_BASE_URL=http://localhost:8000
   ```

4. Run the development server:
   ```bash
   npm run dev
   ```

   The frontend will be available at http://localhost:3000

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up environment variables:
   Create a `.env` file in the backend directory:
   ```env
   DATABASE_URL=postgresql://username:password@localhost:5432/todo_app
   BETTER_AUTH_SECRET=your-super-secret-auth-key-here-make-it-long-and-random
   CORS_ORIGINS=http://localhost:3000,http://localhost:3001
   DEBUG=false
   ```

4. Run the server:
   ```bash
   cd src
   uvicorn main:app --reload --host 0.0.0.0 --port 8000
   ```

   The backend API will be available at http://localhost:8000

## 🔧 Available Scripts

### Frontend

In the `frontend` directory, you can run:

- `npm run dev` - Starts the development server
- `npm run build` - Builds the app for production
- `npm run start` - Runs the built app in production mode

### Backend

In the `backend` directory:

- `uvicorn src.main:app --reload --host 0.0.0.0 --port 8000` - Run development server
- `python -m pytest tests/ -v` - Run tests

## 📁 Project Structure

```
Hackathon-II-Todo_App_Phase-II/
├── frontend/                 # Next.js frontend application
│   ├── app/                  # App router pages
│   ├── components/           # Reusable UI components
│   ├── lib/                  # Utility functions
│   ├── public/               # Static assets
│   └── types/                # Type definitions
├── backend/                  # FastAPI backend application
│   ├── src/
│   │   ├── api/              # API route definitions
│   │   ├── database/         # Database connection and initialization
│   │   ├── models/           # Data models
│   │   ├── services/         # Business logic
│   │   ├── config.py         # Configuration settings
│   │   └── main.py           # Main application entry point
│   ├── tests/                # Test files
│   └── requirements.txt      # Dependencies
├── specs/                    # Project specifications
├── history/                  # Prompt history records
└── README.md                 # This file
```

## 🔐 Authentication System

The application implements JWT-based authentication:

- User registration and login
- Protected routes that require authentication
- Automatic token refresh
- Secure password hashing

## 🗄️ Database Schema

The application uses SQLModel with the following main entities:

- **User**: Stores user information (email, hashed password, etc.)
- **Task**: Stores task information (title, description, status, owner)

## 🧪 Testing

### Frontend Testing
Frontend tests are set up using Jest and React Testing Library.

### Backend Testing
Backend tests are implemented with pytest:

```bash
cd backend
cd src
python -m pytest ../tests/ -v
```

## 🚀 Deployment

### Frontend Deployment
The frontend is deployed on Vercel. To deploy your own version:
1. Push your code to a GitHub repository
2. Connect the repository to Vercel
3. Set the build command to `npm run build`
4. Set the output directory to `out`

### Backend Deployment
The backend can be deployed on platforms like Heroku, AWS, or Google Cloud. Make sure to configure environment variables appropriately.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🐛 Known Issues

- SQLModel relationship compatibility: Fixed by removing `cascade_delete=True` parameter from Relationship definitions due to version compatibility issues.

## 📞 Support

If you encounter any issues, please check the troubleshooting sections in the individual README files for frontend and backend, or open an issue in the repository.