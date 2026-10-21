# ⛅ India Daily Weather Analytics System

A full-stack weather analytics dashboard for exploring historical weather data across major Indian cities. Built as a collaborative DBMS mini project using Node.js, Express, MySQL, and a responsive web interface.

**[🌐 Live Demo](https://weather-analytics-system-production.up.railway.app)** · **[📂 GitHub Repository](https://github.com/Akanksha2007/weather-analytics-system)**

## ✨ Features

- **City-based filtering:** Select cities and explore their weather records.
- **Date range filtering:** Analyze weather data across specific time periods.
- **Weather analytics:** View average, maximum, and minimum temperatures, total rainfall, and average wind speed.
- **Database integration:** Retrieve weather records using SQL queries and JOIN operations.
- **Record management:** Add weather records and delete records with confirmation.
- **Responsive dashboard:** Explore weather information through a dark-themed user interface.
- **REST API:** Access weather records and aggregated analytics through backend endpoints.

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Frontend | HTML, CSS, JavaScript |
| Backend | Node.js, Express.js |
| Database | MySQL |
| Dataset processing | Python |
| Dataset | Open-Meteo historical weather data |
| Deployment | Railway |

## 🏗️ Architecture

The application follows a simple three-layer architecture:

1. **Frontend:** Provides the dashboard, filters, and weather data visualizations.
2. **Backend:** Exposes REST APIs using Node.js and Express.
3. **Database:** Stores city information and daily weather records in MySQL.

The frontend communicates with the backend through HTTP requests, while the backend queries MySQL to retrieve and manage the data.

## 📁 Project Structure

```text
weather-analytics-system/
├── backend/
│   ├── server.js
│   ├── db.js
│   ├── package.json
│   └── .env.example
├── frontend/
│   ├── index.html
│   ├── style.css
│   └── app.js
├── database/
│   ├── schema.sql
│   └── import_data.py
├── data/
├── package.json
├── railway.json
└── README.md
```

## 🚀 Getting Started

### Prerequisites

Install the following tools:

- [Node.js](https://nodejs.org/) (version 16 or later)
- [MySQL](https://dev.mysql.com/downloads/)
- [Python](https://www.python.org/downloads/)
- [Git](https://git-scm.com/downloads/)

### 1. Clone the repository

```bash
git clone https://github.com/Akanksha2007/weather-analytics-system.git
cd weather-analytics-system
```

### 2. Set up the database

Start MySQL and execute the database schema:

```bash
mysql -u root -p
```

Inside the MySQL prompt, run:

```sql
source database/schema.sql;
```

### 3. Import the weather dataset

Place the required CSV dataset at `data/weather_data.csv`, then run the provided import script:

```bash
python database/import_data.py
```

If the script generates `database/seed_data.sql`, import the generated data into the database:

```bash
mysql -u root -p weather_db < database/seed_data.sql
```

### 4. Configure environment variables

Create a `.env` file inside the `backend` directory using `.env.example` as a template.

Configure the values for your local MySQL instance:

```env
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=weather_db
PORT=3000
```

Use your own local database credentials. Never commit real passwords or secrets to GitHub.

### 5. Install dependencies and run

From the project root, install the backend dependencies:

```bash
cd backend
npm install
npm start
```

Open the local application at:

**http://localhost:3000**

Ensure the database is running and configured correctly before starting the server.

## 🔌 REST API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/cities` | Retrieve available cities |
| GET | `/weather` | Retrieve weather records |
| GET | `/analytics` | Retrieve aggregated weather analytics |
| POST | `/weather` | Add a weather record |
| DELETE | `/weather/:id` | Delete a weather record |

The weather and analytics endpoints support filtering by city and date range. The weather endpoint also supports a result limit.

Example query parameters:

```text
/weather?city_id=1&start_date=2023-01-01&end_date=2023-12-31
```

*Note: Query parameter values depend on the IDs and dates present in the database.*

## 🌦️ Dataset

The project is documented as using historical daily weather data for ten Indian cities:

- Delhi
- Mumbai
- Chennai
- Bengaluru
- Kolkata
- Hyderabad
- Pune
- Ahmedabad
- Jaipur
- Lucknow

**Documented coverage:** 2000–2024, with approximately 91,300 daily records.

**Data source:** [Open-Meteo](https://open-meteo.com/)

## ☁️ Deployment

The project is configured for deployment on [Railway](https://railway.app/), with the backend and database hosted in the deployment environment.

The live application is available at:

**https://weather-analytics-system-production.up.railway.app**

Live availability depends on the deployment and its database configuration.

## 🎓 Learning Outcomes

This project demonstrates practical experience with:

- Relational database design and SQL queries
- SQL JOINs and aggregate functions
- REST API development with Express.js
- Frontend-to-backend integration
- Data filtering and weather analytics
- Environment configuration and cloud deployment

## 🤝 Contributors

This is a collaborative project.

- **Akanksha2007** — [GitHub Profile](https://github.com/Akanksha2007)
- **Aarav Gupta** — [GitHub Profile](https://github.com/aaravgupta8)

Please acknowledge each contributor's actual work and contributions.

## 📄 License

No license has been specified yet. Please agree on a license with your collaborator before adding one.

---

*Built as a collaborative DBMS mini project to explore historical weather data through a full-stack analytics application.*
