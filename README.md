# MKCE-AI-BOOKING
 Hotal booking application with MERN fullstack technology
 ## Dependanceies
- Node js
- React js
- Express js
- Vite
- Mongodb

## Installations process
- create the project folder with name of MKCE-AI
- Install the node js on the project folder 



## Prerequisites

Before you start, make sure you have the following installed on your machine:

- [Node.js](https://nodejs.org/) (and npm, which comes with Node.js)

**Verify Installation:**
   Open a new terminal or command prompt and run the following commands to verify that Node.js and npm are installed:

   ```bash
   node -v
   npm -v
   ```

  

## Installing Vite

[Vite](https://vitejs.dev/) is a build tool for modern web development. Follow these steps to install Vite globally on your machine:

1. Open a terminal or command prompt.

2. Run the following command to install Vite globally:

   ```bash
   npm install -g create-vite
   ```


This command will run the Vite executable from the remote npm repository. It will configure the necessary tools to scaffold a React local development environment. Finally, it will open a command-line menu for project settings and language type.

After the script finishes, you will be prompted to enter a project name:

```bash Output
yarn create v1.22.10
[1/4] Resolving packages...
[2/4] Fetching packages...
[3/4] Linking dependencies...
[4/4] Building fresh packages...

success Installed "create-vite@2.9.0" with binaries:
- create-vite
- cva
? Project name: » vite-project
```
Type your project name (this tutorial will use digital-ocean-vite as the example name):

MKCE-AI-vite
After entering your project name, Vite will prompt you to select a framework:

```bash Output
? Select a framework: » - Use arrow-keys. Return to submit.
Vanilla
Vue
> React
Preact
Lit
Svelte
Others
```
Vite allows you to bootstrap a range of project types, not just React. Currently, it supports React, Preact, Vue, Lit, Svelte, and vanilla JavaScript projects.

Use your keyboard arrow key to select React.

After selecting the React framework, Vite will prompt you to choose the language type. You can use JavaScript or TypeScript to work on your project.

Use your arrow keys to select JavaScript:

 ```bash Output
? Select a variant: » - Use arrow-keys. Return to submit.
> JavaScript
TypeScript
JavaScript + SWC
TypeScript + SWC
```

## install yarn 
```bash
npm install --global yarn
```
- vite will create react app in client folder 
- and in client folder the default folders  and files will create 
- under the src folder we need to alter and create the folders
## install pakages in client folder
- using yarn add we can install the pakges
  
```bash
yarn add react-router-dom
yarn add axios
yarn add tailwindcss
```
- then we need to modify some files in src folder and create some files
- first remove the content of app.css
- then create the files in src folder the name of the files are
- AccountNav.jsx
- AddressLink.jsx
- BookingDates.jsx
- BookingWidget.jsx
- Header.jsx
- Layout.jsx
- Perks.jsx
- PhotoUploader.jsx
- PlaceGallery.jsx
- PlaceImg.jsx
- UserContext.jsx
 modify the code in listed files
- App.jsx
- main.jsx
- index.css
## App.jsx
```python
import './App.css'
import {Route, Routes} from "react-router-dom";
import IndexPage from "./pages/IndexPage.jsx";
import LoginPage from "./pages/LoginPage";
import Layout from "./Layout";
import RegisterPage from "./pages/RegisterPage";
import axios from "axios";
import {UserContextProvider} from "./UserContext";
import ProfilePage from "./pages/ProfilePage.jsx";
import PlacesPage from "./pages/PlacesPage";
import PlacesFormPage from "./pages/PlacesFormPage";
import PlacePage from "./pages/PlacePage";
import BookingsPage from "./pages/BookingsPage";
import BookingPage from "./pages/BookingPage";

axios.defaults.baseURL ='http://localhost:4000';
axios.defaults.withCredentials = true;

function App() {
  return (
    <UserContextProvider>
      <Routes>
        <Route path="/" element={<Layout />}>
          <Route index element={<IndexPage />} />
          <Route path="/login" element={<LoginPage />} />
          <Route path="/register" element={<RegisterPage />} />
          <Route path="/account" element={<ProfilePage />} />
          <Route path="/account/places" element={<PlacesPage />} />
          <Route path="/account/places/new" element={<PlacesFormPage />} />
          <Route path="/account/places/:id" element={<PlacesFormPage />} />
          <Route path="/place/:id" element={<PlacePage />} />
          <Route path="/account/bookings" element={<BookingsPage />} />
          <Route path="/account/bookings/:id" element={<BookingPage />} />
        </Route>
      </Routes>
    </UserContextProvider>
  )
}

export default App
```

## index.css
```css
@tailwind base;
@tailwind components;
@tailwind utilities;

input[type="text"],input[type="password"],
input[type="email"],input[type="number"],
input[type="tel"],
textarea{
    @apply w-full border my-1 py-2 px-3 rounded-2xl;
}
textarea{
    height: 140px;
}
button{
    @apply bg-gray-300;
}
button.primary{
    background-color: #2DFADB;
    @apply bg-primary p-2 w-full text-white rounded-2xl;
}


```

## main.jsx
```python
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App'
import './index.css'
import {BrowserRouter} from "react-router-dom";

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>,
)
```







