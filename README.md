HealthVault - Personal Health Record Tracker
A comprehensive, accessible web application designed to help users manage their medical data, track vitals, and maintain personal health records securely. Built with a robust backend architecture, this project features a seamless fallback "mock mode" to ensure uninterrupted development and demonstration even without a live database.

🚀 Features
Secure Authentication: User login and registration with token-based authorization.

Health Dashboard: Real-time overview of vitals including BPM, Blood Pressure, BMI, and Weight.

Record Management: Add, view, and organize various health records (allergies, vitals, treatments, vaccinations, and appointments).

Accessibility First: Built-in toggles for High Contrast Mode, Large Text, and Large Buttons.

Access Control: Mockups for managing data privacy and sharing with healthcare providers or emergency contacts.

Smart Fallback Mode: The Express backend automatically shifts to serving mock data if the MongoDB connection is unavailable, ensuring the UI remains fully functional for testing.

🛠️ Tech Stack
Frontend:

HTML5 & CSS3

Vanilla JavaScript (ES6+)

Bootstrap 5.3 (Responsive UI)

FontAwesome (Icons)

Backend:

Node.js

Express.js

MongoDB & Mongoose

CORS & Body-Parser

⚙️ Prerequisites
Before you begin, ensure you have the following installed:

Node.js (v14 or higher)

MongoDB (Local installation or MongoDB Atlas URI)

📦 Installation & Setup
1. Clone the repository:

Bash
git clone https://github.com/yourusername/HealthVault.git
cd HealthVault
2. Install dependencies:

Bash
npm install express mongoose dotenv body-parser cors
3. Configure Environment Variables:
Create a .env file in the root directory and add the following configuration:

Code snippet
# Optional: Set to your MongoDB connection string. If left blank or connection fails, the app runs in Mock Mode.
MONGO_URI=mongodb://localhost:27017/healthvault

# Port for the Express server
PORT=5000

# Authentication Tokens
API_TOKEN=your_secure_api_token
MOCK_TOKEN=mockToken

# Set to 'true' to force mock mode regardless of DB connection
FORCE_MOCK=false
4. Start the Backend Server:

Bash
node app.js
The server will start on http://localhost:5000. Watch the console output to see if it connected to MongoDB or fell back to Mock Mode.

5. Launch the Frontend:
Open page.html in your preferred web browser to access the Login/Register portal. (You can use a local server like VS Code's Live Server for the best experience).

🗂️ Project Structure
Plaintext
HealthVault/
├── page.html           # Authentication portal (Login/Register)
├── HealthVault.html    # Main application dashboard
├── app.js              # Node.js Express server entry point
├── models/             # Mongoose database schemas
│   ├── User.js
│   ├── HealthRecord.js
│   └── Appointment.js
├── package.json        # Node.js dependencies and scripts
└── .env                # Environment variables (not tracked in git)
📡 API Endpoints Overview
GET /health - Check API status and DB connection mode.

POST /register - Register a new user and initialize health stats.

POST /login - Authenticate an existing user.

GET /me - Retrieve current user's profile and stats.

GET /health-records - Fetch recent medical records.

POST /records - Add a new medical record.

GET /appointments - Retrieve user appointments.

(Mocked Endpoints): /reminders, /categories, /access serve dynamic UI components.
