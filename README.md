<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>PulsPoint - Outdoor Patient Management System</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0 1rem;
      background-color: #f9f9f9;
      color: #333;
    }
    header {
      background-color: #0066cc;
      color: white;
      padding: 1rem;
      text-align: center;
    }
    section {
      margin: 2rem 0;
    }
    h1, h2, h3 {
      color: #0066cc;
    }
    code {
      background: #eee;
      padding: 2px 4px;
      border-radius: 4px;
    }
    pre {
      background: #eee;
      padding: 1rem;
      overflow-x: auto;
    }
    ul {
      padding-left: 1.2rem;
    }
    .footer {
      text-align: center;
      font-size: 0.9rem;
      color: #777;
      margin: 4rem 0 2rem;
    }
  </style>
</head>
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

  <section>
    <h2>🧾 Sample Query</h2>
    <pre><code>SELECT p.first_name, p.last_name, a.appointment_date, d.first_name AS doctor_name
FROM APPOINTMENT a
JOIN PATIENT p ON a.patient_id = p.patient_id
JOIN SCHEDULE s ON a.schedule_id = s.schedule_id
JOIN DOCTOR d ON s.doctor_id = d.doctor_id;</code></pre>
  </section>

  <section>
    <h2>📐 ERD Preview</h2>
    <p>Find a full ERD in the presentation and visual formats below:</p>
    <ul>
      <li><a href="./erd/PulsPoint_ERD_Presentation.pptx">📎 ERD Presentation (PPTX)</a></li>
      <li><a href="./erd/pulspoint-erd-diagram.png">🖼️ Visual ERD (PNG)</a></li>
    </ul>
  </section>

  <section>
    <h2>📘 License</h2>
    <p>This project is developed for educational use. Contributions are welcome.</p>
  </section>

  <section>
    <h2>🙋‍♂️ Author</h2>
    <p><strong>Riyadun Nabi</strong><br />
       📧 your-email@example.com<br />
       🎓 BUET (Bangladesh University of Engineering and Technology)</p>
  </section>

  <div class="footer">© 2025 PulsPoint Project — All rights reserved.</div>
</body>
</html>
