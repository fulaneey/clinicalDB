# clinicalDB
# Clinic Appointment and Patient Management System

## 🏥 Description
A MySQL relational database designed for managing a clinic's patients, doctors, appointments, prescriptions, and treatments. It enforces data integrity through foreign keys and unique constraints while demonstrating 1:1, 1:M, and M:M relationships.

## 📌 Key Features
- Register doctors and assign them to departments
- Add and manage patient records
- Schedule appointments between doctors and patients
- Issue prescriptions per appointment
- Track treatments for patients (M:M)

### To populate this DB 

-- ===============================
-- Data Population
-- ===============================

-- Populate departments
INSERT INTO departments (dept_name) VALUES 
('Cardiology'), 
('Pediatrics'), 
('Neurology');

-- Populate doctors
INSERT INTO doctors (full_name, email, specialization, dept_id) VALUES
('Dr. John Smith', 'john.smith@clinic.com', 'Cardiologist', 1),
('Dr. Alice Green', 'alice.green@clinic.com', 'Pediatrician', 2),
('Dr. Marcus Lee', 'marcus.lee@clinic.com', 'Neurologist', 3);

-- Populate patients
INSERT INTO patients (full_name, dob, gender, phone, email) VALUES
('Jane Doe', '1990-04-15', 'Female', '08123456789', 'jane.doe@gmail.com'),
('David Johnson', '1985-07-22', 'Male', '08098765432', 'david.johnson@yahoo.com'),
('Emily White', '2000-12-05', 'Female', '07011223344', 'emily.white@outlook.com');

-- Populate appointments
INSERT INTO appointments (patient_id, doctor_id, appointment_date, reason) VALUES
(1, 1, '2025-05-10 09:30:00', 'Routine heart check-up'),
(2, 2, '2025-05-11 10:00:00', 'Fever and cough'),
(3, 3, '2025-05-12 11:00:00', 'Migraine evaluation');

-- Populate treatments
INSERT INTO treatments (treatment_name, description) VALUES
('ECG Test', 'Electrocardiogram test to monitor heart activity'),
('Antibiotic Course', '7-day prescription of antibiotics'),
('MRI Scan', 'Brain MRI scan for neurological issues');

-- Populate prescriptions
INSERT INTO prescriptions (appointment_id, medication, dosage) VALUES
(1, 'Aspirin', '75mg daily'),
(2, 'Amoxicillin', '500mg three times daily'),
(3, 'Ibuprofen', '400mg as needed');

-- Populate patient_treatments
INSERT INTO patient_treatments (patient_id, treatment_id, date_given) VALUES
(1, 1, '2025-05-10'),
(2, 2, '2025-05-11'),
(3, 3, '2025-05-12');


## ⚙️ How to Run

### 🧪 Requirements:
- MySQL Server or phpMyAdmin
- Any SQL client (e.g., MySQL Workbench, DBeaver)

### 📥 Import Steps:
```bash
mysql -u root -p < clinic_db.sql

