# Finding: Higher Education & Independent Tracking

This module documents how the system manages students who have transitioned out of residential or primary schooling programs but remain under the Bangla Hope sponsorship and academic support programs.

---

## 1. The "Higher Education" Module
Students finishing their secondary education move into this module. It is not an "Archive"; it is an active educational program.

### Key Data Requirements
- **Institution:** The university/college (e.g., Bangladesh Adventist Seminary, Nursing College).
- **Major/Course:** Field of study.
- **Academic Status:** Current standing (e.g., Good Standing, Hold).
- **Tuition/Support:** Monthly/Semester subsidy amount.
- **Graduation Target:** Expected completion date.

---

## 2. Transition Logic (Promoted to Higher Ed)
- **Status:** Students in this module are `ACTIVE_HIGHER_ED`.
- **Relationship:** They are linked via their `Master_ID (UUID)`. Their previous records (LRC/Boarding) are archived, but they remain "Active" participants in the system.

---

## 3. Dynamic Institution Registry
To avoid hardcoding, the system will implement an "Institution Registry":
- **Admin Management:** Admins can add/edit/archive institutions (Name, Location, Contact Info).
- **Dynamic UI:** The Higher Education module will dynamically fetch these institutions.
- **Scalability:** When a new partnership is formed, adding it to the Registry makes it immediately available in the Higher Ed dashboard without code changes.

---

## 4. Addressing the "Remarks/Hold" Status
The current remarks provided (e.g., "Hold", "Re-take Exam", "New Admit") should be mapped to an **"Academic Alert"** field in the UI.

- **Status Field:** [Good Standing | Academic Probation | Hold | Exam Retake].
- **UI Marker:** A yellow/orange tag on the Student Profile to indicate an alert exists for that student.
