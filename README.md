# Student Utility App — Android Campus Application for ENSA Fez

A native **Android** application that centralises student services in one secure app: schedules, grades, official PDF documents and profile, with dedicated dashboards for **students, teachers and administrators**.

> Academic mini-project — Android Mobile Development module, ENSA Fez (GSCSI), January 2026.

![Android](https://img.shields.io/badge/Android-Java-3DDC84) ![SQLite](https://img.shields.io/badge/SQLite-local%20DB-003B57) ![Android Studio](https://img.shields.io/badge/Android%20Studio-IDE-green)

<img src="images/login-screen.png" alt="Login screen" width="260"/>

---

## The problem

At ENSA Fez, information is scattered across several platforms, mobile access is difficult, administrative procedures are slow and student requests are not tracked centrally.

| Problem | Solution in the app |
|---|---|
| Scattered information | One app, one login for every service |
| Poor mobile access | 100 % mobile interface |
| Slow sign-up procedures | Requests submitted in under 30 seconds, validated by the administration |
| No request tracking | Real-time status: pending, approved, refused |

## Features by role

| Role | Features |
|---|---|
| **Student** | Schedule, grades, official documents (PDF), profile |
| **Teacher** | Grade entry and consultation, schedule, student declarations |
| **Administrator** | Review pending sign-ups, approve or refuse accounts, supervise profiles |

## Security

- Sign-up restricted to **institutional e-mail addresses** (`@ensaf.ac.ma`).
- **Password strength** validation.
- **Hashed passwords** stored in the local SQLite database.
- **Admin approval workflow:** only approved accounts can log in; pending and refused accounts get explicit messages.
- **Role-based access:** each role only sees its own dashboard.
- PDFs opened securely through **FileProvider**, with offline access to downloaded documents.

## Architecture

```
MainActivity (login) ──► role check ──┬─► StudentDashboardActivity
RegisterActivity (sign-up, pending)   ├─► TeacherDashboardActivity
                                      └─► AdminDashboardActivity
Fragments: ScheduleFragment · DocumentsFragment · ProfileFragment · StudentGradesFragment · TeacherGradesFragment
Navigation: BottomNavigationView        Data: DBHelper (SQLite)        Files: FileProvider
```

## Tech stack

Java · Android Studio · SQLite (DBHelper) · Activities & Fragments · BottomNavigationView · custom list adapter · FileProvider · Android Studio Database Inspector

---

**Author:** Khaoula Belhaj — final-year engineering student, Communicating Systems & Computer Security, ENSA Fez · [LinkedIn](https://linkedin.com/in/khaoula-belhaj-1999163a6)
