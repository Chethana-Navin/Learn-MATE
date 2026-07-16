# Learn Mate

Learn Mate is a Spring Boot-based educational management system for schools and universities. It combines role-based access control, secure authentication, and structured academic workflows so administrators, teachers, students, and parents each see only what they are allowed to use.

## What This Project Does

Learn Mate supports day-to-day academic and administrative operations in one application. It covers user management, class and subject administration, timetables, attendance, exams, marks, fees, notifications, and document uploads.

## Technology Stack

- Spring Boot 3.5.0
- Spring Security 6
- Spring Data JPA
- Thymeleaf
- MySQL
- Java 22

## Key Features

### Role-Based Access Control

- Standardized roles: `ADMIN`, `TEACHER`, `STUDENT`, and `PARENT`
- Role-aware navigation and action buttons
- Page-level restrictions for sensitive routes
- Controller-level authorization for protected operations

### Academic Management

- User and role management
- Subject management
- Class management
- Timetable management
- Attendance tracking
- Exam management
- Marks management
- Student result viewing

### Parent and Student Experience

- View personal profile data
- View timetable information
- View marks and results
- View attendance records
- View notifications
- Parent access to child-related fees and attendance data

### Administrative Tools

- Manage users, subjects, and classes
- Generate reports
- Manage fees
- Control system-wide access to operational pages

### File and Document Handling

- Uploaded answer sheets
- Exam files
- Study materials
- Payment slips
- Notification-related assets

## Security Highlights

The project includes a focused security refactor with the following protections:

- Spring Security 6 integration
- BCrypt password hashing
- URL-based access control
- Method-level authorization with `@PreAuthorize`
- Role-based rendering with Thymeleaf Security extras
- Consistent use of `hasRole()` checks
- Protected menus and action buttons in the UI
- Ownership-aware access checks for personal data
- Simplified role model with only four supported roles

## Access Summary

| Feature | ADMIN | TEACHER | STUDENT | PARENT |
|---|---:|---:|---:|---:|
| Users Management | Yes | No | No | No |
| Subjects Management | Yes | No | No | No |
| Classes Management | Yes | No | No | No |
| Timetables | Yes | Yes | Yes | No |
| Attendances | Yes | Yes | Yes | Yes |
| Exams | Yes | Yes | Yes | Yes |
| Marks | Yes | Yes | Yes | Yes |
| Fees | Yes | No | No | Yes |
| Reports | Yes | No | No | No |
| Profile Access | Yes | Yes | Yes | Yes |

## Repository Documentation

Additional project notes are included in the repository root:

- [HOW_TO_RUN.md](HOW_TO_RUN.md)
- [ROLE_BASED_UI_FIXES.md](ROLE_BASED_UI_FIXES.md)
- [SECURITY_REFACTORING_SUMMARY.md](SECURITY_REFACTORING_SUMMARY.md)
- [test-fee-functionality.html](test-fee-functionality.html)

## Project Structure

- `src/main/java` - application source code
- `src/main/resources/templates` - Thymeleaf pages
- `src/main/resources/static` - styles and static assets
- `uploads` - runtime file storage

## Requirements

- Java 22 or later
- Maven 3.9+ for command-line builds
- MySQL database

## Configuration

Runtime configuration lives in `src/main/resources/application.properties`. Typical settings include database connection properties, Hibernate behavior, and upload paths.

## Run the Application

See [HOW_TO_RUN.md](HOW_TO_RUN.md) for detailed instructions.


## Notes

- The role-based UI prevents users from seeing actions they are not allowed to perform.
- Security protections are applied in both the backend and the templates.
- The `uploads` folder is used at runtime for generated or user-submitted files.
