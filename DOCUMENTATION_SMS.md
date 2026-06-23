# Student Management System - Documentation

## 1. Overview
The **Student Management System** is a Java-based Android application developed to manage student records and consume external data via APIs. This system follows the **MVC (Model-View-Controller)** architecture and uses **SQLite** for local storage and **Retrofit** for networking.

## 2. Features Implemented

### 2.1 Authentication (Auth Module)
*   **Activities**: `LoginActivity` & `SignupActivity`
*   **Fields**: User ID and Password.
*   **Validation**: Prevents empty submissions, validates password match on signup, and checks database for existing accounts.
*   **Navigation**: 
    *   Signup → Login
    *   Login → Dashboard

### 2.2 Dashboard Module
*   **Activity**: `DashboardActivity`
*   **Components**: Uses a Grid layout with CardViews for navigation.
*   **Destinations**: Student Registration, View Students, API Users, and Reports.

### 2.3 Student Registration (CRUD)
*   **Activity**: `RegistrationActivity`
*   **Functionality**:
    *   **Create**: Add new students with ID, Name, Email, Course, and Phone.
    *   **Read/Update**: Load existing student data for modification.
    *   **Delete**: Remove student records.
    *   **Clear**: Reset form fields.
*   **Validation**: Checks for empty fields and valid email formats using regex.

### 2.4 API Integration (Networking)
*   **Activity**: `ApiUsersActivity`
*   **Tools**: Retrofit 2 + Gson.
*   **Endpoint**: `https://jsonplaceholder.typicode.com/users`
*   **Display**: Uses a RecyclerView to show user names, emails, phones, and company names fetched from the web.
*   **Error Handling**: Manages API failures and connection issues with Toast messages.

### 2.5 Local Database
*   **Class**: `DatabaseHelper` (Java)
*   **Schema**:
    *   Table: `students`
    *   Columns: `id` (PK), `studentId`, `fullName`, `email`, `course`, `phone`.

### 2.6 Reporting
*   **Activity**: `ReportsActivity`
*   **Metrics**:
    *   Total number of registered students.
    *   Distribution of students per course (dynamic listing).

---

## 3. Architecture & Code Quality
*   **MVC Pattern**: Separated logic into `models`, `activities`, `adapters`, `database`, and `network` packages.
*   **UI/UX**: Consistent brown and white theme applied across all screens with centered layouts and Material Design components.
*   **Responsiveness**: Uses `ScrollView` for forms and `ConstraintLayout`/`LinearLayout` weights for adaptive scaling.

---

## 4. Testing Procedures
1.  **Login Test**: Verify "admin/admin" works and empty fields are rejected.
2.  **Registration Test**: Add a student and verify they appear in "View Students".
3.  **Update/Delete Test**: Click a student in the list, modify their details, and verify persistence.
4.  **API Test**: Open "API Users" and verify data loads from the internet (requires connection).
5.  **Reports Test**: Verify "Total Students" count matches the database.
