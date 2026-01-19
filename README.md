

## ✅ GITHUB STRUCTURE

```text
hadoop-lab/
│
├── README.md
├── hadoop-installation-steps.json
└── screenshots/   (optional)
```

* `README.md` → Human-readable guide
* `hadoop-installation-steps.json` → Machine-structured steps (copy source)

---

## ✅ OPTION 1 (BEST PRACTICE) — Reference JSON from README

### `README.md` (paste this)

````md
# Hadoop Installation – Windows 10 (WSL)

This repository provides a **step-by-step Hadoop installation guide**
for **Windows 10 lab systems using WSL (Ubuntu)**.

## 📁 Files in this Repository

- **`hadoop-installation-steps.json`**
  - Contains all steps in structured JSON format
  - Each step clearly separates:
    - Instructions (plain text)
    - Commands (copy-paste ready)

Students should **open this file** and follow steps sequentially.

---

## 🚀 Quick Start

### Step 1 — Enable WSL (Windows)

Open **PowerShell as Administrator** and run:

```powershell
wsl --install
````

Restart if prompted.

---

### Step 2 — Install Ubuntu

```powershell
wsl --install -d Ubuntu-20.04
```

Create Linux username and password.

---

## 📌 Full Step-by-Step Guide

➡️ Open **`hadoop-installation-steps.json`**
➡️ Follow steps in order
➡️ Copy only values under `"commands"`

---

## 🌐 Hadoop Web UI

* HDFS: [http://localhost:9870](http://localhost:9870)
* YARN: [http://localhost:8088](http://localhost:8088)

---

## ⚠️ Notes for Students

* Hadoop installation is **one-time only**
* After restart, run:

```bash
start-dfs.sh
start-yarn.sh
```

---

## 🎓 For Lab / Seminar

This setup runs Hadoop in **single-node pseudo-distributed mode**,
suitable for:

* Academic labs
* Experiments
* Demonstrations

````

This is **clean, readable, and professional**.

---

## ❌ WHAT NOT TO DO

Do **not** do this:

```md
{ "step": 1, "title": "Enable WSL", ... }
````

It becomes unreadable and confusing for students.

---


