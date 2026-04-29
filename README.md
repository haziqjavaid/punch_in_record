# Punch In Records

Smart Vision-Based AI Attendance System

## Overview

Punch In Records is a web-based face recognition attendance system that allows educators to register students, start attendance sessions, automatically mark attendance using browser camera feeds, and generate reports. Built with Node.js, Express, and face-api.js for real-time face detection and matching.

## Features

- **Student Registration**: Capture and store face descriptors for student identification
- **Session Management**: Create and manage attendance sessions by class
- **Automatic Attendance**: Real-time face recognition during live sessions
- **Reports & Analytics**: View attendance statistics and export CSV reports
- **Responsive UI**: Clean, modern interface that works on desktop and mobile

## Tech Stack

- **Backend**: Node.js, Express, NeDB (embedded database)
- **Frontend**: HTML, CSS, JavaScript, face-api.js
- **Deployment**: Render (free tier)

## Quick Start

### Prerequisites

- Node.js 16+ installed locally (for development)
- Modern web browser with camera access

### Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/haziqjavaid/Attendance.git
   cd face-attendance
   ```

2. Install backend dependencies:
   ```bash
   cd backend
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

4. Open your browser to `http://localhost:3000`

### Production Deployment

The app is deployed on Render at: https://punch-in-records.onrender.com

## Full Demonstration

Follow this step-by-step guide to see the complete functionality of Punch In Records.

### 1. Access the Application

Navigate to the deployed app: [https://punch-in-records.onrender.com](https://punch-in-records.onrender.com)

You'll see the dashboard with current statistics.

### 2. Register Students

1. Click "Register Students" from the navigation or visit `/register.html`
2. Allow camera access when prompted
3. Enter student details:
   - Name: e.g., "John Doe"
   - Roll Number: e.g., "CS001"
   - Class: e.g., "Computer Science 101"
4. Click "Capture Face" to take a photo and generate face descriptors
5. Click "Register Student" to save

Repeat for multiple students. The system stores face data for recognition.

### 3. Start an Attendance Session

1. Click "Live Session" from the navigation or visit `/session.html`
2. Select a class from the dropdown (populated from registered students)
3. Click "Start Session" to begin
4. The camera will activate for real-time face detection

### 4. Mark Attendance Automatically

During the live session:

1. Students appear in front of the camera
2. The system detects faces and matches them against registered students
3. When a match is found (confidence > 0.6), attendance is marked automatically
4. A success toast appears: "Attendance marked for [Student Name]"
5. The attendance table updates in real-time

### 5. End the Session

1. Click "End Session" when finished
2. The session closes and attendance data is finalized

### 6. View Reports

1. Click "Reports" from the navigation or visit `/reports.html`
2. Filter by session, class, or date
3. View attendance statistics and detailed records
4. Export data to CSV for external analysis

### 7. Dashboard Overview

Return to the main dashboard (`/`) to see:

- Today's attendance statistics
- Recent activity feed
- Quick access to all features

## API Endpoints

The backend provides RESTful APIs:

- `GET /api/health` - Health check
- `GET /api/stats` - Dashboard statistics
- `GET/POST/DELETE /api/students` - Student management
- `GET/POST/PUT /api/sessions` - Session management
- `GET/POST /api/attendance` - Attendance marking
- `GET /api/reports` - Report generation

## Troubleshooting

### Camera Not Working

- Ensure HTTPS (required for camera access)
- Grant camera permissions in browser
- Try refreshing the page

### Face Recognition Issues

- Ensure good lighting and clear face visibility
- Register students with multiple angles if needed
- Check browser console for face-api.js errors

### Deployment Issues

- Render builds from `backend/` directory
- Uses `npm install` and `npm start`
- Environment variable `NODE_ENV=production` set

### Local Development Issues

- Run `npm install` in `backend/` directory
- Use `npm run dev` for nodemon auto-restart
- Frontend served statically from `backend/server.js`

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make changes and test locally
4. Submit a pull request

## License

MIT License - feel free to use and modify for educational purposes.