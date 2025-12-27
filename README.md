# Smart-Library-Management-System

## About Project:-
User-friendly Library Management System in Java with a graphical user interface (GUI) that enables efficient management of books, handling of issue and return transactions, fine tracking, and report generation
<img width="694" height="369" alt="image" src="https://github.com/user-attachments/assets/9d4a6eef-5dc7-4990-bbd1-786e0a43a3f3" />
<img width="692" height="351" alt="image" src="https://github.com/user-attachments/assets/9b9d5723-0f1a-4cda-939f-59f3e6896eba" />
<img width="695" height="361" alt="image" src="https://github.com/user-attachments/assets/89ba93c2-5bd1-410d-af76-47555affc839" />

## Technologies Used:-
Java, Swing, JDBC, Mysql

## Users Of the System:-
**Admin**: Manages librarians, generates reports, monitors system-level data.
**Librarian**: Handles day-to-day operations such as managing books, issuing and returning books, maintaining student records.
**Student**: Interacts with the system to borrow books, return books, and view notifications.

## Functional Modules:-
a.	**Authentication & Role-Based Access**
•	LoginScreen.java – Provides a login interface, verifies credentials using User class and queries via DatabaseConnection.java. On successful login, navigates to respective dashboard based on user role.
•	SignUpScreen.java – Handles student self-registration, inserts new user records into the users table. Uses RoundedPanel and CustomButton for modern UI.
•	User.java – Core class that represents a user object with attributes like ID, name, password, role, and status. Used throughout authentication and user management modules.

b.**Dashboards (Post Login Navigation)**
•	AdminDashboard.java – Interface with access to panels: LibrarianManagementPanel, ReportsPanel, UserApprovalPanel, and SettingsPanel. Uses GradientPanel and RoundedPanel for styling.
•	LibrarianDashboard.java – Central navigation panel for librarians. Grants access to BookManagementPanel, IssueBooksPanel, ReturnBooksPanel, FineManagementPanel, etc.
•	StudentDashboard.java – Student home screen with access to BorrowBooksPanel, ReissueBooksPanel, StatusPanel, and SettingsPanel.

c.**Book Management**
•	Book.java – Plain Old Java Object (POJO) representing each book with fields like bookId, title, author, availability. Contains getters, setters, and constructors.
•	BookManagementPanel.java – UI for librarians to add new books, edit details, delete records. Performs validation, interacts with books table via DatabaseConnection.java.
 
d.**Borrowing & Returning**
•	BorrowBooksPanel.java – Allows students to browse available books and request to borrow. Displays data in JTable, reads from books table, and sends borrowing request.
•	IssueBooksPanel.java – Lets librarians issue books. Handles logic like checking book availability, updating issued_books and books tables, and setting due dates.
•	ReturnBooksPanel.java – Enables book return operations. Checks current date vs. due date, updates books table status, and calls FineManagementPanel to check fines.
•	ReissueBooksPanel.java – Students can request a reissue if eligible. Verifies due date and updates new due date if allowed.
•	IssuedBooksPanel.java – Displays list of currently issued books (filterable by student/user). Useful for tracking and batch returns.

e.**Fines & Reports**
•	FineManagementPanel.java – Calculates overdue fines using current date and due date from issued_books table. Updates fines table and shows total amount.
•	ReportsPanel.java – Used by Admin to view system reports: active users, borrowed books, pending fines, and activity logs. Pulls data from multiple tables.

f.**Student & User Management**
•	StudentRecordsPanel.java – Displays all student data to librarians. Can be searched and sorted by student name, ID, or book activity.
•	UserApprovalPanel.java – Admin interface for enabling/disabling newly registered users or suspended accounts. Aﬀects status field in users table.
•	LibrarianManagementPanel.java – Used by Admin to add, delete, or modify librarian details. Each librarian is a special type of user with role='Librarian'.
 
g.**Notifications & Requests**
•	NotificationPanel.java – Shows important alerts like upcoming due dates, overdue fines, or system maintenance. Triggered at login.
•	RequestBooksPanel.java – Allows students to request new book titles. Stores request into requests table for admin/librarian to review.
•	StatusPanel.java – A student’s personal dashboard showing current borrowed books, history, fines, and reissue status.

h.	**Appearance & Settings**
•	SettingsPanel.java – Oﬀers toggle between dark and light modes using custom Java properties. Also includes password change.
•	CustomButton.java – Defines a stylized JButton with custom colours and fonts for consistency.
•	RoundedPanel.java – A JPanel with rounded edges used across dashboards and panels.
•	GradientPanel.java – Provides a gradient background UI panel.

i.	**Utilities & Helpers**
•	DatabaseConnection.java – Singleton class that manages all SQL operations: inserts, updates, queries, and deletes. Central DB access point.
