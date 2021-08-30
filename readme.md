## Getting Started

Warning! This documentation is not super stable. Post an issue if you find any trouble or something is not clear

- Install Node.js >= 7.4.0 [https://nodejs.org/](https://nodejs.org/)

- Install a Git client. I recommend SourceTree [https://www.sourcetreeapp.com/](https://www.sourcetreeapp.com/)

- Clone this repository into a folder in your computer [https://help.github.com/articles/which-remote-url-should-i-use/](https://help.github.com/articles/which-remote-url-should-i-use/)

- Install the dependencies using NPM or Yarn:

````
npm install
````

- Create a new project in your [Firebase account](http://firebase.google.com)

- Enable at the Email/Password provider in the [Firebase authentication providers](https://console.firebase.google.com/project/bigmomo-647f1/authentication/providers)

- Create a file called `.env` in the root of your cloned repository and add the following code. Replace the values with the ones from the project you created in Firebase:

````
FIREBASE_API_KEY=your_firebase_api_key
FIREBASE_AUTH_DOMAIN=your_firebase_project.firebaseapp.com
FIREBASE_DATABASE_URL=https://your_firebase_project.firebaseio.com
FIREBASE_STORAGE_BUCKET=your_firebase_project.appspot.com
````

- Update the default project value in `.firebaserc`

- If you want some demo data, import `/data/demo-data.json` into your Firebase database

- If you are going to use Firebase storage, you should give read access to everyone, otherwise only the authenticated users will be able to download images or files. In your [Firebase console](https://console.firebase.google.com), replace the rules with these ones:

````
allow read: if true;
allow write: if request.auth != null;
````

- To give a user admin rights, you have to add a field called `level` with the value `5` into a user (using the firebase UI). Once you do that, login into Hypatia with that user and you will see the `admin` link in the sidebar navigation

### Start development server with hot reloading

````
npm run dev
````

### Testing

Run test once

````
npm run test
````

Test watch

````
npm run test:watch
````

### Linting

Linting is using Airbnb Eslint configuration

````
npm run lint
````

### Deploy to production

Build for production

````
npm run build
````

Install Firebase tools (if you haven't done it yet)

````
npm install -g firebase-tools
````

Login and init the project

````
firebase login
firebase init
````

Deploy to Firebase

````
firebase deploy
````
