# Campus Project Hub 🎓

### Find Skills. Build Projects. Find Teammates.

Campus Project Hub is a full-stack web application designed to help college students discover projects, collaborate with other students, showcase their technical skills, and build project teams. It provides a centralized platform for managing projects, student profiles, and team collaboration requests.

The application is developed using **React, Spring Boot, and MySQL**, with a REST API connecting the frontend and backend.

---

## 🌐 Live Demo

- **Frontend:** [Add your deployed frontend URL here]
- **Backend API:** https://campus-project-hub-backend.onrender.com
- **Source Code:** https://github.com/ashrith-patel-31/CAMPUS-PROJECT-HUB

> Note: Replace the frontend placeholder with your actual deployed website URL.

## 📌 Project Overview

Students often find it difficult to discover suitable projects, identify teammates with complementary skills, and organize project collaboration. Campus Project Hub addresses this problem by offering a platform where students can create projects, explore available opportunities, manage their profiles, and submit requests to join project teams.

## ✨ Key Features

- **User Registration and Login** — Create an account and access the platform.
- **Student Profiles** — Maintain student information, academic details, branch, year, and technical skills.
- **Project Management** — Create, view, edit, and delete projects.
- **Project Discovery** — Explore projects by category, skills, and team requirements.
- **Join Requests** — Submit requests to collaborate on projects.
- **Request Status Tracking** — View the status of submitted join requests.
- **Team Collaboration** — Connect students with shared technical interests.
- **Persistent Database** — Store user and project information in MySQL.
- **Responsive Web Interface** — Access the application through a modern web browser.

## 🛠️ Technology Stack

| Layer | Technologies |
|---|---|
| Frontend | React.js, Vite, JavaScript, HTML5, CSS3 |
| Routing | React Router |
| HTTP Client | Axios |
| Backend | Java, Spring Boot |
| API | RESTful APIs |
| Database | MySQL |
| ORM | Spring Data JPA, Hibernate |
| Build Tool | Maven |
| Version Control | Git and GitHub |
| Deployment | Render |
| Database Hosting | Aiven MySQL |

## 🏗️ System Architecture

```text
             STUDENT / USER
                    |
                    v
       +--------------------------+
       |     React Frontend       |
       |  React + Vite + Axios    |
       +--------------------------+
                    |
             HTTP / REST API
                    |
                    v
       +--------------------------+
       |    Spring Boot Backend   |
       |  Controllers / Services  |
       |  Repositories / Entities |
       +--------------------------+
                    |
             Spring Data JPA
                    |
                    v
       +--------------------------+
       |       MySQL Database     |
       | Users / Projects /       |
       | Join Requests            |
       +--------------------------+
```

## 📂 Project Structure

```text
CAMPUS-PROJECT-HUB/
│
├── FRONTEND/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── package.json
│   └── vite.config.js
│
├── BACKEND/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── com/campus/campus_project_hub_backend/
│   │   │   │       ├── controller/
│   │   │   │       ├── entity/
│   │   │   │       ├── repository/
│   │   │   │       └── service/
│   │   │   └── resources/
│   │   │       └── application.properties
│   │   └── test/
│   └── pom.xml
│
└── README.md
```

*The folder names shown above are representative; adjust them if your actual project structure differs.*

## ⚙️ Prerequisites

Install the following software before running the project locally:

- Node.js and npm
- Java Development Kit (JDK) 21
- Apache Maven, or use the Maven Wrapper if included
- MySQL Server or a configured MySQL database
- Git
- A code editor such as Visual Studio Code or IntelliJ IDEA

