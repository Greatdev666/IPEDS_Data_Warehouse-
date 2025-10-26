# 📘 IPEDS Data Integration Project  
**Longitudinal Higher Education Analysis (2000–2023)**  

---

## 🧭 1. Analysis Coverage

This project integrates and analyzes **IPEDS data from 2000 to 2023 (24 years)** to explore long-term higher education trends across U.S. institutions.

### ⚠️ Why the analysis starts at 2000
Years prior to 2000 were excluded because:

- 🧩 **Inconsistent file structures and naming** before 2000 modernization.  
- 📉 **Missing or incomplete datasets**, especially for Finance, Enrollment, and Staff.  
- ❌ **No reliable UNITID crosswalks** for linking institutions across time.  
- 📊 **2000 onward** marks the start of consistent data schema, standard variable codes, and digital formats (CSV/Stata).

**✅ Final Scope:** `2000–2023`  
**🚫 Excluded:** `1980–1999` (inconsistent schema, limited coverage)

---

## 🗂️ 2. Core Files by Category

| **Category** | **Example 2023 Files** | **Notes / Key Variables** |
|---------------|------------------------|----------------------------|
| **Admissions** | `adm2023` | Admission applications, offers, and enrollments |
| **Completions** | `c2023_a`, `c2023_b`, `c2023_c` | Awards by program, level, and gender/race |
| **Derived/Validation (DRV)** | `drvc2023`, `drvef2023`, etc. | Derived/summary datasets; not available in all years |
| **Enrollment (EF)** | `ef2023a`, `ef2023b`, `ef2023c`, `ef2023d` | Headcounts by level, attendance, race, and gender |
| **Enrollment (12-month / EFFY)** | `effy2023`, `effy2023_dist` | Annual unduplicated headcounts; `_dist` = distance learning |
| **Finance** | `f2223_f1a`, `f2223_f2`, `f2223_f3` | Revenue, expenses, tuition; varies by institution type |
| **Flags** | `flags2023` | Data availability & participation flags |
| **Graduation Rates** | `gr2023`, `gr200_23` | 100% and 150% completion rates |
| **Institutional Characteristics (HD / IC)** | `hd2023`, `ic2023`, `ic2023_ay`, `ic2023_py` | Core institutional metadata (UNITID, name, control, degree levels, tuition) |
| **Staff (S)** | `s2023_is`, `s2023_sis` | Instructional vs. Non-instructional staff |
| **Staff Salaries (SAL)** | `sal2023_is`, `sal2023_nis` | Faculty and non-faculty salary data |
| **Student Aid (SFA)** | `sfa2223`, `sfav2223` | Aid distribution and student financial support |
| **Distance Learning** | `ef2023a_dist`, `effy2023_dist` | Distance education participation metrics |

---

## 👩‍🏫 3. Staff & Salary File Evolution (Name Changes)

| **Modern File (2012+)** | **Equivalent in 2011** | **Description** | **2001 & Older** | **2002–2011** |
|--------------------------|------------------------|------------------|------------------|----------------|
| `sYYYY_is` | `s2011_F` | Instructional staff (main faculty file) | `Fa_YYYY_hd` | `hd_YYYY` |
| `sYYYY_sis` | *Not found yet (pre-2012)* | Non-instructional / administrative staff | `sal_YYYY_a_s` | `sal_YYYY_a` |
| `salYYYY_is` | `SAL2011_A_rv` | Instructional staff salaries | N/A | `sal_YYYY_a` |
| `salYYYY_nis` | *Not found yet (pre-2012)* | Non-instructional staff salaries | N/A | `sal_YYYY_a_lt9` |

### 🟦 Notes
- From **2012 onward**, IPEDS split staff files into:
  - `s_is` → Instructional staff  
  - `s_sis` → Non-instructional staff  
- **Pre-2012** data (e.g. `SALYYYY_A` or `salYYYY_a`) often combines multiple staff categories.  
- **Pre-2002** files (`Fa_YYYY_hd`) merged staff, tenure, and contract data under older survey names — inconsistent across years.

---

## 📅 4. Data Coverage Tracking (2000–2023)

Each file type was tracked across years to identify missing datasets.  
✅ = Available ❌ = Not Available  

| Year | adm | C_a | DRV | EF | EFFY | EFFY_DIST | F_f1a | flags | gr | hd | IC | s_is | s_sis | sal_is | sal_nis | sfa | ef_dist | C_b | C_c | F_f2 | F_f3 |
|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|
| 2023 | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2022 | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2021 | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2020 | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2019 | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2018 | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2017 | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2016 | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2015 | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2014 | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2013 | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2012 | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2011 | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ |
| 2010 | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ |
| 2009 | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ |
| 2008 | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ |
| 2007 | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ |
| 2006 | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ |
| 2005 | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ |
| 2004 | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ |
| 2003 | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ |
| 2002 | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ |
| 2001 | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ |
| 2000 | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ |

---

## 🧱 5. Data Architecture (Next Stage)

---

**Author:** Muhammad Bashir aka DELEX 
**Project Repository:** [https://github.com/Greatdev666/IPEDS_Data_Warehouse]  
**Last Updated:** October 2025
