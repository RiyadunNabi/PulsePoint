<!DOCTYPE html>
<html lang="en">

<body>
  <header>
    <h1>💊 PulsPoint: An Outdoor Patient Management System</h1>
    <p>A database solution for managing outpatient hospital services</p>
  </header>

  <section>
    <h2>🏥 Features Modeled in the Database</h2>
    <ul>
      <li>🔐 User Management – Patients and doctors with unique roles</li>
      <li>📅 Appointment Scheduling – Link doctors and patients via schedules</li>
      <li>💊 Prescription System – Drugs, doses, files, and instructions</li>
      <li>💸 Payments and Reviews – Track bills and patient feedback</li>
      <li>📁 Medical Records – Logs, health files, and diagnostic checks</li>
      <li>📚 Knowledge Hub – Articles written by doctors</li>
      <li>🧠 Symptom Checker – Predict disease using symptoms</li>
    </ul>
  </section>
<!--
  <section>
    <h2>📁 Project Structure</h2>
    <pre>
📂 pulspoint-db/
├── erd/
│   ├── pulspoint-erd.csv
│   ├── PulsPoint_ERD_Presentation.pptx
│   └── pulspoint-erd-diagram.png
├── sql/
│   ├── create_tables.sql
│   ├── insert_sample_data.sql
│   └── queries.sql
├── docs/
│   ├── schema_description.md
│   └── entity_summary.md
└── README.md
    </pre>
  </section>
--
  <section>
    <h2>⚙️ Getting Started</h2>
    <ol>
      <li>Clone the repo: <code>git clone https://github.com/your-username/pulspoint-db.git</code></li>
      <li>Open your SQL DBMS (MySQL, PostgreSQL, etc.)</li>
      <li>Run <code>create_tables.sql</code> to build the schema</li>
      <li>Load <code>insert_sample_data.sql</code> to populate test data</li>
      <li>Run sample queries from <code>queries.sql</code></li>
    </ol>
  </section>
--
  <section>
    <h2>🧾 Sample Query</h2>
    <pre><code>SELECT p.first_name, p.last_name, a.appointment_date, d.first_name AS doctor_name
FROM APPOINTMENT a
JOIN PATIENT p ON a.patient_id = p.patient_id
JOIN SCHEDULE s ON a.schedule_id = s.schedule_id
JOIN DOCTOR d ON s.doctor_id = d.doctor_id;</code></pre>
  </section>
-->
  <section>
    <h2>📐 ERD Preview</h2>
    <p>Find a full ERD in the presentation and visual formats below:</p>
    <ul>
      <li><a href="./ER_Diagram/ER_Diagram.pdf">📎 ERD Presentation (PDF)</a></li>
    </ul>
  </section>

  <section>
    <h2>📘 License</h2>
    <p>This project is developed for educational use. Contributions are welcome.</p>
  </section>

  <section>
    <h2>🙋‍♂️ Author</h2>
    <p><strong>Riyadun Nabi</strong><br />
    <strong>Fardin Fuad</strong><br />
       📧 riyadunnabi@gmail.com<br />
       🎓 BUET (Bangladesh University of Engineering and Technology)</p>
  </section>

  <div class="footer">© 2025 PulsPoint Project — All rights reserved.</div>
</body>
</html>



------------------------------------------------------------------------------------------
Awesome — since you're working on a **Doctor-Patient Management System**, and you need to complete:

✅ **DB Connection** (done)
✅ **Feature Implementation using Basic SQL** (5-day goal)

Here’s the **ideal backend feature flow**, based on your schema and goals:

---

## ✅ Phase 1: Feature Implementation Roadmap (Only Backend)

| Order | Feature                          | Tables Involved                                                  | API Routes Needed                                                 | SQL Ops        |
| ----- | -------------------------------- | ---------------------------------------------------------------- | ----------------------------------------------------------------- | -------------- |
| 1     | Create & fetch departments       | `department`                                                     | `GET`, `POST /departments`                                        | SELECT, INSERT |
| 2     | Create & fetch users             | `user`                                                           | `POST /users`                                                     | INSERT         |
| 3     | Create & fetch doctors           | `doctor`, `user`, `department`                                   | `GET`, `POST /doctors`                                            | SELECT, INSERT |
| 4     | Create & fetch patients          | `patient`, `user`                                                | `GET`, `POST /patients`                                           | SELECT, INSERT |
| 5     | Weekly availability              | `weekly_schedule`                                                | `POST /schedule`, `GET`                                           | SELECT, INSERT |
| 6     | Book appointment                 | `appointment`                                                    | `POST /appointments`                                              | INSERT         |
| 7     | View doctor/patient appointments | `appointment`, `doctor`, `patient`                               | `GET /appointments/doctor/:id`<br>`GET /appointments/patient/:id` | SELECT JOIN    |
| 8     | Add review to appointment        | `reviews`                                                        | `POST /reviews`                                                   | INSERT         |
| 9     | Add prescription to appointment  | `prescription`, `drug`, `prescription_drug`, `prescription_file` | `POST /prescriptions`                                             | INSERT, JOIN   |
| 10    | Upload & fetch health logs/docs  | `health_logs`, `medical_documents`                               | `POST /logs`, `POST /documents`                                   | INSERT, SELECT |

---

## ⏳ Day-wise Plan (suggested for your 5-day deadline)

| Day   | Tasks                                                                  |
| ----- | ---------------------------------------------------------------------- |
| Day 1 | ✅ DB connection <br> ✅ `/api/doctors [GET]` <br> ✅ Insert sample data  |
| Day 2 | `/departments [GET+POST]` <br> `/users [POST]` <br> `/doctors [POST]`  |
| Day 3 | `/patients [POST+GET]` <br> `/weekly_schedule [POST]`                  |
| Day 4 | `/appointments [POST+GET]` <br> `/appointments/doctor/:id`             |
| Day 5 | `/reviews [POST]` <br> `/prescriptions` basics <br> Polish + demo prep |

---

## ✅ Recommendation for Next Step (Start Here):

**Step 1: Add Department**

* `POST /departments` → to add a department
* `GET /departments` → to view all

> Because `doctor` depends on `department_id`, and you need departments first to create doctors easily.

Shall I create `routes/departmentRoutes.js` for you now?
