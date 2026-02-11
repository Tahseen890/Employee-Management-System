# Employee-Management-System
Employee Management System with History Tracking
A production-ready, full-stack MERN application for managing employee records with comprehensive historytracking and audit trails.
Show Image
Show Image
Show Image
Show Image
Show Image
Show Image
🌟 Features
Core Functionality
✅
Complete CRUD Operations
- Create, Read, Update, Delete employee records
✅
Soft Delete
- Employees are marked as deleted, never permanently removed
✅
Auto-generated Employee IDs
- Unique IDs in format: EMP-YYYYMMDD-XXXX
✅
History Tracking
- Every change is recorded with detailed audit trail
✅
Search & Filter
- Search by name, email, ID with department and status filters
✅
Pagination
- Efficient data loading with customizable page sizes
✅
Sorting
- Sort by any column with ascending/descending order
✅
Statistics Dashboard
- Real-time overview of employee data
✅
Responsive Design
- Works seamlessly on desktop, tablet, and mobile
History & Audit Features
📊
Change History
- View all modifications to employee records
🔍
Field-level Tracking
- See exactly what changed (old value → new value)
⏱️
Timeline View
- Visual timeline of all employee changes
📝
Operation Types
- Track CREATE, UPDATE, and DELETE operations
🔗
Version Comparison
- Compare any two versions of employee data
User Experience
🎨
Modern UI
- Clean, professional interface using Bootstrap 5
🚀
Fast & Responsive
- Optimized for performance
✅
Form Validation
- Client-side and server-side validation
🔔
Toast Notifications
- User-friendly feedback messages
⚠️
Confirmation Modals
- Prevent accidental deletions
📱
Mobile Friendly
- Fully responsive across all devices
🛠️
Technology Stack
Backend
Node.js
- JavaScript runtime
Express.js
- Web application framework
MongoDB
- NoSQL database
Mongoose
- MongoDB object modeling (ODM)
express-validator
- Input validation middleware
Frontend
React.js
- UI library with functional components and hooks
React Router
- Client-side routing
Bootstrap 5
- CSS framework for responsive design
Bootstrap Icons
- Icon library
Architecture
MVC Pattern
- Model-View-Controller architecture
REST API
- RESTful API design principles
Async/Await
- Modern asynchronous JavaScript
📋 Prerequisites
Before you begin, ensure you have the following installed:
Node.js
(v14 or higher)
MongoDB
(v4.4 or higher)
npm or yarn (comes with Node.js)
A code editor (VS Code recommended)
🚀 Quick Start
1. Clone or Download the Project
Create the project structure with all files as provided in the artifacts above.
2. Install Backend Dependencies
3. Install Frontend Dependencies
4. Configure Environment Variables
Backend
.env
:
bash
cdcd
backend
npmnpm
installinstall
express mongoose dotenv cors express-validator
npmnpm
installinstall
--save-dev nodemon
bash
cdcd
frontend
npmnpm
installinstall
react-router-dom bootstrap bootstrap-icons
env
Frontend
.env
:
5. Start MongoDB
6. Start the Backend Server
Server will run on
http://localhost:5000
7. Start the Frontend Application
Application will open at
http://localhost:3000
📁 Project Structure
PORT=5000PORT=5000
NODE_developmentNODE_ENV=development
MONGODB_managementMONGODB_URI=mongodb://localhost:27017/employee_management
CLIENT_3000CLIENT_URL=http://localhost:3000
env
REACT_apiREACT_APP_API_URL=http://localhost:5000/api
bash
# Windows# Windows
net MongoDBnet start MongoDB
# Homebrew)# macOS (Homebrew)
brew communitybrew services start mongodb-community
# Linux# Linux
sudosudo
systemctl start mongod
bash
cdcd
backend
npmnpm
run dev
bash
cdcd
frontend
npmnpm
start
employee-management-system/
├── backend/
│ ├── config/
│ │ └── database.js # MongoDB connection
│ ├── controllers/
│ │ ├── employeeController.js # Employee business logic
│ │ └── historyController.js # History business logic
│ ├── middleware/
│ │ ├── errorHandler.js # Error handling
│ │ └── validator.js # Input validation
│ ├── models/
│ │ ├── Employee.js # Employee schema
│ │ └── EmployeeHistory.js # History schema
│ ├── routes/
│ │ ├── employeeRoutes.js # Employee endpoints
│ │ └── historyRoutes.js # History endpoints
│ ├── .env # Environment variables
│ ├── package.json # Dependencies
│ └── server.js # Entry point
│
└── frontend/
├── public/
│ └── index.html # HTML template
├── src/
│ ├── components/
│ │ ├── DeleteModal.js # Delete confirmation
│ │ ├── EmployeeForm.js # Employee form
│ │ ├── EmployeeTable.js # Employee table
│ │ ├── HistoryTimeline.js # History display
│ │ ├── Navbar.js # Navigation bar
│ │ └── Toast.js # Notifications
│ ├── pages/
│ │ ├── AddEmployee.js # Add employee page
│ │ ├── Dashboard.js # Dashboard page
│ │ ├── EditEmployee.js # Edit employee page
│ │ ├── EmployeeHistory.js # History page
│ │ └── EmployeeList.js # Employee list page
│ ├── services/
│ │ ├── api.js # API configuration
│ │ └── employeeService.js # API methods
│ ├── styles/
│ │ └── custom.css # Custom styles
│ ├── App.js # Main component
│ └── index.js # Entry point
├── .env # Environment variables
└── package.json # Dependencies
🔌 API Endpoints
Employee Operations
Method
Endpoint
Description
POST
/api/employees
Create new employee
GET
/api/employees
Get all employees (with filters)
GET
/api/employees/:id
Get employee by ID
PUT
/api/employees/:id
Update employee
DELETE
/api/employees/:id
Soft delete employee
GET
/api/employees/stats/overview
Get statistics
History Operations
Method
Endpoint
Description
GET
/api/employees/:id/history
Get employee history
GET
/api/employees/:id/history/compare
Compare versions
GET
/api/history/:historyId
Get specific record
📖
Detailed API Documentation:
See
API_DOCUMENTATION.md
💾 Database Schema
Employee Collection
javascript
EmployeeHistory Collection
🎯 Usage Examples
Creating an Employee
1.
Navigate to "Add Employee" page
2.
Fill in all required fields
3.
Click "Create Employee"
4.
View confirmation and automatic redirect to employee list
{{
employeeIdemployeeId
::
StringString
,,
// 0001// Auto-generated: EMP-20240115-0001
fullNamefullName
::
StringString
,,
// chars// Required, 2-100 chars
emailemail
::
StringString
,,
// email// Required, unique, valid email
phoneNumberphoneNumber
::
StringString
,,
// format// Required, unique, valid format
departmentdepartment
::
StringString
,,
// values// Required, predefined values
designationdesignation
::
StringString
,,
// chars// Required, max 100 chars
salarysalary
::
NumberNumber
,,
// 0// Required, >= 0
employmentStatusemploymentStatus
::
StringString
,,
// Inactive// Active | Inactive
dateOfJoiningdateOfJoining
::
DateDate
,,
// Required// Required
isDeletedisDeleted
::
BooleanBoolean
,,
// flag// Soft delete flag
deletedAtdeletedAt
::
DateDate
,,
// timestamp// Deletion timestamp
createdAtcreatedAt
::
DateDate
,,
// generated// Auto-generated
updatedAtupdatedAt
::
DateDate
// updated// Auto-updated
}}
javascript
{{
employeeIdemployeeId
::
ObjectIdObjectId
,,
// Employee// Reference to Employee
employeeRefIdemployeeRefId
::
StringString
,,
// string// Employee ID string
operationoperation
::
StringString
,,
// DELETE// CREATE | UPDATE | DELETE
changeschanges
::
[[
{{
// changes// Array of changes
fieldfield
::
StringString
,,
oldValueoldValue
::
MixedMixed
,,
newValuenewValue
::
MixedMixed
}}
]]
,,
snapshotsnapshot
::
ObjectObject
,,
// snapshot// Complete record snapshot
changedBychangedBy
::
StringString
,,
// identifier// User identifier
changeReasonchangeReason
::
StringString
,,
// description// Change description
createdAtcreatedAt
::
DateDate
// generated// Auto-generated
}}
Viewing History
1.
Go to employee list
2.
Click the history icon for any employee
3.
View complete timeline of changes
4.
See field-level changes with old → new values
Searching and Filtering
1.
Use the search bar to find employees by name, email, or ID
2.
Filter by department or employment status
3.
Sort by clicking column headers
4.
Navigate through pages using pagination
🔒 Data Validation
Frontend Validation
Real-time form validation
User-friendly error messages
Prevention of invalid submissions
Backend Validation
Input sanitization
Type checking
Business rule enforcement
Unique constraint validation
🐛 Common Issues & Solutions
MongoDB Connection Error
Port Already in Use
bash
# running# Check if MongoDB is running
mongod versionmongod --version
# service# Start MongoDB service
sudosudo
systemctl start mongod
CORS Error
Verify
CLIENT_URL
in backend
.env
Check CORS configuration in
server.js
📖
Detailed Troubleshooting:
See
SETUP_GUIDE.md
🧪 Testing
Manual Testing
1.
Create Employee:
Add multiple employees with different departments
2.
Read Operations:
View employee list, search, and filter
3.
Update Employee:
Edit employee details and verify history
4.
Delete Employee:
Soft delete and confirm status change
5.
History View:
Check complete audit trail
Sample Test Data
📈 Future Enhancements
User authentication and authorization (JWT)
Role-based access control (Admin, Manager, HR)
Advanced analytics and reporting
bash
# process# Find and kill process
lsoflsof
-i :5000
# Linux# macOS/Linux
netstatnetstat
-ano
||
findstr :5000
# Windows# Windows
json
{{
"fullName""fullName"
::
"Smith""Jane Smith"
,,
"email""email"
::
"com""jane.smith@example.com"
,,
"phoneNumber""phoneNumber"
::
"4567""555-123-4567"
,,
"department""department"
::
"Marketing""Marketing"
,,
"designation""designation"
::
"Manager""Marketing Manager"
,,
"salary""salary"
::
7500075000
,,
"employmentStatus""employmentStatus"
::
"Active""Active"
,,
"dateOfJoining""dateOfJoining"
::
"20""2024-01-20"
}}
Export to Excel/PDF
Email notifications
File upload (profile pictures, documents)
Department management
Leave management
Payroll integration
Performance reviews
Bulk operations
🤝 Contributing
Contributions are welcome! To contribute:
1.
Fork the repository
2.
Create a feature branch
3.
Make your changes
4.
Write/update tests
5.
Submit a pull request
📄 License
This project is open-source and available under the MIT License.
👨‍💻 Developer
Built with ❤️ using the MERN Stack
📞 Support
For issues and questions:
Review the
Setup Guide
Check
API Documentation
Open an issue on GitHub
🌟 Acknowledgments
MongoDB for the excellent database
Express.js team for the web framework
React.js team for the UI library
Bootstrap team for the CSS framework
Note:
This is a development version. For production deployment, implement proper security measuresincluding authentication, authorization, HTTPS, rate limiting, and environment-specific configurations.
