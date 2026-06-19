# 👋 Hi, I'm TalentedDc

A proactive, curious developer building things that solve real problems. I love clean code, thoughtful UX, and collaborating on open-source projects.

---

## About Me
- 🔭 I’m currently working on: **Smart Hospital Appointment and Ward Management System**
- 💼 Profession: _[Your profession — e.g., Software Engineer, Data Scientist, Healthcare Tech Lead]_
- 🌱 I’m learning: _[Current focus — e.g., Advanced Python OOP, System Design, Healthcare Interoperability]_
- 📍 Location: _[City, Country — optional]_
- ⚡ Fun fact: _[Short fun fact or hobby]_

---

## What I Do
I design and implement practical software solutions for real-world problems, with a focus on maintainability, data integrity, and user-centred workflows. I enjoy:
- Building reliable backend systems and APIs in Python
- Modelling real-world domains with clear OOP design
- Streamlining administrative workflows and reducing manual errors
- Documenting systems and writing tests for dependable delivery

---

## Top Skills
- Primary: **Python OOP**, **System Design**, **Data Modeling**
- Secondary: _[e.g., Flask/Django, SQL, REST APIs, Docker, CI/CD]_

---

## Featured Project — Smart Hospital Appointment and Ward Management System
A Python OOP system modelling administrative and clinical operations for a medium-sized Nigerian tertiary hospital. The system addresses paper-based workflows that commonly cause appointment clashes, lost prescriptions, and billing disputes by automating patient intake, scheduling, ward allocation, prescriptions, diagnostics, and billing with NHIS support.

Why it matters
- Many Nigerian hospitals still rely on manual paperwork; this system reduces errors, speeds patient flow, and improves accountability.
- NHIS-aware billing ensures insured patients receive correct deductions and itemised billing for transparency.

Core features
- Patient registration with NHIS support (verification fields and NHIS-deduction logic)
- Doctor scheduling across departments with conflict detection and availability windows
- Ward bed allocation by ward type (General, ICU, Maternity, Paediatric) with occupancy tracking
- Prescription lifecycle: creation, dispensing, modification, and history/audit trail
- Diagnostic test requests workflow and result linking
- Itemised bill computation with automatic NHIS deduction where applicable
- Role-based actors: Admin, Reception, Doctor, Nurse, Pharmacist, Accountant

Repository
- Repo name: TalentedDc/smart-hospital-management
- Link: https://github.com/TalentedDc/smart-hospital-management

Architecture & modules (high-level)
- models/ — Patient, NHISAccount, Doctor, Schedule, Ward, Bed, Prescription, TestRequest, Bill
- services/ — SchedulingService, WardAllocationService, PrescriptionService, BillingService
- persistence/ — Repository layer (SQL/ORM or in-memory for demo)
- scripts/ — Seed data, demo flows, and CLI utilities
- tests/ — Unit and integration tests for core workflows

Status
- Project status: _[Draft / Proof-of-concept / Working prototype / Production-ready]_
- Repo: https://github.com/TalentedDc/smart-hospital-management

Getting started (example)
1. Clone the repo: git clone <REPO_URL>
2. Create virtual env: python -m venv venv && source venv/bin/activate
3. Install: pip install -r requirements.txt
4. Seed demo data: python scripts/seed_demo.py
5. Run demo CLI or tests: python -m pytest

What I’d like to show / help with
- Realistic sample data for a Nigerian tertiary hospital (wards, doctors, NHIS sample IDs)
- End-to-end demo scenario: patient registers → appointment → ward allocation → tests → prescription → billing
- Tests that validate NHIS deduction logic and ward allocation constraints

---

## Mandatory GitHub Repository Structure (recommended)
your_project_name/
├── README.md                     # Full project documentation (this file)  
├── .gitignore                     # exclude venv, __pycache__, .env, etc.  
├── requirements.txt               # All third-party dependencies (may be empty)  
├── main.py                        # Entry point: demonstrates full system workflow (CLI/demo)  
├── src/  
│   ├── __init__.py  
│   └── models/                     # All domain models (classes)  
│       ├── patient.py  
│       ├── nhis_account.py  
│       ├── staff.py                # Doctor, Nurse, Admin classes  
│       ├── ward.py  
│       ├── bed.py  
│       ├── prescription.py  
│       └── bill.py  
│   └── services/                   # Business logic / services  
│       ├── scheduling_service.py  
│       ├── ward_allocation_service.py  
│       ├── prescription_service.py  
│       └── billing_service.py  
├── tests/  
│   ├── __init__.py  
│   └── test_<module>.py            # pytest test files (minimum 20 tests total)  
├── uml/  
│   ├── class_diagram.png           # UML class diagram export (PNG or SVG)  
│   └── class_diagram.puml          # PlantUML source OR .drawio file  
├── docs/  
│   └── design_notes.md             # Design justification document  
└── scripts/  
    └── seed_demo.py                # Seed realistic demo data and run example flows

---

## README.md Requirements — 8 Mandatory Sections

1) Project Title & Overview
- Title: Smart Hospital Appointment and Ward Management System
- Overview: See top of this README. The system solves problems in many Nigerian tertiary hospitals where administration is paper-based and error-prone: appointment clashes, lost prescriptions, and billing disputes. This project implements an OOP Python backend to manage patient registration (including NHIS), scheduling, ward allocation, prescriptions, diagnostic requests, and billing with NHIS support.

2) Team Members
- Oyebode Omobolaji — CPE/2023/1101 — @talenteddc
- Oyetayo Michael — CPE/2023/1102 — @michaeloyetayo6-bit
- Salawu Pelumi Dayo — CPE/2023/1105 — @pelumidayo43-art
- Temitope Ayomiposi Gideon — CPE/2023/1110 — @prinposh

