## Weather App Deployment on Google App Engine

This repository contains a simple Weather App designed to be deployed on Google App Engine (GAE) using Node.js and Express. The application fetches weather information for a specified city and displays it to the user.

      Project Structure 

The project follows a clear and organized structure:

```
gcp-express-app/
├── app.js
├── app.yaml
├── package.json
├── public/
│   ├── index.html
│   ├── script.js
│   └── styles.css
```

    Files and Their Purpose

  `app.js`: This is the main Node.js application file. It sets up an Express server to:

      * Serve static files (HTML, CSS, JavaScript) from the `public` directory.
      * Handle the root route (`/`) by sending the `index.html` file.
      * Listen for incoming requests on the specified port (either from `process.env.PORT` or default to `8080`).

  * `app.yaml`: This file configures the Google App Engine environment for the application. It specifies that the runtime environment is `nodejs20`.

  * `package.json`: This file defines the project's metadata and its dependencies.

      * `name`: `gcp-express-app` 
      * `version`: `1.0.0`
      * `main`: `app.js` (the entry point of the application).
      * `scripts`: Includes a `start` script to run the application using `node app.js`.
      * `dependencies`: Lists `express` (version `^5.1.0`) as a required dependency.

  * `public/`: This directory holds all the static front-end assets of the web application.

      * `index.html`: The main HTML file for the Weather App. It includes:
          * Basic HTML structure with a title "Weather App".
          * A link to `styles.css` for styling.
          * An input field for entering a city name.
          * A "Get Weather" button.
          * Sections to display city name, temperature, and weather description.
          * An error message section.
          * A link to `script.js` for dynamic functionality.
          * `script.js`**: This JavaScript file handles the client-side logic. It:
          * Listens for the "Get Weather" button click.
          * Retrieves the city name from the input field.
          * Asynchronously fetches weather data from the OpenWeatherMap API using a provided API key.
          * Displays the fetched weather data (city name, temperature, description).
          * Handles and displays error messages if a city is not found.
      *`styles.css`: This CSS file provides the styling for the Weather App's user interface. It includes styles for the body, container, input fields, buttons, and weather information display.

          Deployment Steps

To deploy this Weather App to Google App Engine, follow these steps:

1. Create a Google Cloud Account: If you don't have one, create an account in Google Cloud.
2. Download Google Cloud CLI and SDK: Download and install the Google Cloud CLI and SDK. During the installation, you will be prompted to select an account and create a new project.
3.  Configure Google Cloud Project: After successful installation, open your terminal.The `gcloud init` command will guide you through the configuration.Select the account you wish to use and create a new project or select an existing one.
4. Create Project Files: Ensure all the required files (`app.js`, `app.yaml`, `package.json`, and the `public` directory with `index.html`, `script.js`, `styles.css`) are present with the correct structure. Make sure Python 3 is installed.
5.  Grant Storage Admin Permission: Give "Storage Admin" permission to your Google Cloud project to allow deployment to Google Cloud.
6.  *Deploy the Application*: Navigate to the `gcp-express-app` directory in your terminal and run the command `gcloud app deploy`.
7.  *Browse the Application*: Once deployed, run `gcloud app browse` in your terminal to open the application in your default web browser.

The application will then be accessible via the provided Google App Engine URL.
