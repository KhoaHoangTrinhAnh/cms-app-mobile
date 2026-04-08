<h1 align="center">📱 CMS App Mobile</h1>

<p align="center">
  A <strong>Content Management System (CMS) mobile application</strong> for marketing teams to plan, create, assign, review, and publish content — all from a single Android app.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" />
  <img src="https://img.shields.io/badge/Language-Java-007396?style=for-the-badge&logo=java&logoColor=white" />
  <img src="https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black" />
  <img src="https://img.shields.io/badge/Android%20Studio-3DDC84?style=for-the-badge&logo=androidstudio&logoColor=white" />
</p>

<p align="center">
  <a href="https://drive.google.com/file/d/1E7YrxOpQyeGBwvzNHvtGofGYt6cWa5tC/view">🎬 Watch Demo Video</a> &nbsp;|&nbsp;
  <a href="https://drive.google.com/drive/folders/1pNr4SgXOErCcDA0ngsamJ0_cfIBlRqiH">📄 Full Report & Materials</a>
</p>

---

## 📖 Description

**CMS App Mobile** is an Android-based content management platform designed for marketing teams. It provides a complete workflow for content production — from creation and task assignment to review, approval scheduling, and publishing — with real-time data synchronization powered by Firebase.

**Target users:** Marketing managers (Admins) and content creators/editors (Creators) who need to collaborate on content production via mobile devices.

---

## 🎬 Demo

