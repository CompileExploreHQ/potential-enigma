# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

# Run React App Locally with Nginx

To run a React app using Nginx on Windows, you need to follow these general steps. Note that the specifics might vary based on your project structure and requirements.

1. **Build Your React App:**
   - Open a terminal in your React project directory.
   - Run the following command to build your React app:
     ```bash
     npm run build
     ```
   This will generate a `build` folder containing the production-ready build of your React app.

2. **Install Nginx on Windows:**
   - Download the latest version of Nginx for Windows from the official Nginx website (https://nginx.org/en/download.html).
   - Extract the downloaded ZIP file to a location on your machine.

3. **Configure Nginx:**
   - Navigate to the Nginx installation directory and locate the `conf` folder.
   - Edit the `nginx.conf` file using a text editor.
   - Add a new `server` block to the configuration file to define the configuration for your React app. Here's a basic example:
     ```nginx
     server {
         listen 80;
         server_name localhost;

         location / {
             root   path/to/your/react/app/build;
             index  index.html;
             try_files $uri $uri/ /index.html;
         }
     }
     ```
     Replace `path/to/your/react/app/build` with the actual path to your React app's build folder.

4. **Start Nginx:**
   - Open a command prompt as an administrator.
   - Navigate to the Nginx installation directory.
   - Run the following command to start Nginx:
     ```bash
     nginx
     ```

5. **Access Your React App:**
   - Open a web browser and navigate to `http://localhost` (or the server_name you specified in the `nginx.conf` file).

Now, Nginx should be serving your React app. Keep in mind that these steps provide a basic configuration, and you may need to adjust them based on your specific project structure and requirements. Additionally, always refer to the official Nginx documentation for more details and updates.
