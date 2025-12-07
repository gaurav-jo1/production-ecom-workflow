# Production E-Commerce Workflow 🏢

Welcome to **Production E-Commerce Workflow**, a full-stack portfolio project demonstrating a production-grade online shopping system. This end-to-end platform goes beyond basic demos, featuring robust authentication (including signup, login, password reset with email validation), Google OAuth integration, user-specific persistent shopping carts, a polished React UI, and a scalable architecture with Docker, PostgreSQL for data persistence, Redis for caching, and a Python backend.

Key highlights:
- **Secure User Flows**: Complete auth/authorization with email-based recovery and validation codes.
- **Seamless Experience**: Persistent carts tied to user sessions, smooth OAuth handoffs.
- **Production-Ready**: Dockerized for easy deployment, modern stack for scalability.

![Screenshot from 2024-07-10 08-36-34](https://github.com/gaurav-jo1/E-commerce/assets/93304640/8cce0615-6110-4556-8e6b-eada028ffa34)

![Screenshot from 2024-07-10 08-26-37](https://github.com/gaurav-jo1/E-commerce/assets/93304640/c38fda5d-490c-4bdd-ad10-c0ee4a410c7a)

## Getting Started 🔥

Follow these steps to set up and run the project locally:

1. Clone the repository:
   ```sh
   git clone https://github.com/gaurav-jo1/production-ecom-workflow.git
   ```

2. Navigate to the project directory:
   ```sh
   cd production-ecom-workflow
   ```

3. Install frontend dependencies:
   ```sh
   cd frontend && npm install
   cd ..
   ```

4. Set up backend environment (optional for non-Docker dev):
   - Create and activate a virtual environment:
     ```sh
     cd backend
     python -m venv venv
     source venv/bin/activate  # On Windows: venv\Scripts\activate
     pip install -r requirements.txt
     cd ..
     ```

5. Configure Google OAuth (optional for enhanced login):
   - Create a project in the [Google API Console](https://console.cloud.google.com/apis/dashboard).
   - Enable the Google+ API and create OAuth 2.0 credentials (Web application type).
   - Add authorized origins (e.g., `http://localhost:5173`) and redirect URIs (e.g., `http://localhost:5173/auth/callback`).
   - Download the `client_secret.json` and place it in the `frontend` directory.
   - For a step-by-step guide, watch this [YouTube tutorial](https://www.youtube.com/watch?v=roxC8SMs7HU).

    <p align="center">
    <img src="https://user-images.githubusercontent.com/93304640/236677794-cddb3f35-2ef9-4a60-b9cf-8547a3a54753.png" alt="client_json_img" width="450" height="450">
    </p>

6. Update environment variables:
   - In `backend/.env`, add:
     ```
     GOOGLE_CLIENT_ID=your_google_client_id_here
     # Add other vars like DB credentials if needed for custom setup
     ```

7. Run the application with Docker:
   ```sh
   docker compose up --build
   ```
   This spins up all services (frontend, backend, Postgres, Redis, Redash) in containers.

## Access the Application

- **Frontend**: Open [http://localhost:5173](http://localhost:5173) in your browser.
- **Backend API**: Available at [http://localhost:8000](http://localhost:8000) (e.g., for docs at `/docs`).

## Troubleshooting
- Ensure Docker and Docker Compose are installed.
- For port conflicts, edit `docker-compose.yml`.
- If using the virtualenv backend setup, run `uvicorn main:app --reload` in the backend dir.

## Contributing
Feel free to fork, raise issues, or submit PRs for improvements. This project is designed as a showcase but welcomes enhancements!

Thanks for checking out **Production E-Commerce Workflow**—a testament to building deployable, full-featured systems! 🚀