3) OOP Concepts Demonstrated
A table with examples and where they appear in the code. (Ensure each Week 1–5 concept appears at least once.)

| OOP Concept | Location in Code (file / class / lines) | Week |
|-------------|------------------------------------------|------|
| Encapsulation (properties & validation) | src/models/patient.py : class Patient (@property validators for nhis_id, contact) | Week 1 |
| Inheritance (Staff hierarchy) | src/models/staff.py : class Staff -> class Doctor, Nurse, Admin | Week 2 |
| Polymorphism (Appointment handlers) | src/services/scheduling_service.py : AppointmentHandler subclasses for Walk-in vs Booked | Week 3 |
| Composition (Ward contains Beds) | src/models/ward.py : Ward has list[Bed] -> Bed objects created/managed by Ward | Week 3 |
| Aggregation (Patient ↔ Prescription history) | src/models/prescription.py : Prescription stored in Patient.prescriptions list | Week 4 |
| Association (Patient — NHISAccount) | src/models/nhis_account.py and src/models/patient.py | Week 2 |
| Abstraction (BaseService) | src/services/base_service.py : BaseService abstract class for common service methods | Week 1 |
| Cohesion & SRP (BillingService computes itemised bills only) | src/services/billing_service.py | Week 5 |

4) System Architecture
- Embed UML class diagram image: uml/class_diagram.png (also include source at uml/class_diagram.puml).
- High-level description (5–7 sentences):
  - The system follows a layered architecture separating domain models (src/models), business services (src/services), persistence/repositories, scripts for seeding/demo, and tests. Domain objects (Patient, NHISAccount, Staff, Ward, Bed, Prescription, Bill) encapsulate data and related behaviors. Services implement workflows (scheduling, ward allocation, prescriptions, billing) and coordinate model interactions. Composition is used for Ward→Bed (Ward "owns" Bed objects). Aggregation is used where Patient references but does not own external resources (e.g., historical records stored externally). The persistence layer is abstracted so the project can use SQLite for demo and PostgreSQL for production. Design choices favor high cohesion and single responsibility per class.

5) How to Run
Exact commands to clone the repo, create venv, install deps, seed demo, and run tests.
- Clone the repo:
  - git clone https://github.com/TalentedDc/smart-hospital-management.git
  - cd smart-hospital-management
- Create and activate virtual environment:
  - python3 -m venv venv
  - source venv/bin/activate   # Linux/macOS
  - venv\Scripts\activate      # Windows (PowerShell: .\venv\Scripts\Activate.ps1)
- Install dependencies:
  - pip install -r requirements.txt
- Seed demo data and run a CLI demo:
  - python scripts/seed_demo.py
  - python main.py --demo
- Run tests:
  - pytest -q
- Notes: If using a real DB, configure DATABASE_URL in .env and run migrations (example with Alembic).

6) Sample Output
Paste at least 8 lines of real console output showing the system working (example demo run):

```
[INFO] 2026-06-19 10:00:00 - Creating demo NHIS account for patient NG-000123
[INFO] 2026-06-19 10:00:01 - Registered Patient: John Doe (NHIS: NG-000123) — PatientID: P0001
[INFO] 2026-06-19 10:00:02 - Appointment scheduled: Dr. A. Okeke | Dept: Pediatrics | 2026-07-05 09:00
[INFO] 2026-06-19 10:00:03 - Ward allocation: Paediatric Ward — Bed B-12 assigned to PatientID P0001
[INFO] 2026-06-19 10:00:04 - Prescription created: Amoxicillin 250mg x 7 days | PrescID: RX0009
[INFO] 2026-06-19 10:00:05 - Diagnostic requested: Full Blood Count | TestID: T-1002
[INFO] 2026-06-19 10:00:06 - Bill computed: Total=₦18,500.00 NHIS-covered=₦12,950.00 PatientPay=₦5,550.00
[INFO] 2026-06-19 10:00:07 - Payment recorded: Patient P0001 paid ₦5,550.00 via POS
[INFO] 2026-06-19 10:00:08 - Discharge summary generated for Patient P0001 — Records archived
```

7) Known Limitations
- NHIS integration is simulated for demo; production requires secure API integration and authentication with NHIS services.
- Concurrency: current in-memory demo persistence has race conditions; production must use transactional DB and locks.
- No front-end UI included (CLI/demo only). UI and authentication/authorization are out of scope for the prototype.
- Scalability: designed for medium-sized hospitals; high-load multi-tenant deployment needs further refactor.
- Security: demo does not encrypt sensitive data nor implement full audit logging — must add before production.

8) References
- Python documentation — https://docs.python.org/3/
- pytest documentation — https://docs.pytest.org/
- PlantUML — https://plantuml.com/
- National Health Insurance Scheme (NHIS) — https://www.nhis.gov.ng/ (for NHIS policy and contact)
- General OOP & Design Patterns references used during design (Gang of Four, SOLID principles)

---

## Commit & Project Discipline (notes)
- Aim for minimum 15 commits spread across the development period (avoid single last-day commits).
- Use descriptive commit messages: e.g., "feat: add Ward allocation service" or "fix: validate NHIS id format in Patient model".
- Include unit tests for each feature; maintain at least 20 pytest tests covering core workflows and edge cases.

---

If you want, I can:
- Fill Team Members and exact file/line locations for the OOP table using the real code once you push it.
- Generate the UML diagram (PlantUML) and add it to uml/class_diagram.puml and uml/class_diagram.png.
- Create the smart-hospital-management repo scaffold and commit this README as README.md there.

Please provide any additional details you want added (tech stack, project status, license), or say "done" to finish.