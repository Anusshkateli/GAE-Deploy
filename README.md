## Weather App Deployment on Google App Engine

This repository contains a simple Weather App designed to be deployed on Google App Engine (GAE) using Node.js and Express. The application fetches weather information for a specified city and displays it to the user.

### [cite\_start]Project Structure [cite: 7]

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

### Files and Their Purpose

  * [cite\_start]**`app.js`**: This is the main Node.js application file[cite: 8]. It sets up an Express server to:

      * [cite\_start]Serve static files (HTML, CSS, JavaScript) from the `public` directory[cite: 8].
      * [cite\_start]Handle the root route (`/`) by sending the `index.html` file[cite: 8].
      * [cite\_start]Listen for incoming requests on the specified port (either from `process.env.PORT` or default to `8080`)[cite: 8].

  * [cite\_start]**`app.yaml`**: This file configures the Google App Engine environment for the application[cite: 9]. [cite\_start]It specifies that the runtime environment is `nodejs20`[cite: 9].

  * [cite\_start]**`package.json`**: This file defines the project's metadata and its dependencies[cite: 10].

      * [cite\_start]`name`: `gcp-express-app` [cite: 10]
      * [cite\_start]`version`: `1.0.0` [cite: 10]
      * [cite\_start]`main`: `app.js` (the entry point of the application) [cite: 10]
      * [cite\_start]`scripts`: Includes a `start` script to run the application using `node app.js`[cite: 10].
      * [cite\_start]`dependencies`: Lists `express` (version `^5.1.0`) as a required dependency[cite: 10].

  * [cite\_start]**`public/`**: This directory holds all the static front-end assets of the web application[cite: 7].

      * [cite\_start]**`index.html`**: The main HTML file for the Weather App[cite: 11]. It includes:
          * [cite\_start]Basic HTML structure with a title "Weather App"[cite: 11].
          * [cite\_start]A link to `styles.css` for styling[cite: 11].
          * [cite\_start]An input field for entering a city name[cite: 11].
          * [cite\_start]A "Get Weather" button[cite: 11].
          * [cite\_start]Sections to display city name, temperature, and weather description[cite: 11].
          * [cite\_start]An error message section[cite: 11].
          * [cite\_start]A link to `script.js` for dynamic functionality[cite: 11].
      * [cite\_start]**`script.js`**: This JavaScript file handles the client-side logic[cite: 12]. It:
          * [cite\_start]Listens for the "Get Weather" button click[cite: 12].
          * [cite\_start]Retrieves the city name from the input field[cite: 12].
          * [cite\_start]Asynchronously fetches weather data from the OpenWeatherMap API using a provided API key[cite: 12].
          * [cite\_start]Displays the fetched weather data (city name, temperature, description)[cite: 12].
          * [cite\_start]Handles and displays error messages if a city is not found[cite: 12].
      * [cite\_start]**`styles.css`**: This CSS file provides the styling for the Weather App's user interface[cite: 13]. [cite\_start]It includes styles for the body, container, input fields, buttons, and weather information display[cite: 13].

### Deployment Steps

To deploy this Weather App to Google App Engine, follow these steps:

1.  [cite\_start]**Create a Google Cloud Account**: If you don't have one, create an account in Google Cloud.
2.  [cite\_start]**Download Google Cloud CLI and SDK**: Download and install the Google Cloud CLI and SDK. During the installation, you will be prompted to select an account and create a new project.
3.  **Configure Google Cloud Project**: After successful installation, open your terminal. [cite\_start]The `gcloud init` command will guide you through the configuration[cite: 6]. [cite\_start]Select the account you wish to use and create a new project or select an existing one[cite: 6].
4.  [cite\_start]**Create Project Files**: Ensure all the required files (`app.js`, `app.yaml`, `package.json`, and the `public` directory with `index.html`, `script.js`, `styles.css`) are present with the correct structure[cite: 7]. [cite\_start]Make sure Python 3 is installed[cite: 7].
5.  [cite\_start]**Grant Storage Admin Permission**: Give "Storage Admin" permission to your Google Cloud project to allow deployment to Google Cloud[cite: 14].
6.  [cite\_start]**Deploy the Application**: Navigate to the `gcp-express-app` directory in your terminal and run the command `gcloud app deploy`[cite: 15].
7.  [cite\_start]**Browse the Application**: Once deployed, run `gcloud app browse` in your terminal to open the application in your default web browser[cite: 16].

The application will then be accessible via the provided Google App Engine URL.
