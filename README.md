# PERN Stack Project (Backend + Frontend with Next.js)

This is a full-stack project using the PERN stack, which includes PostgreSQL, Express.js, Next.js, and Node.js. The backend is implemented with Node.js and Express, while the frontend uses Next.js. Prisma is used as the ORM to manage database interactions. The project is configured to be easily run in a Docker environment.

backend/: Contains the backend code written in Node.js with Express and Prisma for ORM.
prisma/: Contains the Prisma schema and migration files.
frontend/: Contains the frontend code using Next.js.
.gitignore: Specifies which files or folders should be ignored by Git.
docker-compose.yml: Docker Compose configuration file for orchestrating the backend and PostgreSQL database containers.

###Prerequisites
Before getting started, make sure you have the following installed on your machine:

Docker
Docker Compose
Node.js (for running Prisma CLI commands locally)

### Getting Started

1. Clone the Repository
   First, clone the repository to your local machine:

bash
Copiar código
git clone https://github.com/galdinorenantruta/pern-crud-app.git
cd pern-crud-app 2. Configure Environment Variables
The necessary environment variables for the backend are defined in the docker-compose.yml. The default configuration uses a PostgreSQL database running in a container.

3. Install Dependencies
   Before building the Docker containers, you may want to install the dependencies locally (if you're planning to run migrations or generate Prisma client):

bash
Copiar código
cd backend
npm install 4. Run Database Migrations
If you haven't set up the database yet, you can apply the Prisma migrations to set up the database schema:

bash
Copiar código
npx prisma migrate dev
This command will apply any pending migrations and update your PostgreSQL database schema accordingly.

5. Build and Start the Containers with Docker
   With Docker and Docker Compose installed, you can run the entire project using the following command:

bash
Copiar código
docker-compose up --build
This command will:

Backend: Build the Docker image for the backend and run it on port 4000.
Database: Start a PostgreSQL container using version 12, accessible on port 5432. 6. Accessing the Application
The backend will be accessible at http://localhost:4000.
The frontend will be accessible at http://localhost:3000 (if configured in Docker, see below). 7. Stopping the Containers
To stop and remove the created containers, run:

bash
Copiar código
docker-compose down

### Additional Notes

Ensure that ports 4000 and 5432 are not being used by other services on your machine.
Prisma is used to interact with the PostgreSQL database. You can manage the schema, run migrations, and generate the Prisma Client using Prisma commands.
If you need to run database migrations or seed data, you can do so with the Prisma CLI, either inside or outside of Docker.
