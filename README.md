# 🎫 Queue Management System (QMS)

> A comprehensive digital queue management solution designed to eliminate long wait times and streamline service delivery for organizations of any size.

![Status](https://img.shields.io/badge/status-active-success)
![License](https://img.shields.io/badge/license-MIT-blue)
![Version](https://img.shields.io/badge/version-1.0.0-orange)

## 📖 Overview

QMS transforms traditional physical queuing into a modern, transparent, and efficient digital experience. The system serves three primary user groups — customers, service providers, and administrators — each with a purpose-built interface, connected through a central queue management server.

## ✨ Key Features

### For Customers
- 📱 Responsive web portal accessible on any device (mobile & desktop)
- 🖥️ On-site self-service kiosk for walk-in customers
- 🎯 Mandatory service triage for accurate queue routing
- 🎟️ Instant digital token generation via SMS/Email
- 📅 Flexible booking (immediate queue or scheduled appointment)
- 📊 Optimized scheduling with low-wait window suggestions
- ⚠️ Proactive "Today is Impossible" alerts to prevent wasted trips
- ⏱️ Dynamic real-time Estimated Time Remaining (ETR)
- 📍 Dedicated token status page with full transparency
- ⏳ Grace period for late arrivals with automatic token expiry
- 🗺️ Office/desk mapping for visual navigation guidance
- ♿ Priority verification for seniors and PWD (Aadhaar/ID based)
- 🤖 AI-powered query assistance for common questions
- 📷 Multiple check-in options (QR code, kiosk, manual entry, receptionist)

### For Service Providers
- 🔐 Secure, personalized login with skill-based queue views
- ▶️ One-click "Call Next Customer" with automatic service timer
- 📋 Active token view with complete customer details
- ⚖️ Automatic load balancing across available officers
- ✅ Check-in integration (only checked-in appointments appear)
- 🔄 Seamless service transfer between desks/officers
- 📅 In-service rescheduling for follow-up appointments
- 🚦 Transaction closure options (Completed/Cancelled/Escalated)
- 🚨 Emergency alert button for manager assistance
- ❌ No-show management to maintain queue flow

### For Administrators
- 👥 Complete user creation and account management
- 🚫 Instant user deactivation/suspension
- 🔑 Granular role and permission definition
- 🛠️ Officer skill-set definition and modification
- 📋 Service master data management (add/edit/archive)
- ⏰ System operating hours configuration
- 📜 Comprehensive, time-stamped audit logging
- 💾 Scheduled data backup and recovery management

### System-Wide Features
- 📺 Public display screen with real-time token updates
- 🔔 Proactive notifications (ETR changes, grace period, "You Are Next", queue transfers, restructuring alerts, reschedule confirmations)
- 📝 Post-service feedback collection system
- 🌐 Multi-language support (English, Hindi, Gujarati, Spanish)

## 🏗️ System Architecture

The system follows a three-tier architecture:

- **Client-Side (User Interfaces)**: Customer Web Portal, On-Site Kiosk, Service Provider Dashboard, Admin Control Panel
- **Server-Side (Backend)**: Web Server, Application Server, Database
- **External Services**: SMS/Email Gateway, AI Query System, Public Display Screen Controller

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | HTML5, Tailwind CSS, JavaScript, React/Vue |
| Backend | Node.js / Express.js |
| Database | MySQL / PostgreSQL |
| Real-time | WebSocket / Socket.io |
| Notifications | Twilio (SMS), SendGrid (Email) |
| AI Assistant | Dialogflow / OpenAI API |

## 📂 Project Structure

```
queue-management-system/
│
├── frontend/                     # Frontend application
│   ├── public/                   # Public assets
│   │   ├── index.html            # Main HTML file
│   │   └── favicon.ico           # Favicon
│   │
│   ├── src/                      # Source files
│   │   ├── components/           # React/Vue components
│   │   ├── pages/                # Page components
│   │   ├── services/             # API service calls
│   │   ├── App.js                # Main application file
│   │   ├── index.js              # Entry point
│   │   └── styles/               # CSS/SCSS files
│   │
│   ├── package.json              # Frontend dependencies
│   └── .env                      # Environment variables for frontend
│
├── backend/                      # Backend application
│   ├── src/                      # Source files
│   │   ├── controllers/          # Request handlers
│   │   ├── models/               # Database models
│   │   ├── routes/               # API routes
│   │   ├── middleware/           # Middleware functions
│   │   ├── config/               # Configuration files
│   │   ├── app.js                # Main application file
│   │   └── server.js             # Server setup
│   │
│   ├── package.json              # Backend dependencies
│   └── .env                      # Environment variables for backend
│
├── database/                     # Database setup
│   ├── migrations/               # Database migration files
│   ├── seeds/                    # Seed data files
│   └── db_config.sql             # Database configuration and setup script
│
├── README.md                     # Project documentation
└── .gitignore                    # Git ignore file
```

### Description of Each Component

**1. frontend/**
This directory contains all the files related to the frontend of the application.
- **public/**: Contains static files that are served directly.
- **src/**: Contains the source code for the frontend application.
  - **components/**: Reusable UI components.
  - **pages/**: Different pages of the application (Customer Portal, Admin Dashboard, Officer Dashboard).
  - **services/**: Functions to handle API calls to the backend.
  - **App.js**: Main application component.
  - **index.js**: Entry point for the React/Vue application.
  - **styles/**: CSS or SCSS files for styling the application.

**2. backend/**
This directory contains all the files related to the backend of the application.
- **src/**: Contains the source code for the backend application.
  - **controllers/**: Functions that handle incoming requests and return responses.
  - **models/**: Database models that define the structure of the data.
  - **routes/**: API routes that define the endpoints for the application.
  - **middleware/**: Functions that process requests before they reach the route handlers.
  - **config/**: Configuration files for the application (e.g., database connection).
  - **app.js**: Main application file where the Express app is configured.
  - **server.js**: File that starts the server.

**3. database/**
This directory contains files related to the database setup.
- **migrations/**: Files that define how to create or modify database tables.
- **seeds/**: Files that populate the database with initial data.
- **db_config.sql**: SQL script to set up the database schema and initial data.

**4. README.md**
A markdown file that provides an overview of the project, how to set it up, and how to use it.

**5. .gitignore**
A file that specifies which files and directories should be ignored by Git.

## 🚀 Getting Started

### Prerequisites
- Node.js v16 or higher
- MySQL / PostgreSQL
- npm or yarn package manager

### Setting Up the Database

Create a MySQL database for your Queue Management System using the following SQL commands:

```sql
CREATE DATABASE queue_management;

USE queue_management;

CREATE TABLE queues (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE tickets (
    id INT AUTO_INCREMENT PRIMARY KEY,
    queue_id INT NOT NULL,
    ticket_number INT NOT NULL,
    status ENUM('waiting', 'served') DEFAULT 'waiting',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (queue_id) REFERENCES queues(id)
);
```

### Setting Up the Backend

Use Node.js and Express for the backend. Install the necessary packages:

```bash
cd backend
npm init -y
npm install express mysql2 dotenv
```

Create a `config/db.js` file to handle the database connection.

### Setting Up the Frontend

Use Create React App or Vue CLI to set up the frontend:

```bash
npx create-react-app frontend
# or for Vue
vue create frontend
```

### Installation (Full Setup)

```bash
# Clone the repository
git clone https://github.com/yourusername/queue-management-system.git

# Navigate to project directory
cd queue-management-system

# Install backend dependencies
cd backend
npm install

# Set up environment variables
cp .env.example .env
# Edit .env with your configuration

# Run database migrations
npm run migrate

# Start the backend server
npm start
```

```bash
# In a new terminal, set up frontend
cd frontend
npm install
npm start
```

## 📊 User Roles

| Role | Access Level | Key Permissions |
|------|--------------|------------------|
| Manager/Admin | Full | System config, user management, backups, complete overview |
| Service Provider | Limited | Customer service, queue handling, service transfer |
| Waiting Customer | Public | Token generation, status tracking |
| Scheduled Customer | Public | Appointment booking, check-in |
| Priority Customer | Public (elevated) | Precedence in queue (seniors/PWD) |
| Overdue Customer | Public (flagged) | Missed appointment handling |

## 🎯 Roadmap

- [ ] Mobile app (iOS/Android)
- [ ] Multi-branch support
- [ ] Advanced analytics dashboard
- [ ] Voice-based queue announcements
- [ ] Integration with third-party CRMs

## 🤝 Contributing

Contributions are welcome. Please read the contribution guidelines before submitting a pull request.

1. Fork the repository
2. Create a descriptive branch name (e.g., `feature/sms-integration`, `fix/token-expiry-bug`)
3. Make your changes with clear, atomic commits
4. Write or update tests as needed
5. Submit a pull request with a clear description of changes

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 📧 Contact

For questions or support, reach out at support@qms.com

## 🙏 Conclusion

This structure provides a clear separation of concerns, making it easier to manage and scale the application. You can further enhance this structure by adding testing directories, documentation, and other features as needed.
