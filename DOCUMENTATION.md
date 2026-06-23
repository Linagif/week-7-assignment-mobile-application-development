# Student Attendance App - Documentation

## 1. Overview
The **Student Attendance App** is a robust Android application developed in **Kotlin** designed to streamline the process of managing student records and tracking daily attendance. It features a localized **SQLite database** for data persistence, ensuring it works completely offline.

## 2. Features
*   **User Authentication**: Secure Login and Signup system using unique User IDs.
*   **Student Management**: Add new students with their names and courses.
*   **Attendance Tracking**: Mark students as 'Present' or 'Absent' for the current date.
*   **Registry & Reports**: 
    *   View a complete registry of all added students.
    *   View detailed attendance history for all records.
*   **Modern UI**: A custom "Brown and White" theme with a centered, dashboard-style interface using Material Design 3.

---

## 3. Technical Architecture
### Language & Frameworks
*   **Kotlin**: Primary programming language.
*   **Android SDK**: Minimum SDK 24 (Android 7.0), Target SDK 36.
*   **Material Components**: For CardViews, Grid Layouts, and standard UI elements.

### Database Schema (SQLite)
The app uses a local database named `StudentAttendance.db` with three primary tables:
1.  **Users Table**: Stores `user_id_internal`, `login_id` (unique), and `password`.
2.  **Students Table**: Stores `student_id`, `name`, and `course`.
3.  **Attendance Table**: Stores `attendance_id`, `student_id_fk` (ForeignKey), `date`, and `status`.

---

## 4. App Structure (Packages)
*   **`com.example.week7assignment_studentattendanceapp`**:
    *   `MainActivity.kt`: The main dashboard after login.
    *   **`data/`**:
        *   `DatabaseHelper.kt`: Manages SQLite operations (CRUD).
        *   `Student.kt` & `Attendance.kt`: Data models.
    *   **`ui/`**:
        *   `LoginActivity.kt` & `SignupActivity.kt`: Auth management.
        *   `AddStudentActivity.kt`: Form for new students.
        *   `MarkAttendanceActivity.kt`: Daily attendance logging.
        *   `ViewStudentsActivity.kt`: RecyclerView for student registry.
        *   `ViewAttendanceActivity.kt`: RecyclerView for attendance history.
    *   **`adapter/`**:
        *   `StudentAdapter.kt` & `AttendanceAdapter.kt`: Binds data to RecyclerViews.

---

## 5. User Guide
### Initial Setup
1.  Launch the app on an Android device.
2.  On the **Login Screen**, click "Sign Up" if it is your first time.
3.  Enter a unique **User ID** and **Password** to create an account.

### Managing Students
1.  From the Dashboard, tap the **Add Student** icon.
2.  Enter the Student's Full Name and Course, then tap **Save Student Record**.
3.  View your list of students anytime by tapping the **View Student List** icon.

### Marking Attendance
1.  Tap the **Mark Attendance** icon.
2.  Select a student from the dropdown menu.
3.  Select the status (**Present** or **Absent**).
4.  Tap **Submit Attendance**.

### Viewing Reports
1.  Tap **View Reports** to see a chronological list of all attendance records, including student names and dates.

---

## 6. Visual Design
*   **Color Palette**:
    *   Primary Background: `#795548` (Brown)
    *   Card Backgrounds: `#5D4037` (Dark Brown)
    *   Text/Icons: `#FFFFFF` (White)
*   **Layout Logic**: Content is centered vertically and horizontally on the main screen, with specialized top-padding (100dp) on form pages to ensure compatibility with modern phone notches and status bars.

---

## 7. Future Enhancements
*   Search and Filter functionality for attendance records.
*   Export reports to PDF or Excel.
*   Syncing local data with a cloud backend (Firebase).