▶️ [Watch the Demo Video on Google Drive](https://drive.google.com/file/d/1E7YrxOpQyeGBwvzNHvtGofGYt6cWa5tC/view)

---

## ✨ Features

### 🔐 Authentication
- Email/password sign-in via Firebase Authentication
- Forgot password & password reset flow
- Change password from profile settings
- Role-based access control: **Admin** and **Creator** roles

### 🏠 Dashboard (Home)
- Personalized overview of assigned content, approved posts, and rejected posts
- Admins see an additional "Pending Approval" queue
- Quick navigation to all major sections via bottom navigation bar

### 📋 Content Management
- Create, edit, and delete content items with fields: Title, Type, Channel, Tag, URL, Editor Link, Assignees
- Attach sub-tasks to content with deadlines and completion tracking
- Filter content list by status and search by keyword
- Content status lifecycle: **To Do → In Progress → Done → Approved / Rejected → Published**

### 📅 Content Calendar
- Visual calendar view showing scheduled content by publication date
- Tap on a date to see a popup list of content items for that day

### ✅ Review & Approval (Admin)
- Dedicated review queue where Admins can approve or reject submitted content
- Reject with a written reason sent back to the creator
- Approve and schedule a publication date/time

### 📅 Schedule Post
- Schedule approved content for a specific publish date and time

### 🔔 Notifications
- In-app notification list for content status updates (approved, rejected, assigned, etc.)
- Notification detail view with full message context

### 📊 Reports & Analytics
- Bar chart: Published vs. In-Progress content count, grouped by month
- Horizontal bar chart: Top 5 most productive users by published content count
- Date range filter (from / to date) using a date picker
- Data table (RecyclerView) showing per-channel monthly breakdown

### 👤 User Profile
- View and edit full name, phone number
- Profile info displayed across the app
- Edit profile screen with save functionality

### 👥 User Management (Admin)
- View all registered users with name, email, phone, and role
- Add new users via a dialog
- Edit or delete existing users

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Language** | Java |
| **UI / Layout** | XML Layouts, View Binding |
| **UI Components** | Material Design 3 (`com.google.android.material:material:1.11.0`) |
| **Charts** | MPAndroidChart v3.1.0 (`BarChart`, `HorizontalBarChart`) |
| **Lists** | `RecyclerView` 1.3.2 |
| **Authentication** | Firebase Authentication 23.0.0 |
| **Realtime Database** | Firebase Realtime Database 21.0.0 |
| **Cloud Database** | Firebase Firestore 25.1.1 |
| **IDE** | Android Studio |
| **Min SDK** | Android 10 (API 29) |
| **Target SDK** | Android 16 (API 36) |
| **Build System** | Gradle with Kotlin DSL (`.kts`) |

---

## 📁 Project Structure

```
cms-app-mobile/
├── app/
│   ├── src/
│   │   └── main/
│   │       ├── java/com/example/nt118_marketingapp/
│   │       │   ├── model/                      # Data models
│   │       │   │   ├── Content.java            # Content item model
│   │       │   │   ├── SubTask.java            # Sub-task model
│   │       │   │   ├── User.java               # User model
│   │       │   │   ├── Notification.java       # Notification model
│   │       │   │   └── Approval.java           # Approval record model
│   │       │   ├── adapters/                   # RecyclerView adapters
│   │       │   │   ├── UserAdapter.java
│   │       │   │   └── DemoAdapter.java
│   │       │   ├── firebase/
│   │       │   │   └── firebase_dataset.json   # Sample Firebase data structure
│   │       │   ├── utils/
│   │       │   │   └── IdGenerator.java        # Custom ID generation utility
│   │       │   │
│   │       │   ├── SignInActivity.java          # Login screen (launcher)
│   │       │   ├── ForgotPasswordActivity.java # Forgot password entry
│   │       │   ├── ForgotPasswordCre.java      # Password reset confirmation
│   │       │   ├── NewPassword.java            # Set new password
│   │       │   ├── ChangePassWordCre.java      # Change password (authenticated)
│   │       │   │
│   │       │   ├── MainActivity.java           # Entry point / router
│   │       │   ├── DashboardActivity.java      # Home dashboard
│   │       │   ├── ContentListActivity.java    # Content list with filters
│   │       │   ├── ContentManageActivity.java  # Create/edit content & subtasks
│   │       │   ├── ContentCalendarActivity.java# Calendar view of content
│   │       │   ├── ReviewContentActivity.java  # Admin content review queue
│   │       │   ├── SchedulePostActivity.java   # Schedule content for publishing
│   │       │   ├── NotificationActivity.java   # Notification list
│   │       │   ├── NotificationDetailActivity.java # Notification detail
│   │       │   ├── ReportActivity.java         # Analytics & charts
│   │       │   ├── UsermanagerActivity.java    # Admin user management
│   │       │   ├── Profile.java               # View user profile
│   │       │   ├── EditProfile.java            # Edit profile info
│   │       │   │
│   │       │   ├── Post.java                   # Post display model (dashboard)
│   │       │   ├── PostAdapter.java            # Adapter for dashboard post list
│   │       │   ├── ReportAdapter.java          # Adapter for report table
│   │       │   ├── ReportItem.java             # Report row data model
│   │       │   ├── ContentCalendarRepository.java # Firebase data layer for calendar
│   │       │   ├── ContentCalendarPopupAdapter.java # Calendar popup list adapter
│   │       │   ├── AddEditUserDialog.java      # Dialog for add/edit user
│   │       │   └── ConfirmDeleteDialog.java    # Reusable confirm-delete dialog
│   │       │
│   │       ├── res/
│   │       │   ├── layout/                     # XML layout files (37 files)
│   │       │   ├── drawable/                   # Icons and shapes
│   │       │   ├── menu/                       # Bottom navigation menu
│   │       │   ├── anim/                       # Transition animations
│   │       │   └── values/                     # Strings, colors, themes
│   │       │
│   │       └── AndroidManifest.xml
│   │
│   ├── build.gradle.kts                        # App-level build config & dependencies
│   └── google-services.json                    # Firebase project configuration
│
├── build.gradle.kts                            # Project-level build config
├── settings.gradle.kts
└── gradle.properties
```

---

## ⚙️ Installation & Setup

### Prerequisites

- **Android Studio** Hedgehog (2023.1.1) or later
- **JDK 11** (bundled with Android Studio)
- **Android device or emulator** running Android 10 (API 29) or higher
- A **Firebase project** (see Firebase setup below)

### Steps

1. **Clone the repository**

   ```bash
   git clone https://github.com/KhoaHoangtrinhAnh/cms-app-mobile.git
   cd cms-app-mobile
   ```

2. **Open in Android Studio**

   - Launch Android Studio
   - Select **File → Open** and choose the `cms-app-mobile` folder

3. **Firebase Setup** *(assumed — use the existing `google-services.json` or create your own)*

   - Go to the [Firebase Console](https://console.firebase.google.com/)
   - Create a new project (or use an existing one)
   - Register an Android app with the package name: `com.example.nt118_marketingapp`
   - Download the `google-services.json` file and place it at `app/google-services.json`
   - Enable **Firebase Authentication** (Email/Password provider)
   - Enable **Firebase Realtime Database** and import the sample data from `app/src/main/java/com/example/nt118_marketingapp/firebase/firebase_dataset.json`
   - Enable **Firebase Firestore** (used for additional data)

4. **Sync & Build**

   - Click **Sync Project with Gradle Files** in Android Studio
   - Wait for all dependencies to download

5. **Run the App**

   - Connect a physical device or start an emulator (Android API 29+)
   - Click the **Run ▶** button or press `Shift + F10`

---

## 🚀 Usage

### User Flow

```
Launch App
    └── Sign In (email + password)
            ├── Forgot Password? → Enter email → Check inbox → Set new password
            │
            └── Dashboard (Home)
                    ├── [All] View assigned, approved, rejected content cards
                    ├── [Admin] View "Pending Approval" queue
                    │
                    ├── Content Management (bottom nav)
                    │       ├── Browse content list (filter by status/search)
                    │       ├── Create new content (title, type, channel, tag, URL)
                    │       ├── Assign sub-tasks with deadlines to team members
                    │       └── Edit / delete content
                    │
                    ├── Calendar (bottom nav)
                    │       └── View content scheduled by publish date
                    │
                    ├── Review (Admin only, bottom nav)
                    │       ├── See all "Done" content awaiting approval
                    │       ├── Approve → Schedule publish date/time
                    │       └── Reject → Enter rejection reason (sent as notification)
                    │
                    ├── User Management (Admin only, bottom nav)
                    │       ├── View all users
                    │       ├── Add / Edit / Delete users
                    │
                    ├── Notifications (bottom nav)
                    │       └── View all system notifications with detail view
                    │
                    ├── Profile (bottom nav)
                    │       ├── View user info (name, email, phone, role)
                    │       ├── Edit profile
                    │       └── Change password
                    │
                    └── Reports (accessible from Dashboard)
                            ├── Bar chart: Published vs In-Progress by month
                            ├── Horizontal bar chart: Top 5 productive users
                            └── Filter by date range
```

### Roles

| Role | Capabilities |
|---|---|
| **Admin** | Full access: manage users, review & approve content, view all reports, access all navigation tabs |
| **Creator** | Create & manage own content, view personal dashboard (assigned/approved/rejected), notifications, profile |

---

## 🖼️ Screenshots

> *Screenshots are not yet embedded in this README. To add them:*
> 1. Place screenshot images in a `screenshots/` folder at the project root.
> 2. Reference them using: `![Screen Name](screenshots/filename.png)`

Suggested screens to capture:
- Sign In screen
- Dashboard (Admin view)
- Content List with filters
- Content Create/Edit form
- Content Calendar
- Review & Approval screen
- Report charts
- User Management

---

## 👥 Team Members

This project was developed as part of the course **NT118.Q11 — Mobile Application Development** at the **University of Information Technology (UIT), VNU-HCM**.

**Team 14**

| Name | GitHub |
|---|---|
| Kiều Oanh | [@KieuOanhUIT](https://github.com/KieuOanhUIT) |
| Diễm Quyên | [@saramwon1103](https://github.com/saramwon1103) |
| Anh Khoa | [@KhoaHoangtrinhAnh](https://github.com/KhoaHoangtrinhAnh) |
| Tiến Thành | [@Nang-Tien-Thanh](https://github.com/Nang-Tien-Thanh) |

---

## 📚 Documentation & Resources

| Resource | Link |
|---|---|
| 🎬 Demo Video | [Google Drive](https://drive.google.com/file/d/1E7YrxOpQyeGBwvzNHvtGofGYt6cWa5tC/view) |
| 📁 Full Report & Materials | [Google Drive Folder](https://drive.google.com/drive/folders/1pNr4SgXOErCcDA0ngsamJ0_cfIBlRqiH) |
| 📖 Course | NT118.Q11 — Mobile Application Development |
| 🏫 University | University of Information Technology (UIT), VNU-HCM |

---

## 📬 Contact

For questions or collaboration, reach out via email:

📧 [khoahoangtrinhanh@gmail.com](mailto:khoahoangtrinhanh@gmail.com)

---

<p align="center">Made with ❤️ by Team 14 — UIT NT118.Q11</p>
