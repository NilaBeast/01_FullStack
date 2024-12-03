# Node.js Project Setup Guide

This guide provides step-by-step instructions for creating and running a basic Node.js project. We'll use VS Code for development and Nodemon for automatic server restarts during development.

---

## Prerequisites

1. **Visual Studio Code (VS Code)**  
   Download and install VS Code from [here](https://code.visualstudio.com/).

2. **Node.js**  
   Download and install Node.js from [here](https://nodejs.org/).  
   _(Ensure that Node.js includes npm, the Node Package Manager.)_

---

## Project Structure

Below is the recommended file structure for this project:

```
project-root/
│
├── public/       # Static files (e.g., CSS, JS, images)
├── views/        # EJS templates or other view files
├── index.js      # Entry point for the Node.js application
├── package.json  # Contains project metadata and dependencies
└── package-lock.json
```

---

## Steps to Set Up and Run the Project

1. **Create the Project Folder**

   ```bash
   mkdir my-node-project
   cd my-node-project
   ```

2. **Initialize the Project**  
   Generate a `package.json` file with default settings:

   ```bash
   npm init -y
   ```

3. **Install Dependencies**  
   Add the required dependencies for your project:

   ```bash
   npm install express ejs
   ```

4. **Install Nodemon Globally**  
   Nodemon is a utility that automatically restarts your application when file changes are detected:

   ```bash
   npm install -g nodemon
   ```

5. **Create Files and Folders**  
   Create the required directories and files:

   ```bash
   mkdir public views
   touch index.js
   ```

6. **Write Code in `index.js`**  
   Add the following basic server code to `index.js`:

   ```javascript
   import express from "express";

   const app = express();

   const __dirname = dirname(fileURLToPath(import.meta.url));
   app.use(express.static("public"));
   app.use(express.static("public"));

   app.set("view engine", "ejs");

   const PORT = 3000;

   app.get("/", (req, res) => {
     res.render(__dirname + '/views/index.ejs');
   });

   app.listen(PORT, () => {
     console.log(`Server running on http://localhost:${PORT}`);
   });
   ```

7. **Run the Project Using Nodemon**  
   Start the server using Nodemon to automatically reload on file changes:
   ```bash
   nodemon index.js
   ```

---

## Access Your Application

1. Open a web browser and visit:  
   [http://localhost:3000](http://localhost:3000)

2. Modify your files as needed; Nodemon will automatically restart the server.

---

## Tips for Development

- Keep your `public` folder organized with subfolders like `css`, `js`, and `images`.
- Write modular code by creating separate route files if needed.
- Use `.env` files for managing environment variables (e.g., `PORT`, `API_KEYS`).

---

Happy coding! 🚀
