# 📊 SMP Command Centre Dashboard

![Python Version](https://img.shields.io/badge/python-3.8%2B-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Status](https://img.shields.io/badge/status-active-brightgreen.svg)

A lightweight, terminal-based analytics dashboard and data pipeline written in Python. The **SMP Command Centre** aggregates member activity metrics (daily steps, dietary fasting protocols, sleep, cold exposure habits), tracks weekly community-wide physical output, monitors active skill-sharing class enrollments, and exports structured operational summaries in JSON format.

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Data Architecture](#-data-architecture)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#-usage)
- [Example Terminal Output](#-example-terminal-output)
- [JSON Schema & Export](#-json-schema--export)
- [Project Structure](#-project-structure)
- [License](#-license)

---

## 🔍 Overview

The SMP Command Centre serves as a central hub for processing and visualizing performance metrics across three core operational pillars:
1. **Member Metrics:** Evaluates individual step goals, fasting protocol distributions (OMAD/2MAD), cold shower compliance, and sleep patterns.
2. **Weekly Performance:** Processes daily aggregate step counts, calculates weekly averages, and identifies peak activity days using ASCII visual data bars.
3. **Skill Ecosystem:** Tracks active community workshops, student enrollments, and identifies high-demand instructors.

---

## ✨ Key Features

- **Zero External Dependencies:** Built entirely with standard Python libraries (`json`).
- **Data Aggregation Pipeline:** Includes utility functions (`process_members`, `process_weekly`, `process_skills`) to digest raw payloads into calculated KPIs.
- **Visual ASCII Terminal UI:** Formatted dashboard displaying step goals, daily progression charts, and sorted skill enrollment rankings.
- **JSON Data Export:** Standardized JSON output ready for downstream API consumption or dashboard persistence.

---

## 📐 Data Architecture

```text
                   ┌──────────────────────┐
                   │ Raw Endpoint Feeds   │
                   └──────────┬───────────┘
                              │
     ┌────────────────────────┼────────────────────────┐
     ▼                        ▼                        ▼
┌──────────────────┐    ┌──────────────────┐    ┌──────────────────┐
│  fetch_members() │    │ fetch_weekly...()│    │  fetch_skills()  │
└────────┬─────────┘    └────────┬─────────┘    └────────┬─────────┘
        │                        │                        │
        ▼                        ▼                        ▼
┌──────────────────┐    ┌──────────────────┐    ┌──────────────────┐
│ process_members()│    │ process_weekly() │    │ process_skills() │
└────────┬─────────┘    └────────┬─────────┘    └────────┬─────────┘
        │                        │                        │
        └────────────────────────┼────────────────────────┘
                                 │
                                 ▼
                      ┌──────────────────────┐
                      │  Formatted Dashboard │
                      │    & JSON Export     │
                      └──────────────────────┘
```

---

## 🚀 Getting Started

### Prerequisites

- **Python 3.8+** installed on your system. No additional third-party dependencies are required.

### Installation

1. Clone the repository:
   ```bash
  git clone https://github.com/your-username/smp-command-centre.git
  ```

2. Navigate to the project directory:
  ```bash
  cd smp-command-centre
  ```

## 💻 Usage
Run the main dashboard script directly via Python:
```bash
python main.py
```

🖥️️ Example Terminal Output
```text
*********************************************************
  SMP COMMAND CENTRE DASHBOARD  |  YEAR 2026, Week 33-37
*********************************************************

  MEMBERS IN THE SMP PROGRAM
  1. Member 1
  2. Member 2
  3. Member 3
  4. Member 4
  5. Member 5
  6. Member 6

  SECTION 1: MEMBER PERFORMANCE
  Total members:               6
  Hit {STEP_GOAL:,} step goal: 4/6
  Average steps:               9,500
  Cold showers today:          5/6
  Goal hitters: Member 2, Member 4, Member 6
---------------------------------------------------------

  SECTION 2: WEEKLY STEPS
  DAY     TOTAL STEPS    BAR
  Mon     :     54,200   ||||||||||
  Tue     :     62,000   ||||||||||||
  Wed     :     58,400   |||||||||||
  Thu     :     71,000   ||||||||||||||
  Fri     :     49,600   |||||||||
  Sat     :     68,000   |||||||||||||
  Sun     :     65,200   |||||||||||||
  Best day: Thu (71,000 total steps)
  Week avg: 61,200 steps/day
---------------------------------------------------------

  SECTION 3: ACTIVE SMP SKILLS
  copywriting     15 enrolled
  tiling          12 enrolled
  phone repair    10 enrolled
  welding         8 enrolled
  beekeeping      6 enrolled
  Most popular: copywriting (15 enrolled)

---------------------------------------------------------
```

## JSON export:
```json
{
  "week": "2024-W47",
  "members": {
    "total": 6,
    "goal_met": 4,
    "avg_steps": 9500
  },
  "weekly": {
    "best_day": "Thu",
    "total_steps": 428400
  },
  "skills": {
    "active": 5,
    "most_popular": "copywriting"
  }
}
```

## 📄 JSON Schema & Export
The system automatically generates a payload summarizing overall activity:
```json
{
  "week": "2024-W47",
  "members": {
    "total": 6,
    "goal_met": 4,
    "avg_steps": 9500
  },
  "weekly": {
    "best_day": "Thu",
    "total_steps": 428400
  },
  "skills": {
    "active": 5,
    "most_popular": "copywriting"
  }
}
```

## 📁 Project Structure
```text
smp-command-centre/
│
├── main.py            # Core application containing data fetchers, processors & dashboard display
├── README.md          # Project documentation
└── .gitignore         # Standard git ignore configurations
```

## 📜 License
Distributed under the MIT License. See LICENSE for more information.

##Auther
Branham Simiyu

