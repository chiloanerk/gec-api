# Node.js Express and React Starter Template

This project is meant to help be a starting point for combining Node.js Express backend and a React frontend.
This is beneficial when having two teams working on the different technologies. The second benefit is that it includes 
a deployment configuration for working with Azure containers making deployment to Web App platform simple and quick.

### Directory Structure
The folders are structured to be friendly to get into. The backend should work with any framework having a build folder.
- frontend
  - build - This is where the production files need to be
- backend
  - bin/www - is the entry point of our application
- .github
  - workflow/workflow-script-yml - change to .yml and add your downloaded azure key in the file.

### Working with the code
The server has an entry point under `bin/www`, it points to `app.js` where it calls a static page from the folder above at 
`../frontend/build`. Without this folder the frontend won't run. I have setup a postinstall script to run after npm install in
the root directory. This means you should have it before you test the app.

To create a new build you will need to run, from inside the frontend `npm run build`. It will build our production ready files.

### Deployment Requirements

- There isn't much documentation on this project format but what works is:
  - Create an App Services project on Azure and set it to basic authentication.
  - Proceed to Deployment Center and link with Github and select repository and confirm.
  - It will create a github workflow in your repository, replace its contents with the one provided in this project but keep the publisher key.
  - Make sure everything runs locally and commit to github. It should trigger a workflow under actions tab.
  - You will need to set a start command on Azure the portal, under 'configurations' on the left pane to `node backend/bin/www`.
  - If all was done correctly it should work when the project is pushed to the main branch automatically.

### End
  - It was fun learning about the building CI/CD pipelines and would appreciate if you add your input to this guide.

