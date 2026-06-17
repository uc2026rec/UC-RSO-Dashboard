# UC RSO Dashboard — GitHub Pages Deployment Guide

## 📁 Files in This Repo

| File | Purpose |
|------|---------|
| `index.html` | Main dashboard (rename `uc_rso_dashboard_v6.html` → `index.html`) |
| `users.json` | User accounts and roles |
| `README.md` | This guide |

---

## 🚀 Quick Setup (GitHub Pages)

1. **Create a new GitHub repository** (e.g. `uc-rso-dashboard`)
2. Upload both files: `index.html` and `users.json`
3. Go to **Settings → Pages → Branch: main → / (root)** → Save
4. Your dashboard will be live at:
   `https://YOUR_USERNAME.github.io/uc-rso-dashboard/`

> ✅ Works on any WiFi — it's hosted on GitHub's servers, not your local machine.

---

## 👤 Default Login Credentials

| Username | Password | Role |
|----------|----------|------|
| `superadmin` | `admin123` | Superadmin |
| `admin` | `admin123` | Admin |
| `viewer` | `viewer123` | Viewer |

> ⚠️ **Change these passwords immediately after first login!**

---

## 🔐 Role Permissions

| Feature | Superadmin | Admin | Viewer |
|---------|-----------|-------|--------|
| View all data & charts | ✅ | ✅ | ✅ |
| Edit data (tables, KPIs) | ✅ | ✅ | ❌ |
| Export CSV / JSON / HTML | ✅ | ✅ | ❌ |
| Backup & Restore | ✅ | ✅ | ❌ |
| Manage user accounts | ✅ | ❌ | ❌ |
| Export users.json | ✅ | ❌ | ❌ |

---

## ✏️ How to Add / Change Users

### Option A — Edit `users.json` directly on GitHub (easiest)
1. Open your repo on GitHub
2. Click `users.json` → pencil icon (Edit)
3. Add, edit, or remove entries following this format:
```json
{
  "username": "juana",
  "password": "mypassword",
  "role": "admin",
  "name": "Juana dela Cruz"
}
```
4. Click **Commit changes**
5. Done — takes effect immediately on next login attempt

### Option B — Use the in-app User Manager (Superadmin only)
1. Log in as `superadmin`
2. Click **👥 Manage Users** in the sidebar
3. Add/edit/delete users
4. Click **⬇ Export users.json**
5. Commit the downloaded file to your GitHub repo

---

## 🔒 Security Notes

- Passwords are stored in plain text in `users.json` — **suitable for internal/intranet use**
- For public-facing deployments, consider upgrading to Firebase Authentication
- The dashboard uses `sessionStorage` — users are logged out when the browser tab closes
- Each login attempt re-fetches `users.json` from GitHub, so account changes take effect immediately

---

## 🌐 Sharing With Colleagues

Just share your GitHub Pages URL:
```
https://YOUR_USERNAME.github.io/uc-rso-dashboard/
```
Anyone on any WiFi can access it. Give each colleague their own account via `users.json`.

---

## 💾 Saving Data Changes

Data edited in the dashboard (grants, activities, etc.) is **not** automatically saved back to GitHub.
To preserve changes permanently:
1. Use **💾 Backup / Restore → Download Dashboard as HTML**
2. Rename it `index.html`
3. Commit it to GitHub — this bakes the current data into the file

---

*University of the Cordilleras — Research Services Office*
