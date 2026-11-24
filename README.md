# HR Analytics System

> 🔒 The source code is private. This repository is only a showcase. You can request access to the code or a live demo by messaging me on [LinkedIn](https://www.linkedin.com/in/bassam-alanzi-508b99325).

A secure **Windows desktop application** for HR teams. It brings employee records, performance, attendance and an audit history together in one workspace, with live workforce metrics.

![Setup screen](screenshots/setup-screen.png)

## Highlights
- **Standalone desktop app.** It runs in its own native window (PySide6), with no browser, no Python install and no extra runtimes needed. It ships as a ready-to-run `.exe`.
- **REST API backend** built with FastAPI: authentication, employee CRUD, metrics, audit logs and a health check
- **Security by design:**
  - Passwords hashed with **PBKDF2-SHA256 (600,000 iterations)** and a unique salt, plus a strong password policy
  - Server-side sessions over HTTP-only cookies; the database stores only hashed session tokens
  - Every create, update and delete is written to an **audit log** (who, what, when)
- **Live analytics dashboard** with workforce metrics computed from the database
- Local SQLite database stored in the user's AppData folder, with clear backup guidance
- Automated tests for the API

## Architecture
```
Desktop window (PySide6)  ──►  Local FastAPI server  ──►  SQLite
        │                         │
   HTML/CSS/JS UI            Auth · Sessions · Audit log · Metrics
```

## Tech stack
`Python` · `FastAPI` · `Uvicorn` · `Pydantic` · `SQLite` · `PySide6 (Qt)` · `HTML/CSS/JavaScript` · `PyInstaller` · `pytest`

---

## بالعربي
**HR Analytics System** برنامج سطح مكتب لإدارة الموارد البشرية، يجمع بيانات الموظفين والأداء والحضور في مكان واحد، مع لوحة مؤشرات مباشرة وسجل تدقيق لكل عملية. يعتمد حماية قوية تشمل تجزئة كلمات المرور وإدارة الجلسات من جهة الخادم، ويعمل كبرنامج مستقل دون متصفح ودون الحاجة إلى تثبيت Python.

**الكود المصدري خاص** ويُتاح عند الطلب.

© All rights reserved. No part of this project may be copied or reused without written permission.
