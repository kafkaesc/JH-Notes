# Create a React app with React Router and Tailwind

By Jared Hettinger

## Prerequisites

1. [VSCode](https://code.visualstudio.com) is installed
1. [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) is installed
1. [Node.js and npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) are installed
1. A [GitHub](https://github.com) account

## Setting Up the Project with Create React App

1. Create a directory with the name of the project you want to create
1. Run `npx create-react-app .` in the terminal

## Install and Setup React-Router

1. Run `npm install react-router-dom`
1. Open `/src/index.js` and add an import statement: `import { createBrowserRouter, RouterProvider } from 'react-router-dom';`
1. Rename `App.js` to `App.jsx`
1. In `index.js` Replace the `<App />` component with `<RouterProvider router={router} />`
1. Above the render function write:

        const router = createBrowserRouter([
	        {
            path: '/',
            element: <App />,
            errorElement: <Error />,
            children: [
              { path: '/', element: <Home /> },
              { path: '/About', element: <About /> },
              { path: '/Home', element: <Home /> },
            ],
	        },
        ]);

1. Create a basic React component for `Error.jsx` in `/src/`

        function Error() {
          return <h1 className="text-3xl font-bold text-center">Error Component</h1>
        }

        export default Error;

1. Create folder `/src/pages/`
1. Create a basic component for `Home.jsx` in `/src/pages/`

        function Home() {
          return <h1 className="text-3xl font-bold text-center">Home Component</h1>
        }

        export default Home;

1. Create a basic component for `About.jsx` in `/src/pages/`

        function About() {
          return <h1 className="text-3xl font-bold text-center">About Component</h1>
        }

        export default About;

1. Import the About, Error, and Home components in the `/src/index.js/` file

        import About from './pages/About';
        import Error from './Error';
        import Home from './pages/Home';

1. Replace the content of `App.jsx`

        import { Outlet } from "react-router-dom";
        import "./App.css";

        function App() {
          return <Outlet />;
        }

        export default App;

1. Run `npm start` and test the paths

## Install and Setup Tailwind

1. Run `npm install -D tailwindcss` to install Tailwind
1. Run `npx tailwindcss init` to create the Tailwind config file
1. In `tailwind.config.js` update `content: []` to be `content: ["./src/**/*.{html,js,jsx}"]`
1. In `/src/` create the file `input.css` and `output.css` and leave them blank
1. In `App.css` add

        @tailwind base;
        @tailwind components;
        @tailwind utilities;

1. In `App.jsx` add `import './output.css';` to the component
1. In the terminal run `npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch`
1. Open a new terminal and run `npm start`

## Clean-up Before Initial Commit

Cleanup before first pushing to GitHub. These steps are not necessary to setup a working React app, but customizing a projects logos and information before the first push is nice.

1. Run `rm -rf .git` to remove the git info that was created
1. Delete the test in `/src/App.test.js`
1. Delete or replace `logo.svg`
1. Delete the CSS in `/src/App.css`
1. Update the favicon.ico in `/public/`
1. Update the `<meta>` elements in `/public/index.html`
1. Update the `logo192.png` and `logo512.png` files in `/public/`

## Pushing the Project to GitHub

These are the nearly the same instructions GitHub will show you when you create an empty repository, except with the addition of step 2.

1. Run `git init`
1. Run `git add .`
1. Run `git commit -m "Initial commit"`
1. Run `git branch -M main`
1. Run `git remote add origin https://github.com/kafkaesc/<YOUR REPO NAME>`
1. Run `git push -u origin main`
