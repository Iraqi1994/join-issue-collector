# Join — Kanban Task Management Application

Join is a modern, responsive Kanban-based task and project management web application. It enables users to organize tasks across configurable workflow stages, assign team members, manage contacts, track subtasks, and monitor project deadlines in real time.

---

## 🌟 Key Features

- **🔐 User Authentication & Guest Access**
  - Secure sign-up and login with input validation and error feedback.
  - Password visibility toggle.
  - Instant **Guest Login** mode for quick access without account registration.

- **📊 Interactive Dashboard Summary**
  - Real-time task statistics: _To Do_, _In Progress_, _Await Feedback_, _Done_, and total task counts.
  - Urgent priority task tracker with automated nearest deadline calculation.
  - Personalized time-based greetings for logged-in users and guests.

- **📋 Kanban Board**
  - Visual column workflow: **Triage** (backlog, where new tasks land), **To do**, **In progress**, **Await feedback**, and **Done**.
  - **Drag and Drop**: Drag tasks across workflow columns to update status instantly.
  - **Live Search**: Filter tasks dynamically by title or description.
  - **Task Overlay & Detail View**: View task categories, assigned team members, subtask progress bars, and priority levels.
  - Interactive subtask progress toggling, task editing, and deletion.

- **➕ Task Creation & Editing**
  - Detailed task creation interface (available on board overlay or standalone page).
  - Configurable attributes: Title, description, due date (with past-date validation), priority selection (_Urgent_, _Medium_, _Low_), task category (_Technical Task_, _User Story_), and assigned contacts.
  - Dynamic subtasks list with inline add, edit, and delete functionality.

- **📇 Contact Management**
  - Alphabetically indexed contact directory.
  - Custom color badge generation for user initials.
  - Full CRUD operations: Add new contacts, view contact details, edit information, or remove contacts.

- **📱 Fully Responsive Design**
  - Mobile-first adaptive layout supporting mobile devices, tablets, and desktop displays.
  - Custom mobile navigation header and floating task action buttons.

- **📄 Legal & Help Documentation**
  - Built-in Legal Notice, Privacy Policy, and user help guide pages.

---

## 🛠️ Tech Stack & Architecture

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Backend & Database**: Firebase Realtime Database (REST API)
- **State & Caching**: LocalStorage for session state and offline fallbacks
- **Templating**: Dynamic HTML component inclusion using custom client-side templating (`includeHTML`)
- **Documentation**: JSDoc configuration (`jsdoc.json`)

---

## 📁 Project Structure

```text
join-own/
├── assets/                  # Graphics, icons, and custom fonts
│   ├── fonts/               # Inter font files
│   ├── icon/                # Application SVG/PNG icons
│   └── imgs/                # UI images and background assets
├── htmlTemplates/           # Reusable HTML UI components
│   ├── accountNav.html      # Account dropdown overlay
│   ├── boardTaskPopUp.html  # Task detail and edit popup modal
│   ├── header.html          # Application top navigation header
│   └── navigation.html      # Side navigation sidebar
├── pages/                   # Standalone page views
│   ├── addTask.html         # Add task page
│   ├── board.html           # Kanban board page
│   ├── contacts.html        # Contacts directory page
│   ├── help.html            # Help and usage instructions
│   ├── legalNotice.html     # Internal legal notice
│   ├── legalNoticeExtern.html # External legal notice
│   ├── privacyPolicy.html   # Internal privacy policy
│   ├── privacyPolicyExtern.html # External privacy policy
│   └── summary.html         # Main dashboard summary
├── scripts/                 # Application logic modules
│   ├── addTask.js           # Add task page handlers and interaction
│   ├── addTaskSetData.js    # Add task payload creation & submit
│   ├── board.js             # Board page initialization & logic
│   ├── boardDragAndDrop.js  # HTML5 drag-and-drop implementation
│   ├── boardRender.js       # Kanban board card & column rendering
│   ├── contacts.js          # Contact list rendering & interactions
│   ├── contactsApiCalls.js  # Contact REST API sync with Firebase
│   ├── editTemplates.js     # Task edit templates and form bindings
│   ├── loginSignUp.js       # Auth form validation & guest login
│   ├── summary.js           # Dashboard metrics & greeting logic
│   └── template.js          # HTML template loading utilities
├── styles/                  # Modular CSS stylesheets
│   ├── accountNav.css
│   ├── addTask.css
│   ├── addTaskBoard.css
│   ├── board.css
│   ├── boardTaskPopUp.css
│   ├── contacts.css
│   ├── fonts.css
│   ├── header.css
│   ├── help.css
│   ├── legalNotice.css
│   ├── loginSignUp.css
│   ├── navigation.css
│   ├── privacyPolicy.css
│   ├── responsivness.css
│   └── summary.css
├── index.html               # Authentication landing page (Login/Sign Up)
├── script.js                # Core global functions, Firebase URLs & init
├── styles.css               # Base global styling rules
├── jsdoc.json               # JSDoc generator configuration
└── up.bat                   # Git commit/push helper script
```

---

## 🚀 Getting Started

### Prerequisites

No build tools or Node.js runtime are required to run the application. Any standard web browser and local web server (such as Live Server extension for VS Code or `python -m http.server`) are sufficient.

### Installation & Local Setup

1. **Clone the repository**:

   ```bash
   git clone https://github.com/Iraqi1994/join.git
   cd join
   ```

2. **Run with a Local Server**:
   - **VS Code Live Server**: Open the project folder in VS Code, right-click `index.html`, and select **Open with Live Server**.
   - **Python HTTP Server**:
     ```bash
     python -m http.server 8000
     ```
     Then open `http://localhost:8000` in your web browser.

3. **Firebase Database Setup (Optional)**:
   The application is pre-configured with a default Firebase Realtime Database endpoint in `script.js`:
   ```javascript
   const BASE_URL = "https://join-3193b-default-rtdb.europe-west1.firebasedatabase.app/";
   ```
   To connect your own database instance, update the `BASE_URL` variables in `script.js` and `scripts/contactsApiCalls.js`.

---

## 📚 Generating Documentation

To build JSDoc documentation for the JavaScript codebase:

1. Ensure JSDoc is installed globally or locally:
   ```bash
   npm install -g jsdoc
   ```
2. Run JSDoc generation:
   ```bash
   jsdoc -c jsdoc.json
   ```
3. Open `./out/index.html` in your browser to view the generated API documentation.
