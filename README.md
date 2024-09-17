# FastAPI Azure Web App Deployment

This repository contains a simple FastAPI application that is deployed to Azure Web Apps with CI/CD using GitHub Actions.

## Project Overview

This project includes a basic FastAPI application that returns a JSON response with the message `"Hello, Azure Web Apps!"` when accessed at the root endpoint. The deployment process is automated using GitHub Actions to deploy to Azure Web Apps.

## Application Structure

- `main.py`: Contains the FastAPI application code.
- `requirements.txt`: Lists the Python dependencies for the application.
- `.github/workflows/deploy.yml`: GitHub Actions workflow file for CI/CD.

## Getting Started

### Prerequisites

- Python 3.x
- `pip` (Python package installer)
- Git

### Local Setup

1. **Clone the Repository**

    ```bash
    git clone https://github.com/Cetyl/fastapi-azure-web-app.git
    cd fastapi-azure-web-app
    ```

2. **Install Dependencies**

    ```bash
    pip install -r requirements.txt
    ```

3. **Run the Application Locally**

    ```bash
    uvicorn main:app --reload
    ```

    - Visit `http://127.0.0.1:8000` in your browser to see the application in action.

### Deploying to Azure Web Apps

1. **Create an Azure Web App**

    - Go to the [Azure Portal](https://portal.azure.com/).
    - Create a new App Service with Python as the runtime stack.
    - Note the App Service name for later use.

2. **Set Up GitHub Actions**

    - In the Azure Portal, go to your Web App's "Overview" section and click on "Get publish profile".
    - In GitHub, navigate to your repository's "Settings" > "Secrets" > "Actions".
    - Add a new repository secret with the name `AZURE_WEBAPP_PUBLISH_PROFILE` and paste the content of the publish profile.

3. **Deploy the Application**

    - Ensure your code is pushed to the `main` branch of your GitHub repository.
    - GitHub Actions will automatically trigger the deployment workflow to deploy the application to Azure Web Apps.

## GitHub Actions Workflow

The deployment workflow is defined in `.github/workflows/deploy.yml`. It performs the following steps:

1. Checks out the code from the repository.
2. Sets up Python.
3. Installs the application dependencies.
4. Deploys the application to Azure Web Apps using the publish profile.

## Verifying Deployment

1. **Access the Deployed Application**

    - Visit the URL of your Azure Web App (e.g., `https://fastapi-azure-internship-eqbgamffauh0cdfq.eastasia-01.azurewebsites.net`).
    - You should see the JSON response: `{"message": "Hello, Azure Web Apps!"}`.

## Troubleshooting

- Ensure all required secrets are set up in GitHub.
- Check the GitHub Actions logs for deployment issues.
- Verify that the Azure Web App is correctly configured and running.

## Contributing

Feel free to fork the repository and submit pull requests. For any issues or feature requests, please use the [GitHub Issues](https://github.com/<your-username>/fastapi-azure-web-app/issues) page.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