## 🚀 Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/ashrith-patel-31/CAMPUS-PROJECT-HUB.git
cd CAMPUS-PROJECT-HUB
```

### 2. Configure the backend

Navigate to the backend folder:

```bash
cd BACKEND
```

Configure the following environment variables for your database connection:

```text
SPRING_DATASOURCE_URL
SPRING_DATASOURCE_USERNAME
SPRING_DATASOURCE_PASSWORD
```

The database URL should include the correct database host, port, database name, and any required SSL parameters.

Do not commit database passwords or other secrets to GitHub.

Start the Spring Boot application:

```bash
mvn spring-boot:run
```

The backend will normally run at:

```text
http://localhost:8080
```

### 3. Configure the frontend

Open a second terminal from the repository root:

```bash
cd FRONTEND
npm install
```

Configure the frontend API base URL to point to your local backend:

```text
http://localhost:8080
```

For the deployed application, use your actual deployed backend URL instead.

Start the frontend development server:

```bash
npm run dev
```

Open the local URL displayed by Vite, usually:

```text
http://localhost:5173
```

## 🔌 API Endpoints

The following endpoints represent the current backend API structure.

### User APIs

| Method | Endpoint | Purpose |
|---|---|---|
| POST | `/api/users/register` | Register a new user |
| POST | `/api/users/login` | Log in a user |
| PUT | `/api/users/{id}` | Update a user profile |

### Project APIs

| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/api/projects` | Retrieve projects |
| GET | `/api/projects/{id}` | Retrieve a project by ID |
| POST | `/api/projects` | Create a project |
| PUT | `/api/projects/{id}` | Update a project |
| DELETE | `/api/projects/{id}` | Delete a project |

> Join-request endpoints depend on the mappings implemented in your `JoinRequestController`. Add their exact routes here after verifying the controller source.

## 🗄️ Database Design

The application uses MySQL to persist application data.

The main data entities include:

- **Users:** Stores student account and profile information.
- **Projects:** Stores project titles, descriptions, categories, required skills, and team information.
- **Join Requests:** Stores requests to join projects and their current statuses.

Spring Data JPA and Hibernate are used to map Java entities to database tables.

## ☁️ Deployment

The application uses the following deployment services:

- **Frontend:** Render static site or another compatible static hosting provider.
- **Backend:** Render web service.
- **Database:** Aiven MySQL.

### Deployment configuration

1. Push the source code to GitHub.
2. Deploy the frontend using the `FRONTEND` directory as its root directory.
3. Deploy the backend using the `BACKEND` directory as its root directory.
4. Configure the backend's database connection through environment variables.
5. Configure the frontend API base URL to point to the deployed backend.
6. Allow requests from the deployed frontend origin in the backend CORS configuration.
7. Test registration, login, project operations, and join requests on the live website.

## 🔒 Security Considerations

- Store database credentials in environment variables.
- Do not upload `.env` files containing secrets.
- Enforce unique email addresses in the database.
- Hash passwords using a suitable password-hashing algorithm before storing them.
- Avoid returning passwords or other sensitive fields in API responses.
- Add proper authorization checks so users can modify only resources they are permitted to access.
- Validate incoming request data and handle errors consistently.
- Configure CORS to allow only trusted frontend origins in production.

## 🔮 Future Enhancements

- JWT-based authentication and role-based authorization.
- Advanced project search and filtering.
- Notifications for project invitations and join requests.
- Project team chat and collaboration tools.
- File and project-document uploads.
- Student skill recommendations and teammate matching.
- Project progress tracking and milestone management.
- Automated testing and CI/CD integration.

## 🎯 Learning Outcomes

This project demonstrates practical experience with:

- Full-stack web application development.
- React component-based frontend development.
- Java and Spring Boot REST API development.
- Database integration using MySQL and Spring Data JPA.
- Client-server communication using Axios.
- Git and GitHub version control.
- Environment-based configuration and cloud deployment.
- Debugging API, database, and deployment issues.

## 👨‍💻 Author

**Ashrith Patel**

GitHub: [ashrith-patel-31](https://github.com/ashrith-patel-31)

## 📄 License

This project was developed for educational and academic purposes. Add a license file if you intend to distribute or reuse the project under specific terms.

---

**Campus Project Hub — Find Skills. Build Projects. Find Teammates.**
