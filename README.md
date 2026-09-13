# Smart Attendance System — Web Step 2

This build is based on the supplied Python Smart Attendance System source.

## Step 2 goals
- Full-screen Python-style **Letter Flow** welcome animation: `WELCOME` + `SMART ATTENDENCE SYSTEM`.
- Welcome animation goes directly into the login/app flow with no long artificial splash delay.
- Admin / Teacher password login.
- Viewer login without a password.
- Server-side role checks using Neon PostgreSQL.
- Admin-only registered-student delete, timetable editing, holiday add/delete, audit/admin actions.
- Admin + Teacher attendance, temporary OUT/IN and notifications.
- Holiday/Sunday attendance blocking and automatic lecture final OUT.
- Admin + Teacher own-password change in Settings.
- Advanced Features Center and reports.

## Vercel structure

```
index.html
style.css
script.js
package.json
vercel.json
.env.example
README.md
api/index.js
db/schema.sql
```

## Demo accounts when the database has no users yet
- Admin: `admin` / `admin123`
- Teacher: `teacher` / `teacher123`
- Viewer: `viewer` / no password

For production, set `DATABASE_URL`, `AUTH_SECRET`, `ADMIN_PASSWORD`, and `TEACHER_PASSWORD` in Vercel. Never publish secret values in GitHub or chat.

### Important web-platform difference
The desktop Python version uses OpenCV Haar Cascade + LBPH. A normal browser cannot execute that desktop OpenCV/LBPH pipeline directly, so the web build uses browser-compatible face descriptors while keeping the same registration/recognition attendance workflow.
