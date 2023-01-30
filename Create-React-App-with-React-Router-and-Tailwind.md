# Create a React app with React Router and Tailwind

## Setting Up the Project

1. Create a directory with the name of the project you want to create
1. Run `npx create-react-app .` in the terminal
1. Cleanup before first pushing to GitHub. These steps are not necessary because `create-react-app` obviously creates a working React app, but it's nice to have things cleaned up and personalized for an initial commit.
    1. Run `rm -rf .git` to remove the git info that was created
    1. Delete the test in `/src/App.test.js`
    1. Delete or replace logo.svg
    1. Delete the CSS in `/src/App.css`
    1. Update the favicon.ico in `/public/`
    1. Update the `<meta>` elements in `/public/index.html`
    1. Update the `logo192.png` and `logo512.png` files in `/public/`
1. Run `npm install react-router-dom`
1. Open `/src/index.js` and add an import statement: `import { createBrowserRouter, RouterProvider } from 'react-router-dom';`
1. Replace the `<App />` component with `<RouterProvider router={router} />`
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

1. Create a basic React component for Error in `/src/`
1. Create folder `/src/pages/`
1. Add basic React components called Home and About
1. Import the Home and About components in the `/src/index.js/` file

## Pushing the Project to GitHub

1. Run `git init`
1. Run `git commit -m "Initial commit"`
1. Run `git branch -M main`
1. Run `git remote add origin https://github.com/kafkaesc/<YOUR REPO NAME>`
1. Run `git push -u origin main`

(These are the same instructions GitHub will show you when you create an empty repository.)