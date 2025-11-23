# AI-Powered Fraud Detection System

This repository contains a **Java (Servlet) + MySQL + HTML/CSS** project implementing a simple real-time fraud detection prototype.
It demonstrates core Java/OOP concepts, JDBC DB access, servlets, multithreading, DAO patterns, and a minimal frontend UI.

---

## Project structure (single folder ready for VS Code)
```
AI-Fraud-Detection-System/
  backend/    # Maven webapp (Java servlets)
  frontend/   # Static HTML/CSS/JS (served by web container or static server)
  database/   # schema.sql to create DB and seed data
```

> **Screenshots used in the presentation** are included under `frontend/assets/` for reference:
- /mnt/data/Screenshot 2025-11-23 012212.png
- /mnt/data/Screenshot 2025-11-23 012237.png
- /mnt/data/Screenshot 2025-11-23 012258.png

(These are local paths to the images you provided — when you upload to GitHub the images are already included.)

---

## Requirements (what to install)
- Java 11 or newer
- Maven
- MySQL server
- VS Code extensions (recommended):
  - **Extension Pack for Java** (Microsoft)
  - **Language Support for Java(TM) by Red Hat**
  - **Debugger for Java**
  - **Tomcat for Java** (if you want to run in Tomcat)
  - **MySQL** extension (optional)
  - **VS Code Java Pack Installer**

Also download the **MySQL Connector/J** JAR (Maven dependency is included in `pom.xml`).

---

## Setup & Run (development using Jetty plugin)
1. Import the folder into VS Code.
2. Create the database and seed data:
   - Open MySQL client and run `database/schema.sql` (or use Workbench).
3. Edit `backend/src/main/resources/database.properties` and set `db.user` and `db.password`.
4. In terminal, go to `backend/` directory and run:
```bash
mvn clean package
mvn jetty:run
```
5. Open `http://localhost:8080/` to view the frontend pages (index.html).

Alternatively, build WAR and deploy to Tomcat: `mvn clean package` -> copy `target/ai-fraud-detection.war` to Tomcat `webapps` folder.

---

## What is implemented (rubric mapping)
- **OOP:** model classes, services, interfaces (clear separation), inheritance and encapsulation.
- **Collections & Generics:** DAO returns lists, usage of generics for collections.
- **Multithreading:** `RealTimeMonitorThread` periodically calls fraud detection.
- **Database Classes:** `DBConnection`, `TransactionDAO`, `UserDAO`.
- **JDBC:** PreparedStatements, transactions, connection pooling (basic).
- **Servlets & Web Integration:** `AuthServlet`, `TransactionServlet`, `AdminServlet`.
- **Problem Understanding & Solution Design:** Simple anomaly detection heuristic (mock ML).

---

## Notes
- The ML detector is a placeholder to demonstrate integration. Replace with a real model or ML service for production.
- Passwords are stored in plain text for demonstration only; use hashing in real projects.
- The frontend is minimal and meant to illustrate interaction with servlets.

---

## How to submit / GitHub
1. Initialize git, add files, commit.
2. Push to GitHub.
3. Include screenshots and README in repository root.

---
.
