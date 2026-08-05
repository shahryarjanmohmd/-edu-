# EDU System

A simplified university **Educational Management System** written in C  
(Fundamentals of Programming course project).

---

## Features

### Roles
| Role | Capabilities |
|------|----------------|
| **Admin** | Manage students, faculty, courses, offerings, requests, calendar |
| **Faculty** | Offer courses, capacity requests, grade recording (manual + CSV), LMS |
| **Student** | Enroll / withdraw, report card, survey, homework & exam |

### Core
- Calendar phases (offering → unit selection → class & exams → grades → survey)
- Course offering with admin approval
- Capacity increase & removal requests
- Prerequisites & capacity checks on enrollment
- Report card with **semester GPA** and **overall GPA**
- Search by field (course name, faculty, capacity, …)
- Persistent storage (`students.json`, `faculty.json`, `courses.json`, `offerings.json`, …)

### Bonus
- Course survey + statistical analysis (mean, stdev, quartiles, chart)
- LMS: homework & exams (MCQ / descriptive)
- PhD thesis submission & grading

---

## Build & Run

```bash
gcc -o edu.exe edu.c -Wall
edu.exe
```

On Linux / macOS:

```bash
gcc -o edu edu.c -Wall -lm
./edu
```

> `-lm` is needed for survey statistics (`sqrt`).

---

## Default Accounts

| Role | Username | Password |
|------|----------|----------|
| Admin | `admin` | `admin123` |
| Student | `404123456` | `123456` |
| Faculty | `dr_karimi` | `karimi123` |

**Student security questions** (`404123456`):
- Birthplace: `Karaj`
- First school: `Shahid Beheshti`
- First book: `Anne Shirley`
- Bicycle color: `White`

---

## Notes

- **Offering IDs** are numeric: `01`, `02`, `03`, … (also accepts `1` or `O1`)
- **Passing grade:** `>= 10`
- Decimal grades supported (e.g. `9.75`, `18.5`)
- Courses added mid-term are locked until the next offering period
- Runtime data files are git-ignored and recreated on first run

---

## Project Structure

```
edu.c           Main source code
README.md       This file
.gitignore      Ignored build & data files
```

---

## License

Educational use only — Fundamentals of Programming course project.
