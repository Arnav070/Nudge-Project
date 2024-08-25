1. Prerequisites
Before you can run the application, ensure that the following software is installed on the new machine:

1.1 Install Node.js and npm
Node.js: Required to run the backend and manage frontend dependencies.
npm (Node Package Manager): Comes with Node.js and is used to install packages.
Installation:

Download and install Node.js from the official website.
Verify the installation by running:
bash
Copy code
node -v
npm -v
1.2 Install MongoDB
MongoDB: The database used by your application.
Installation:

Download and install MongoDB from the official website.
Follow the setup instructions specific to your operating system.
Verify MongoDB is installed by running:
bash
Copy code
mongo --version
1.3 Install Git
Git: Required to clone the application repositories from GitHub.
Installation:

Download and install Git from the official website.
Verify Git is installed by running:
bash
Copy code
git --version
2. Clone the Repositories
Assuming your frontend and backend are in separate GitHub repositories:

Clone the Backend Repository:

bash
Copy code
git clone <backend-repository-url>
cd <backend-repository-directory>
Clone the Frontend Repository:

bash
Copy code
git clone <frontend-repository-url>
cd <frontend-repository-directory>
3. Setup and Run the Backend
Navigate to the Backend Directory:

bash
Copy code
cd <backend-repository-directory>
Install Dependencies:

bash
Copy code
npm install
Set Up Environment Variables:

Create a .env file in the backend directory if it doesn't exist:
bash
Copy code
touch .env
Add the required environment variables (e.g., MongoDB URI, port):
bash
Copy code
MONGO_URI=mongodb://localhost:27017/your-database-name
PORT=5000
Start MongoDB:

Ensure MongoDB is running:
bash
Copy code
mongod
Run the Backend Server:

bash
Copy code
npm start
Or, if using nodemon:
bash
Copy code
npx nodemon server.js
4. Setup and Run the Frontend
Navigate to the Frontend Directory:

bash
Copy code
cd <frontend-repository-directory>
Install Dependencies:

bash
Copy code
npm install
Set Up Environment Variables:

Create a .env file in the frontend directory if it doesn't exist:
bash
Copy code
touch .env
Add the necessary environment variables (e.g., Backend API URL):
bash
Copy code
REACT_APP_API_URL=http://localhost:5000/api
Run the Frontend Server:

bash
Copy code
npm start
The frontend should now be running on http://localhost:3000.
5. Verify the Application
Open the Frontend: Go to http://localhost:3000 in your web browser.
Check Interaction: Ensure the frontend can interact with the backend, and verify that data from MongoDB is being correctly displayed.
6. Troubleshooting
Port Conflicts: Ensure that no other processes are using the ports required by MongoDB, Node.js backend, and React frontend.
MongoDB Connection: If the MongoDB connection fails, verify that the MongoDB service is running and that the MONGO_URI is correctly configured in the .env file.
7. Docker Option (Optional)
For easier deployment on a new machine, consider using Docker:

Create Dockerfiles for the frontend and backend.
Create a docker-compose.yml file to define and manage multi-container Docker applications.
8. Running the Application with CI/CD
GitHub Actions: Once set up, every time you push changes to the repository, GitHub Actions will automatically build, test, and deploy your application based on the workflows defined in the .github/workflows/ directory.
By following these steps, you should be able to successfully run your full-stack application on a new machine.
