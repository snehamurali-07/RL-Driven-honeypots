# AI-Enabled Student Advising Assistant for Course Pathway Planning
An AI assistant for academic advising that optimizes course plans based on degree rules, student history, and resource constraints. Features rule- and learning-based modeling, interactive advisor editing/annotation, and robust guardrails to ensure viable, equitable pathways at scale.

> **Graph-Based Prerequisite Modeling & Capacity-Aware Student Advising Platform**

[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![Neo4j](https://img.shields.io/badge/Neo4j-008CC1?style=for-the-badge&logo=neo4j&logoColor=white)](https://neo4j.com/)
[![MySQL](https://img.shields.io/badge/MYSQL-316192?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

---

## 📖 Overview

Higher education academic advisors face the daunting task of balancing complex degree requirements, prerequisite networks, course seat capacities, and individual student interests. Manual advising is slow, error-prone, and difficult to scale across thousands of students—especially under flexible credit frameworks like **NEP 2020 (Academic Bank of Credits)**.

**AI Enabled Student Advising Assistant for Course Pathway Planning** is a neuro-symbolic AI assistant designed for academic advisors. It combines **symbolic knowledge graphs** (for 0% prerequisite violation guarantees) with **predictive machine learning** (for seat capacity forecasting) and an **interactive Human-in-the-Loop (HITL) dashboard** for advisor annotations and overrides.

---

## ✨ Key Features

- 🕸️ **Prerequisite Knowledge Graph Engine:** Maps multi-tier prerequisite trees, co-requisites, and credit caps using graph structures for instant validation ($\le 200\text{ ms}$).
- 🔮 **Predictive Demand & Capacity Forecaster:** Uses machine learning models to forecast elective course demand 4 to 6 weeks prior to registration, preventing capacity bottlenecks.
- 🛡️ **Symbolic Guardrails & Fairness Engine:** Enforces constraint solvers to prevent timetable collisions, over-allocated seats, and inequitable distribution of high-demand electives.
- 📝 **Human-in-the-Loop (HITL) Dashboard:** Enables advisors to inspect generated degree tracks, annotate plans, and apply custom overrides in $\le 2$ clicks.

---

## 🏗️ System Architecture
```mermaid
graph TD
    %% Define Styles
    classDef default fill:#1e293b,stroke:#f8fafc,stroke-width:2px,color:#ffffff;
    classDef highlight fill:#fffbeb,stroke:#d97706,stroke-width:2.5px,color:#78350f;

    %% Nodes
    A[Student Data & Requests]
    B[Rule-Based Component <br> Knowledge Graphs <br> Enforces Prerequisites & Credit Policies]
    C[Learning-Based Model <br> Predictive Analytics <br> Forecasts Capacity & Student Demands]
    D[Guardrailed Optimization <br> Filters Out Infeasible & Inequitable Schedules]
    E[Human-in-the-Loop Portal <br> Advisor Annotations & Final Overrides/Approval]

    %% Connections
    A --> B
    A --> C
    B --> D
    C --> D
    D --> E

    %% Apply Styles
    class B,C,D highlight;
```


---

## 🛠️ Tech Stack

| Layer | Technologies Used |
| :--- | :--- |
| **Frontend UI** | React.js / Next.js, TypeScript, Tailwind CSS, React Flow |
| **Backend API** | FastAPI (Python 3.10+), SQLAlchemy, Pydantic, OAuth2 / JWT |
| **Graph & Rules** | Neo4j / NetworkX (Python) |
| **ML & Analytics** | Scikit-Learn, XGBoost, Pandas, Google OR-Tools |
| **Database** | **MySQL 8.0+** (Relational Data), Neo4j (Graph Dependencies) |
| **DevOps** | Docker, Git, GitHub Actions |

---

## 🚀 Getting Started

### Prerequisites

Ensure you have the following installed locally:
- **Node.js** ($\ge$ v18.x) & **npm**
- **Python** ($\ge$ 3.10)
- **MySQL Server** ($\ge$ 8.0)
- **Neo4j Desktop / Server**

---

### 1. Database Setup (MySQL)

Create a MySQL database and configure the credentials:

```sql
CREATE DATABASE student_advising_db;
CREATE USER 'advising_user'@'localhost' IDENTIFIED BY 'your_secure_password';
GRANT ALL PRIVILEGES ON student_advising_db.* TO 'advising_user'@'localhost';
FLUSH PRIVILEGES;
```

### 2. Backend Installation
Clone the repository:

```Bash
git clone [https://github.com/your-username/ai-student-advising-assistant.git](https://github.com/your-username/ai-student-advising-assistant.git)
cd ai-student-advising-assistant/backend
```
Create and activate a virtual environment:

```Bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```
Install dependencies:

```Bash
pip install -r requirements.txt
```
Configure Environment Variables (.env):
Create a .env file in the backend/ directory:
```
Code snippet
# MySQL Configuration
MYSQL_HOST=localhost
MYSQL_PORT=3306
MYSQL_USER=advising_user
MYSQL_PASSWORD=your_secure_password
MYSQL_DATABASE=student_advising_db
DATABASE_URL=mysql+pymysql://advising_user:your_secure_password@localhost:3306/student_advising_db

# Neo4j Configuration
NEO4J_URI=bolt://localhost:7687
NEO4J_USER=neo4j
NEO4J_PASSWORD=your_neo4j_password

# Security
SECRET_KEY=your_jwt_secret_key
ALGORITHM=HS256
```

Run Database Migrations & Start FastAPI:

```Bash
alembic upgrade head
uvicorn main:app --reload
```
*The backend API server will start at http://localhost:8000 (API Docs at /docs).*

### 3. Frontend Installation
Navigate to the frontend directory:

```Bash
cd ../frontend
```
Install node dependencies:
```Bash
npm install
```
Configure Environment Variables (.env.local):

```Code snippet
NEXT_PUBLIC_API_BASE_URL=http://localhost:8000/api/v1
```
Run the development server:

```Bash
npm run dev
```
*The client interface will start at http://localhost:3000.*

---

### 📅 Development Roadmap
[x] Phase 1: Requirements Analysis, Data Collection & MySQL Schema Design

[x] Phase 2: Knowledge Graph Construction & Rule-Based Constraint Engine

[ ] Phase 3: Machine Learning Capacity Demand Forecaster Integration

[ ] Phase 4: Interactive Advisor Dashboard & Guardrail Verification

[ ] Phase 5: System Testing, Evaluation, and Final Deployment

---

## 👥 Team & Credits

This project was developed by:

- **[Sneha Murali]** - *Role / Lead Focus* (e.g., Knowledge Graph Architecture, FastAPI Backend, Core AI Logic) - [@yourusername](https://github.com/yourusername)
- **[Chandana N]** - *Role / Focus* (e.g., Frontend Dashboard, React.js UI/UX, Data Visualization) - [@member2username](https://github.member2username)
- **[Lahari GM]** - *Role / Focus* (e.g., Machine Learning Demand Forecaster, MySQL Database & Schema) - [@member3username](https://github.member3username)
- **[Tejaswini A]** - *Role / Focus* (e.g., Constraint Guardrails Optimization, System Integration & Testing) - [@member4username](https://github.member4username)

---

### 🏫 Academic Supervision & Guidance
Special thanks to our project supervisor and institution for guidance throughout the development lifecycle:
- **Project Guide:** Ms. Ashishika Singh, Assistant Professor, *School of Computer Science & Engineering*
- **Institution:** Presidency University, Bangalore.

---
